# CICD-templates

這是一個集中的 CI/CD 參考範本庫，旨在標準化並簡化 DevOps 流程。本儲存庫收集了跨平台的流水線（Pipeline）配置，包含 **GitHub Actions**、**GitLab CI** 等主流平台，以及常用的自動化腳本。

無論您是需要一個完整的 Docker 建置流程，還是簡單的單元測試範本，都可以在這裡找到參考。

## 📂 儲存庫結構 (Repository Structure)

本專案依照「**CI/CD 平台**」作為第一層分類，並依據「**程式語言/框架**」或「**功能用途**」進行子分類。

```text
CICD-templates/
├── 📂 github-actions/          # GitHub Actions 專用 workflow 範本
│   ├── 📂 dotnet/              # .NET / C# 相關 (Build, Test, Publish)
│   ├── 📂 nodejs/              # Node.js 相關 (npm/yarn, Lint, Build)
│   ├── 📂 docker/              # Docker Image 建置與推送 (GHCR, DockerHub)
│   └── 📂 terraform/           # IaC 部署流程
│
├── 📂 gitlab-ci/               # GitLab CI/CD 專用範本 (.gitlab-ci.yml)
│   ├── 📂 templates/           # 可被 include 的共用模組 (Hidden Jobs)
│   │   ├── build.yml
│   │   ├── deploy.yml
│   │   └── security-scan.yml
│   ├── 📂 language-specific/   # 針對特定語言的完整 Pipeline 範例
│   │   ├── go.gitlab-ci.yml
│   │   └── python.gitlab-ci.yml
│   └── .gitlab-ci-base.yml     # 建議的基礎設定檔
│
├── 📂 jenkins/                 # (選用) Jenkinsfile 範本
│   ├── Jenkinsfile.maven
│   └── Jenkinsfile.gradle
│
├── 📂 scripts/                 # 跨平台共用的 Shell/Python 腳本
│   ├── update-version.sh       # 版本號自動更新腳本
│   └── notify-slack.py         # 部署通知腳本
│
└── README.md
