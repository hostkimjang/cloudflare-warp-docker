# Cloudflare Warp Project

이 프로젝트는 Cloudflare Warp를 Docker 컨테이너에서 실행하기 위한 설정을 포함하고 있습니다. 이 문서에서는 프로젝트의 설정 방법과 사용법에 대해 설명합니다.

## 프로젝트 구조

```
cloudflare-warp-project
├── docker-compose.yml
├── Dockerfile
├── scripts
│   └── setup.sh
└── README.md
```

## 설정 방법

1. **Docker 설치**: Docker가 설치되어 있지 않은 경우, [Docker 공식 웹사이트](https://docs.docker.com/get-docker/)를 참조하여 설치합니다.

2. **프로젝트 클론**: 이 저장소를 클론합니다.
   ```bash
   git clone <repository-url>
   cd cloudflare-warp-project
   ```

3. **Docker 이미지 빌드**: 다음 명령어를 사용하여 Docker 이미지를 빌드합니다.
   ```bash
   docker-compose build
   ```

4. **컨테이너 실행**: 다음 명령어로 컨테이너를 실행합니다.
   ```bash
   docker-compose up -d
   ```

5. **설정 스크립트 실행**: 컨테이너 내에서 설정 스크립트를 실행하여 Cloudflare Warp를 설치하고 구성합니다.
   ```bash
   docker exec -it <container-name> /scripts/setup.sh
   ```

## 사용법

- Cloudflare Warp에 연결하려면 다음 명령어를 사용합니다.
  ```bash
  docker exec -it <container-name> warp-cli connect
  ```

- Warp 모드를 변경하려면 다음 명령어를 사용합니다.
  ```bash
  docker exec -it <container-name> warp-cli mode warp+doh
  ```

## 추가 정보

- 더 많은 정보는 [Cloudflare Warp 공식 문서](https://developers.cloudflare.com/warp-client/)를 참조하세요.