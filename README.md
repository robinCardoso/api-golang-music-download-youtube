# API Golang Music Download YouTube 🎵

API desenvolvida em **Go (Golang)** para realizar o **download e conversão de vídeos do YouTube** em **MP3** ou **MP4**, utilizando a ferramenta [yt-dlp](https://github.com/yt-dlp/yt-dlp).

---

## 🚀 Funcionalidades

- Buscar vídeos do YouTube por URL ou nome.
- Baixar vídeos em formato **MP3 (áudio)** ou **MP4 (vídeo)**.
- Utilizar cookies para downloads de vídeos privados ou restritos.
- Servir os downloads via **API REST**.
- Configuração simplificada com **Docker**.

---

## 📂 Estrutura do Projeto

```
.
├── cmd/            # Arquivo principal para inicialização da API
├── common/         # Utilitários e funções comuns
├── handlers/       # Handlers responsáveis pelas rotas da API
├── services/       # Serviços que implementam a lógica de download e conversão
├── utils/          # Funções auxiliares
├── Dockerfile      # Configuração para execução via Docker
├── cookies.txt     # Arquivo de cookies usado pelo yt-dlp (quando necessário)
├── go.mod          # Dependências Go
├── go.sum          # Hash das dependências Go
├── LICENSE         # Licença GPL-3.0
└── README.md       # Documentação
```

---

## ⚙️ Requisitos

Antes de executar a aplicação, instale as seguintes dependências:

- [Go 1.21+](https://go.dev/)
- [yt-dlp](https://github.com/yt-dlp/yt-dlp)
- [FFmpeg](https://ffmpeg.org/) (necessário para conversão de áudio/vídeo)

Verifique se estão disponíveis no **PATH**:

```bash
yt-dlp --version
ffmpeg -version
```

---

## ▶️ Como Executar

### 1. Clonar o Repositório

```bash
git clone https://github.com/marcosoleniuk/api-golang-music-download-youtube.git
cd api-golang-music-download-youtube
```

### 2. Instalar Dependências

```bash
go mod tidy
```

### 3. Rodar Localmente

```bash
go run cmd/main.go
```

A API estará disponível em:

```
http://localhost:8080
```

---

## 🐳 Executando com Docker

### 1. Build da Imagem

```bash
docker build -t youtube-music-api .
```

### 2. Rodar o Container

```bash
docker run -p 8080:8080 youtube-music-api
```

---

## 📡 Endpoints da API

### 🔹 `GET /download/mp3?url=YOUTUBE_URL`

Baixa o áudio (formato MP3) do vídeo informado.

Exemplo:

```bash
curl "http://localhost:8080/download/mp3?url=https://www.youtube.com/watch?v=dQw4w9WgXcQ" -o musica.mp3
```

### 🔹 `GET /download/mp4?url=YOUTUBE_URL`

Baixa o vídeo (formato MP4).

Exemplo:

```bash
curl "http://localhost:8080/download/mp4?url=https://www.youtube.com/watch?v=dQw4w9WgXcQ" -o video.mp4
```

---

## 🔐 Uso de Cookies

Para vídeos privados/restritos, adicione um arquivo `cookies.txt` na raiz do projeto.  
Esse arquivo pode ser exportado do navegador com extensões como [cookies.txt exporter](https://chrome.google.com/webstore/detail/njabckikapfpffapmjgojcnbfjonfjfg).

O `yt-dlp` usará automaticamente esse arquivo.

---

## 📜 Licença

Este projeto está sob a licença **GPL-3.0**.  
Você pode usar, modificar e distribuir, desde que mantenha os créditos e preserve a mesma licença.

---

## 🤝 Contribuições

Contribuições são bem-vindas!  
Sinta-se à vontade para abrir **issues** ou enviar **pull requests**.

---

## 🌟 Autor

Desenvolvido por [**Marcos Oleniuk**](https://github.com/marcosoleniuk) 🚀
