# Frontend - GoGym

Este é o frontend do projeto GoGym, uma aplicação para gerenciamento de treinos, competição entre usuários e acompanhamento de desempenho.
O projeto foi desenvolvido em React Native e se comunica com o backend via API.

## Instalação

Antes de tudo, garanta que você tenha instalado:

Node.js

npm ou yarn

Expo CLI (para rodar o app)

Um emulador Android/iOS ou o app Expo Go no seu celular

1. Entrar na pasta do projeto

       cd frontend

2. Instalar as dependências

        npm install

ou, se preferir:

        npm i

## Integração com o Backend

Para que o frontend consiga se comunicar com o backend, é necessário configurar o endereço IP da sua máquina local.

Passos:

No terminal, execute:

      hostname -I

Copie o endereço IPv4 retornado (ex: 192.168.1.9).

Abra o arquivo:

src/service/app.ts

Localize a variável que define o endereço base da API (geralmente baseURL ou similar) e substitua o IP atual pelo seu IPv4 local.
Exemplo:

export const api = axios.create({
  baseURL: 'http://192.168.1.9:8000',
});

<hr>

# Executando o Projeto

Com tudo configurado, basta iniciar o servidor de desenvolvimento:

      npx expo start
ou

    npm run start

Após isso:

Se estiver com o Expo Go instalado no celular, escaneie o QR Code que aparece no terminal ou na interface web.

Se estiver usando um emulador Android, pressione a para abrir o app.

Para iOS, pressione i (em macOS com Xcode configurado).

<hr>

### Dica

Se estiver executando o backend com o comando:

    php artisan serve --host=0.0.0.0 --port=8000
    
e ambos os dispositivos (PC e celular) estiverem na mesma rede Wi-Fi, o app conseguirá se conectar normalmente ao backend usando o IP configurado.

