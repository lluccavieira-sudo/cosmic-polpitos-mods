# 🛸 Cosmic Polpitos — Guia Oficial de Modding

Bem-vindo ao repositório oficial de modding do **Cosmic Polpitos** (desenvolvido por **Vieiras Games**)!  
Aqui você encontra tudo o que precisa para modificar a física da nave, alterar a gravidade de Polpostorinos, editar diálogos do Polpito e criar seus próprios scripts.

---


📁 Como Rodar um Mod

1. Baixe o arquivo oficial Cosmic Polpitos.json no repositório principal do jogo: github.com
2. Abra o GDevelop (no aplicativo ou pelo navegador em gdevelop.io) e carregue o arquivo Cosmic Polpitos.json.
3. Crie ou edite o seu arquivo mod.json com as novas configurações (como velocidade da nave, força de voo ou gravidade).
4. Nos eventos da cena Planeta 1, adicione a ação Convert JSON to a scene variable (ou global variable) para carregar o texto do seu JSON diretamente nas variáveis do jogo.

 
 A seguir temos alternativas diferentes
---

## 🛠️ Tutorial 1: Criando seu Primeiro Mod (`mod.json`)

Você não precisa saber programar! Crie um arquivo chamado `mod.json` dentro da pasta `mods/` usando o Bloco de Notas e cole o código abaixo:

```json
{
  "nomeDoMod": "Super Nave de Polpostorinos",
  "autor": "SeuNome",
  "versao": "1.0",
  "configuracoes": {
    "velocidadeNave": 1200,
    "forcaVoo": 900,
    "gravidadePlaneta": 4.5,
    "escalaNave": 1.3
  },
  "dialogos": {
    "polpitoInicio": "Olá explorador! Estamos voando com um mod customizado hoje!"
  }
}
```

### Tabela de Configurações

| Propriedade | Valor Padrão | O que altera no jogo |
| :--- | :---: | :--- |
| `velocidadeNave` | `500` | Velocidade máxima da nave andando no solo (`PhysicsCar3D`). |
| `forcaVoo` | `400` | Impulso e velocidade da nave voando (`PhysicsAirplane3D`). |
| `gravidadePlaneta` | `10` | Força da gravidade no *Planeta 1* (quanto menor, mais alto você salta). |
| `escalaNave` | `1` | Tamanho da nave (`2` dobra o tamanho, `0.5` deixa ela miniatura). |

---

## 💻 Tutorial 2: Mods Avançados com JavaScript (`mod.js`)

Se você sabe programar em JavaScript, pode manipular os objetos 3D da cena diretamente através da variável `runtimeScene` do motor GDevelop:

```javascript
// Exemplo: Transformar a nave em uma versão gigante ao iniciar o Planeta 1
const naves = runtimeScene.getObjects("Spaceship_Rae_The_Red_Panda");

if (naves.length > 0) {
  naves[0].setScale(2.0);
  console.log("[Mod] Nave Gigante ativada em Polpostorinos!");
}
```

---

## 🧬 Lista Oficial de Objetos do Jogo

Use estes nomes exatos nos seus scripts para encontrar os elementos da cena:

* `Astronaut_Rae_The_Red_Panda` — Personagem principal (visão em 1ª pessoa).
* `Spaceship_Rae_The_Red_Panda` — Nave espacial híbrida (terra e ar).
* `Rover_2` — Veículo terrestre experimental.
* `Terreno` — Solo rochoso onde a nave pousa.
* `Planeta 1` — Nome da cena principal do jogo.

---

## 🚀 Como Compartilhar Seu Mod

1. Crie um repositório no seu GitHub com o seu arquivo `mod.json` ou `mod.js`.
2. Abra uma **Issue** aqui neste repositório clicando na aba **Issues > New Issue**.
3. Coloque o nome do seu mod, o que ele faz e o link para o pessoal baixar!

---

*Mantido por **Vieiras Games** 🐙🚀*

