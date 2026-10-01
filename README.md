<div align="center">

<h1>🚀 CI/CD Laboratory</h1>

<p><b>Мои учебные проекты по автоматизации проверок, сборки и публикации приложений</b></p>
<p>13 репозиториев · 8 языков программирования · Docker · GitHub Actions</p>

<p>
  <img src="https://img.shields.io/badge/Projects-13-2563EB?style=for-the-badge" alt="13 проектов">
  <img src="https://img.shields.io/badge/Languages-8-7C3AED?style=for-the-badge" alt="8 языков">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
</p>

<p>
  <a href="#catalog">Каталог проектов</a> ·
  <a href="#releases">Готовые программы</a> ·
  <a href="#skills">Что реализовано</a> ·
  <a href="#navigation">Как посмотреть результат</a>
</p>

</div>

---

Эта коллекция показывает развитие от первого workflow до автоматической публикации контейнеров и готовых программ для Linux, macOS и Windows. Каждый проект находится в отдельном репозитории; этот README объединяет их в один каталог.

В проектах используются **Python, JavaScript, Go, Rust, PHP, C++, Java и C#**. Бейдж CI рядом с репозиторием показывает статус его workflow и ведёт к журналу запусков.

<a id="catalog"></a>

## 🗂️ Каталог проектов

### 01 · Первый workflow

