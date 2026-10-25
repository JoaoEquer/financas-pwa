# financas-pwa

App web progressivo (PWA) de controle pessoal de dívidas e reserva financeira, em um único `index.html`, sem backend e sem dados embutidos.

## Funcionalidades

O app tem seis abas (Resumo, Plano, Dívidas, Fixos, Projeção e Dados):

- **Resumo:** compromissos por mês, vencimentos dos próximos 30 dias e um simulador.
- **Plano:** saldo até o próximo salário, lista "o que fazer", premissas, presets de plano (dia de pagamento e valor extra) e tabela mês a mês.
- **Dívidas / Fixos:** cadastro de dívidas parceladas e de gastos fixos recorrentes.
- **Projeção:** gráficos (canvas) de quanto falta pagar e da reserva no fim de cada mês.
- **Dados:** backup e restauração. Copiar JSON, baixar `.json`, aplicar um JSON colado e voltar aos dados iniciais.
- Funciona offline após a primeira visita (service worker) e pode ser instalado como app (`manifest.webmanifest`).
- Os dados ficam no `localStorage` do navegador. Nada é enviado a servidor.

## Tecnologias

HTML, CSS e JavaScript puro (sem frameworks nem build), Service Worker, Web App Manifest, fonte IBM Plex via Google Fonts.

## Como rodar

Não há dependências. O service worker exige `http://localhost` ou HTTPS, então sirva a pasta por um servidor local em vez de abrir o arquivo direto:

```
python -m http.server 8000
```

Depois acesse `http://localhost:8000`. Abrir `index.html` direto também mostra a interface, mas sem service worker.

### Dados iniciais

O `index.html` carrega opcionalmente um `seed.private.js` (que define `window.SEED_PRIVADO`) com dados pessoais. Esse arquivo **não faz parte do repositório**. Sem ele, o app inicia vazio e você cadastra seus dados ou importa um backup JSON.

## Estrutura

```
index.html              app completo (HTML, CSS e JS)
sw.js                   service worker (rede primeiro, cache como reserva)
manifest.webmanifest    metadados do PWA
icon-*.png              ícones do app
```

## Status

Projeto pessoal em uso e evolução, sem testes automatizados. Não há demo publicada.