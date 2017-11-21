# angular-yarn-alpine
Docker Image for Angular Development

## How to use
sample:

`docker run --rm -it -v ${PWD}:/root angular-yarn-alpine sh`

### Use unroot user

sample:

```Dockerfile
FROM angular-yarn-alpine

RUN adduser -D appuser

COPY --chown=appuser:appuser app /home/appuser/app
ENV HOME=/home/appuser
USER appuser
WORKDIR ${HOME}/app
CMD [ "yarn d && ng serve --host 0.0.0.0 --poll 2000" ]

```