| Репозиторий | Что реализовано | CI |
| --- | --- | --- |
| [my-first-cicd](https://github.com/Focsi4ek/my-first-cicd) | Workflow на YAML: запуск при push, checkout репозитория и выполнение команды на Ubuntu | [![CI](https://github.com/Focsi4ek/my-first-cicd/actions/workflows/hello.yml/badge.svg)](https://github.com/Focsi4ek/my-first-cicd/actions) |

### 02 · Проверки, тесты и Docker

| Репозиторий | Инструменты | Особенности pipeline | CI |
| --- | --- | --- | --- |
| [my-python-app](https://github.com/Focsi4ek/my-python-app) | Python · Flake8 · pytest | Матрица Python 3.9–3.12; сборка Docker-образа | [![CI](https://github.com/Focsi4ek/my-python-app/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/my-python-app/actions) |
| [my-node-app](https://github.com/Focsi4ek/my-node-app) | JavaScript / Node.js · ESLint · Jest | Матрица Node.js 18, 20, 22; сборка Docker-образа | [![CI](https://github.com/Focsi4ek/my-node-app/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/my-node-app/actions) |
| [my-go-app](https://github.com/Focsi4ek/my-go-app) | Go · golangci-lint · go test | Тесты с отчётом покрытия; сборка Docker-образа | [![CI](https://github.com/Focsi4ek/my-go-app/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/my-go-app/actions) |
| [my-rust-app](https://github.com/Focsi4ek/my-rust-app) | Rust · rustfmt · Clippy · Cargo | Debug и Release; тесты, запуск контейнера, образ как артефакт | [![CI](https://github.com/Focsi4ek/my-rust-app/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/my-rust-app/actions) |
| [my-php-app](https://github.com/Focsi4ek/my-php-app) | PHP · php -l · PHPUnit | Синтаксис и тесты; запуск контейнера, образ как артефакт | [![CI](https://github.com/Focsi4ek/my-php-app/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/my-php-app/actions) |
| [my-cpp-app](https://github.com/Focsi4ek/my-cpp-app) | C++ · clang-format · CMake · Google Test | Сборка и CTest; запуск контейнера, образ как артефакт | [![CI](https://github.com/Focsi4ek/my-cpp-app/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/my-cpp-app/actions) |
| [hello-java](https://github.com/Focsi4ek/hello-java) | Java · Maven · JUnit 5 | Проверки Maven, исполняемый JAR и Docker-образ | [![CI](https://github.com/Focsi4ek/hello-java/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/hello-java/actions) |

В `my-cpp-app`, `my-php-app` и `my-rust-app` Docker-образ сохраняется как архив в **Artifacts** запуска CI. В `my-go-app` отдельно сохраняется отчёт покрытия тестами. Доступность этих артефактов зависит от срока хранения.

### 03 · Публикация контейнеров в GHCR

| Репозиторий | Проверки | Публикация | CI |
| --- | --- | --- | --- |
| [hello-go](https://github.com/Focsi4ek/hello-go) | gofmt, go vet, тесты и сборка Go | Docker Buildx; Linux amd64 и arm64; образ `ghcr.io/focsi4ek/hello-go` | [![CI](https://github.com/Focsi4ek/hello-go/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/hello-go/actions) |
| [hello-rust](https://github.com/Focsi4ek/hello-rust) | rustfmt, Clippy, тесты и Release-сборка | Docker Buildx; Linux amd64 и arm64; образ `ghcr.io/focsi4ek/hello-rust` | [![CI](https://github.com/Focsi4ek/hello-rust/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/hello-rust/actions) |

Образы публикуются при push в `main`. Workflow создаёт теги `latest` и короткий SHA коммита. При pull request выполняется сборка без публикации.

### 04 · Бинарники в GitHub Releases

| Репозиторий | Проверки и сборка | Платформы | CI |
| --- | --- | --- | --- |
| [hello-go-bin](https://github.com/Focsi4ek/hello-go-bin) | gofmt, go vet, go test; версия внедряется при сборке | Linux amd64/arm64, macOS Intel/Apple Silicon, Windows amd64 | [![CI](https://github.com/Focsi4ek/hello-go-bin/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/hello-go-bin/actions) |
| [hello-python](https://github.com/Focsi4ek/hello-python) | Ruff, pytest; PyInstaller `--onefile` | Linux x64, macOS arm64, Windows x64 | [![CI](https://github.com/Focsi4ek/hello-python/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/hello-python/actions) |
| [hello-dotnet](https://github.com/Focsi4ek/hello-dotnet) | dotnet format, сборка, xUnit; self-contained single-file | Linux x64, macOS arm64, Windows x64 | [![CI](https://github.com/Focsi4ek/hello-dotnet/actions/workflows/ci.yml/badge.svg)](https://github.com/Focsi4ek/hello-dotnet/actions) |

Тег `v*` запускает проверки, матричную сборку и публикацию релиза. Во всех трёх проектах версия готовой программы берётся из тега. Python- и .NET-бинарники дополнительно проверяются запуском на соответствующих runner.

<a id="releases"></a>

## 📦 Готовые программы

| Проект | Релизы | Файлов в релизе v1.0.0 |
| --- | --- | --- |
| **Go** — [hello-go-bin](https://github.com/Focsi4ek/hello-go-bin) | [![Release](https://img.shields.io/github/v/release/Focsi4ek/hello-go-bin?style=flat-square&label=release)](https://github.com/Focsi4ek/hello-go-bin/releases) | 5 |
| **Python** — [hello-python](https://github.com/Focsi4ek/hello-python) | [![Release](https://img.shields.io/github/v/release/Focsi4ek/hello-python?style=flat-square&label=release)](https://github.com/Focsi4ek/hello-python/releases) | 3 |
| **C#/.NET** — [hello-dotnet](https://github.com/Focsi4ek/hello-dotnet) | [![Release](https://img.shields.io/github/v/release/Focsi4ek/hello-dotnet?style=flat-square&label=release)](https://github.com/Focsi4ek/hello-dotnet/releases) | 3 |

Бинарники релизов **v1.0.0** для Apple Silicon проверены запуском на macOS: программы выводят версию, ОС, архитектуру, приветствие и сумму `1..10 = 55`.

<details>
<summary><b>🍎 Какой файл скачать для Mac с Apple Silicon?</b></summary>

| Проект | Файл | Скачать из релиза |
| --- | --- | --- |
| Go | `hello-go-darwin-arm64` | [v1.0.0](https://github.com/Focsi4ek/hello-go-bin/releases/tag/v1.0.0) |
| Python | `hello-python-macos-arm64` | [v1.0.0](https://github.com/Focsi4ek/hello-python/releases/tag/v1.0.0) |
| C#/.NET | `hello-dotnet-macos-arm64` | [v1.0.0](https://github.com/Focsi4ek/hello-dotnet/releases/tag/v1.0.0) |

Пример запуска скачанного .NET-бинарника из папки с файлом:

```bash
chmod +x hello-dotnet-macos-arm64
./hello-dotnet-macos-arm64 Привет
```

```text
hello-dotnet version v1.0.0
Hello from C#/.NET! 🚀
OS: darwin
Arch: arm64
Hello, GitHub!
Sum 1..10 = 55
Аргументы:
  1: Привет
```

Для запуска этих готовых файлов устанавливать Go, Python или .NET SDK не требуется. Python-бинарник содержит интерпретатор, .NET-бинарник — .NET Runtime.

</details>

<a id="skills"></a>

## 🛠️ Что реализовано

| Направление | Практика в проектах |
| --- | --- |
| **Автоматизация** | Workflow на YAML, события push и pull request, jobs, steps и зависимости между заданиями |
| **Качество кода** | Проверка форматирования, линтеры и статический анализ |
| **Тестирование** | Unit-тесты, матрицы версий Python и Node.js, отчёт покрытия Go |
| **Сборка** | Cargo, Maven, CMake, Go, PyInstaller и .NET CLI |
| **Контейнеризация** | Dockerfile, сборка образов и проверочный запуск контейнеров |
| **Артефакты** | Передача результатов между jobs, архивы Docker-образов и отчёты тестов |
| **Публикация образов** | GHCR, Docker Buildx, QEMU, теги latest и SHA, две Linux-архитектуры |
| **Выпуск программ** | Git-теги, версия в бинарнике, матричная сборка и GitHub Releases |

Локальные проверки выполнялись через Docker, в том числе на Mac с Apple Silicon. SDK и инструменты сборки запускались внутри контейнеров.

<a id="navigation"></a>

## 🔎 Как посмотреть результат

1. **Открыть репозиторий** — посмотреть исходники, тесты, Dockerfile и README проекта, если он есть.
2. **Перейти в Actions** — открыть workflow и логи форматирования, тестов, сборки или публикации.
3. **Проверить результат сборки** — выбрать подходящий раздел из таблицы ниже.

| Где искать | Что находится | Для каких проектов |
| --- | --- | --- |
| **Actions → запуск → Artifacts** | Архивы Docker-образов и отчёт покрытия | my-cpp-app, my-php-app, my-rust-app, my-go-app |
| **Packages / GHCR** | Опубликованные контейнерные образы | hello-go, hello-rust |
| **Releases** | Исполняемые файлы для нужной ОС и архитектуры | hello-go-bin, hello-python, hello-dotnet |

Общий каталог содержит ссылки на самостоятельные проекты. Для клонирования, проверки и сборки нужно выбрать конкретный репозиторий.

---

<div align="center">
<p><b>Даниил Абрамов</b> · <a href="https://github.com/Focsi4ek">Focsi4ek</a></p>
<p>Учебная практика: GitHub Actions · тесты · Docker · GHCR · Releases</p>
</div>

