# financas-pwa

PWA de controle pessoal de dívidas e reserva financeira, em um único `index.html`, sem backend.

![HTML5](https://img.shields.io/badge/-HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/-CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?logo=javascript&logoColor=black)
![PWA](https://img.shields.io/badge/-PWA-5A0FC8?logo=pwa&logoColor=white)
![Google Fonts](https://img.shields.io/badge/-Google%20Fonts-4285F4?logo=googlefonts&logoColor=white)

## Sobre

Ferramenta pessoal para acompanhar parcelas, gastos fixos e a reserva até o próximo salário. Os dados ficam só no navegador (`localStorage`); nada é enviado a servidor. Projeto em uso pelo autor, sem demo publicada.

## Funcionalidades

- Seis abas: Resumo, Plano, Dívidas, Fixos, Projeção e Dados.
- Resumo: compromissos por mês, vencimentos dos próximos 30 dias e simulador.
- Plano: saldo até o próximo salário, lista "o que fazer", presets (dia de pagamento e valor extra) e tabela mês a mês.
- Cadastro de dívidas parceladas e de gastos fixos recorrentes.
- Gráficos em canvas do quanto falta pagar e da reserva no fim de cada mês.
- Backup: copiar JSON, baixar `.json`, aplicar JSON colado e voltar aos dados iniciais.
- Instalável e offline após a primeira visita.

## Stack

| Tecnologia | Para que serve aqui |
|---|---|
| HTML, CSS e JavaScript puro | Interface e lógica inteiras, sem framework nem build |
| Canvas | Gráficos de projeção |
| localStorage | Persistência dos dados no dispositivo |
| Service Worker (`sw.js`) | Funcionamento offline (rede primeiro, cache como reserva) |
| Web App Manifest | Instalação como app |
| Google Fonts (IBM Plex) | Tipografia |

## Como rodar

Sem dependências. O service worker exige `localhost` ou HTTPS, então sirva a pasta:

```bash
python -m http.server 8000
# acesse http://localhost:8000
```

### Dados iniciais (`seed.private.js`)

O `index.html` carrega um `seed.private.js` (define `window.SEED_PRIVADO`) com os dados pessoais do autor. Esse arquivo não está no repositório, por conter dados privados. Sem ele o app inicia vazio: cadastre seus dados ou importe um backup JSON na aba Dados.

## Estrutura

```
index.html              app completo (HTML, CSS e JS)
sw.js                   service worker
manifest.webmanifest    metadados do PWA
icon-*.png              ícones
```

## Status

Uso pessoal, em evolução, sem testes automatizados.
