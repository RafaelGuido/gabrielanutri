# gabrielanutri.com

Site da consultoria nutricional de Gabriela Araújo Ribeiro (CRN-1/29679/P).
Site estático, sem build: HTML + CSS puro, hospedado no GitHub Pages.

## Estrutura

```
index.html        página única com todas as seções
css/style.css     estilos (paleta, tipografia, layout)
assets/           favicon e imagens
CNAME             domínio customizado do GitHub Pages
.nojekyll         desliga o processamento Jekyll do Pages
```

## Editar conteúdo

Todo o texto está em `index.html`, organizado por seção com comentários
(`<!-- ===== Planos ===== -->` etc.). Cores e fontes ficam no topo de
`css/style.css`, nas variáveis `:root`.

Para trocar o monograma provisório pelo logo real, salve o arquivo em
`assets/logo.png` (ou `.svg`) e substitua os blocos `<span class="mono">`
no `index.html` por `<img src="assets/logo.png" alt="Gabriela Araújo">`.

## Publicar (GitHub Pages)

1. Faça push da branch `main` para `github.com/RafaelGuido/gabrielanutri`.
2. No repositório: **Settings > Pages**.
   - Source: *Deploy from a branch*
   - Branch: `main` / pasta `/ (root)`
3. Em **Custom domain**, confirme `gabrielanutri.com` (o arquivo `CNAME`
   já está no repositório, então o campo deve vir preenchido).
4. Depois do DNS propagar, marque **Enforce HTTPS**.

## DNS (painel da Zoho)

Adicione apenas estes registros. Não altere MX, SPF (TXT) nem DKIM, que
são do e-mail.

| Tipo  | Nome | Valor                    |
|-------|------|--------------------------|
| A     | @    | 185.199.108.153          |
| A     | @    | 185.199.109.153          |
| A     | @    | 185.199.110.153          |
| A     | @    | 185.199.111.153          |
| CNAME | www  | rafaelguido.github.io    |

Se a Zoho tiver criado um registro A ou CNAME em `@` apontando para uma
página deles, substitua pelos A do GitHub acima.

## Testar localmente

Abra `index.html` direto no navegador, ou rode um servidor simples:

```
python -m http.server 8080
```

e acesse http://localhost:8080.
