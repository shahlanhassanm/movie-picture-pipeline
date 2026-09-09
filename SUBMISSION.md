# Project Submission — Movie Picture Pipeline

Repository: https://github.com/shahlanhassanm/movie-picture-pipeline

## Live application URLs

| Application | URL |
| --- | --- |
| Frontend | http://ae3b99e75d36c4ae0b16853ee0232b17-1737984447.us-east-1.elb.amazonaws.com |
| Backend API | http://ae61392a1591b4516b52fa741aa2a38a-1915296944.us-east-1.elb.amazonaws.com/movies |

> These point at AWS resources that are torn down after review, so the
> screenshots below are the durable evidence.

Backend response:

```json
{"movies":[{"id":"123","title":"Top Gun: Maverick"},{"id":"456","title":"Sonic the Hedgehog"},{"id":"789","title":"A Quiet Place"}]}
```

## Workflows

| Workflow | File | Run |
| --- | --- | --- |
| Frontend Continuous Integration | [.github/workflows/frontend-ci.yaml](.github/workflows/frontend-ci.yaml) | [34315118113](https://github.com/shahlanhassanm/movie-picture-pipeline/actions/runs/34315118113) |
| Backend Continuous Integration | [.github/workflows/backend-ci.yaml](.github/workflows/backend-ci.yaml) | [34316445864](https://github.com/shahlanhassanm/movie-picture-pipeline/actions/runs/34316445864) |
| Frontend Continuous Deployment | [.github/workflows/frontend-cd.yaml](.github/workflows/frontend-cd.yaml) | [34322843297](https://github.com/shahlanhassanm/movie-picture-pipeline/actions/runs/34322843297) |
| Backend Continuous Deployment | [.github/workflows/backend-cd.yaml](.github/workflows/backend-cd.yaml) | [34322565192](https://github.com/shahlanhassanm/movie-picture-pipeline/actions/runs/34322565192) |

Both applications were deployed from images tagged with the git SHA
`8d46e4925486dfcbbbc38c6c711306d3303f8e4e`.

## Pipelines fail when tests fail

Demonstrated on the `feature/failure-demo` branch:

| Workflow | Run | Result |
| --- | --- | --- |
| Frontend Continuous Integration | [34317082084](https://github.com/shahlanhassanm/movie-picture-pipeline/actions/runs/34317082084) | failure |
| Backend Continuous Integration | [34317082066](https://github.com/shahlanhassanm/movie-picture-pipeline/actions/runs/34317082066) | failure |

## Screenshots

### 1. Frontend displaying the movie list

![Frontend movie list](screenshots/01-frontend-movies.png)

### 2. Backend API returning the movie list

![Backend movies JSON](screenshots/02-backend-movies-json.png)

### 3. Frontend Continuous Integration — passing

![Frontend CI success](screenshots/03-frontend-ci-success.png)

### 4. Backend Continuous Integration — passing

![Backend CI success](screenshots/04-backend-ci-success.png)

### 5. Frontend Continuous Deployment — passing

![Frontend CD success](screenshots/05-frontend-cd-success.png)

### 6. Backend Continuous Deployment — passing

![Backend CD success](screenshots/06-backend-cd-success.png)

### 7. Frontend CI failing on a broken test

![Frontend CI failure](screenshots/07-frontend-ci-failure.png)

### 8. Backend CI failing on a broken test

![Backend CI failure](screenshots/08-backend-ci-failure.png)

### 9. Images pushed to Amazon ECR

![ECR images](screenshots/09-ecr-images.png)

### 10. Workloads running on the EKS cluster

![kubectl get all](screenshots/10-kubectl-get-all.png)
