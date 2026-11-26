#  Despertador Anti-Soneca com QR Code

Um despertador feito em Python para quem tem dificuldade de acordar depois de um dia cansativo, aperta a soneca, volta a dormir e acaba perdendo compromissos.

A ideia é simples: **o alarme só desliga quando você escaneia um QR Code**, e esse QR Code fica em outro cômodo da casa (na geladeira, no banheiro ou na mesa da cozinha). Para parar o barulho, você precisa levantar da cama e andar até lá. Quando chega, o sono já foi embora.

##  Como funciona

1. O alarme toca em **tela cheia**, com som, no horário definido.
2. Não existe botão de soneca e nem senha para desligar.
3. Você pega o celular, vai até o local onde o QR Code está colado e aponta a câmera para ele.
4. O sistema lê o QR Code pela câmera do celular, valida o conteúdo e, só então, o alarme para.

##  Tecnologias utilizadas

| Tecnologia | Para que serve |
|---|---|
| **Python** | Linguagem principal do projeto |
| **Tkinter** | Interface do alarme em tela cheia |
| **Pygame** | Reprodução do som do alarme |
| **OpenCV** | Leitura e decodificação do QR Code |
| **IP Webcam (app Android)** | Usa a câmera do celular como câmera do PC |
| **qrcode** | Geração do QR Code (`gerar_qr.py`) |

##  Estrutura do projeto

```
despertador-qr/
├── despertador.py     # Programa principal (alarme + leitura do QR Code)
├── gerar_qr.py        # Gera a imagem do QR Code para imprimir
├── alarme.mp3         # Som do alarme (use o seu preferido)
└── README.md
```



##  Como usar

### 1. Pré-requisitos

- Python 3.14.7 
- Um celular Android com o app **IP Webcam ou Droidcam** instalado
- PC e celular conectados na **mesma rede Wi-Fi**

### 2. Instalação

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/despertador-qr.git
cd despertador-qr

# Instale as dependências
pip install pygame opencv-python qrcode[pil]
```


### 3. Gere o QR Code

```bash
py gerar_qr.py
```

Isso cria a imagem do QR Code. **Imprima e cole em outro cômodo**, o mais longe possível da cama.

### 4. Configure a câmera do celular

1. Abra o app **IP Webcam ou droidcam** no celular e toque em *Iniciar servidor*.
2. Anote o endereço IP que aparece na tela (algo como `http://192.168.0.10:8080`).
3. Coloque esse endereço na configuração do `despertador.py`.

### 5. Rode o despertador

```bash
py despertador.py
```

Defina o horário, deixe o celular com o IP Webcam ativo e vá dormir. Pela manhã, o alarme só vai parar quando você escanear o QR Code, de preferência em outro cômodo. 

##  Ideias para o futuro

- [ ] Desafios lógicos como alternativa ao QR Code (ex.: resolver contas de matemática)
- [ ] Interface para escolher o horário sem mexer no código
- [ ] Volume do alarme aumentando aos poucos
- [ ] Versão rodando direto no celular

##  Contribuições

Sugestões e melhorias são bem-vindas! Abra uma *issue* ou envie um *pull request*.

##  Sobre o projeto

Projeto pessoal desenvolvido com ajuda do **Google Gemini**, durante meus estudos de Análise e Desenvolvimento de Sistemas, para resolver um problema real: o hábito de apertar a soneca e perder o horário.

