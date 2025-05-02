# Instruções para Deploy no GitHub Pages

Este documento explica como fazer o deploy do site da Titan Engenharia & Soluções Ambientais no GitHub Pages.

## Resumo dos Arquivos Importantes

- `index.html` - Arquivo principal que carrega a aplicação React
- `.nojekyll` - Arquivo vazio que impede o processamento Jekyll do GitHub
- `404.html` - Página de erro que redireciona para a página principal
- `public/` - Pasta com arquivos estáticos necessários para o GitHub Pages
- `CNAME` - Arquivo que configura o domínio personalizado (se houver)

## Passos para Deploy Manual

1. Faça o download do código do Replit (botão "Download as zip")
2. Extraia o arquivo zip em uma pasta local
3. Instale o Git em sua máquina local (se ainda não tiver)
4. Crie um novo repositório no GitHub chamado `seu-usuario.github.io`
5. Clone o repositório para sua máquina local:
   ```
   git clone https://github.com/seu-usuario/seu-usuario.github.io.git
   ```
6. Copie todos os arquivos para a pasta do repositório clonado
7. Adicione os arquivos, faça commit e push:
   ```
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

O GitHub Pages detectará automaticamente seu repositório e o publicará em `https://seu-usuario.github.io`.

## Configurando o Domínio Personalizado (Opcional)

1. Edite o arquivo `CNAME` para conter seu domínio personalizado 
   (ex: `www.titan-engenharia.com`)
2. No painel de controle do seu provedor de DNS:
   - Adicione um registro A apontando para os IPs do GitHub Pages:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Adicione um registro CNAME de `www` apontando para `seu-usuario.github.io`
3. No GitHub, vá para Settings > Pages e configure seu domínio personalizado

## Dicas para Resolução de Problemas

1. **Erro 404**: Se seu site mostra erro 404, verifique se os arquivos `.nojekyll` e `404.html` estão na raiz do repositório.

2. **Redirecionamento não funciona**: Certifique-se de que o arquivo `index.html` na raiz tem o script de redirecionamento correto.

3. **Imagens não aparecem**: Verifique se os caminhos das imagens são relativos e não absolutos.

4. **Links quebrados**: Se os links internos não funcionam, certifique-se de que estão usando o roteamento correto para SPAs.

5. **Cache do navegador**: Sempre tente limpar o cache do navegador ao testar mudanças.

## Como Testar Localmente

Para testar o site localmente antes de fazer o deploy:

1. Instale o http-server:
   ```
   npm install -g http-server
   ```

2. Navegue até a pasta do projeto e execute:
   ```
   http-server
   ```

3. Acesse `http://localhost:8080` no seu navegador

## Recomendações Adicionais

- Sempre teste o site localmente antes de fazer o deploy
- Use um navegador em modo anônimo para testar sem interferência de cache
- Adicione Google Analytics para acompanhar visitas ao site
- Configure HTTPS no GitHub Pages para maior segurança
- Mantenha o arquivo CNAME atualizado com seu domínio personalizado