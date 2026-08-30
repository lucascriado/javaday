# javaday

Página do evento **Java Day Noroeste**. Site estático de uma página só.

- **Repositório:** `git@github.com:lucascriado/javaday.git` (público)
- **Produção:** <https://javaday.vercel.app>
- **Local:** `C:\www\javaday`

## Stack

HTML puro, sem build e sem `package.json`. Só dois itens na raiz:

```
index.html
assets/
```

O CSS vem do **Tailwind pelo CDN** (`cdn.tailwindcss.com`, com os plugins
`forms` e `container-queries`), e as fontes do Google Fonts — **Fustat**,
**JetBrains Mono** e **Material Symbols Outlined**.

Para trabalhar nele basta abrir o `index.html` no navegador; não há servidor de
desenvolvimento nem etapa de build.

## Deploy

**Este é o único projeto que não roda na VPS.** Ele está na Vercel, ligado ao
repositório do GitHub — push na `main` publica.

Não existe aplicação correspondente no Coolify. Se um dia for trazido para a
VPS, é o caso mais simples do conjunto: um `Dockerfile` com `nginx:alpine`
copiando a raiz resolve, porque não há build. Faltaria decidir o domínio — um
subdomínio de `lucascriado.com` já resolve pelo curinga do DNS.

## Cuidado

O Tailwind por CDN **não é recomendado para produção** — ele compila as classes
no navegador a cada visita, o que custa alguns décimos de segundo no primeiro
paint e depende de o CDN estar no ar. Para uma página de evento com tráfego
concentrado em poucos dias, é uma troca aceitável; se o site ganhar vida longa,
vale gerar o CSS num build.
