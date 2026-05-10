# DR_PLANILHAS

Fluxo básico no **branch `main`** com remoto **`origin`**:

## Enviar alterações (add → commit → push)

```bash
git add .
git commit -m "Descreva a alteração aqui"
git push origin main
git push -u origin main
```

Na primeira vez que você ligar este repositório ao remoto, use também:

```bash
git push -u origin main 
```

Depois disso, `git push origin main` (ou só `git push`, se o upstream já estiver configurado) costuma bastar.

## Configurar o remoto `origin` (se ainda não existir)

Substitua pela URL do seu repositório (HTTPS ou SSH):

```bash
git remote add origin https://github.com/USUARIO/REPOSITORIO.git
git branch -M main
git push -u origin main
```

## Windows: se o comando `git` não for reconhecido

O Git costuma ficar em `C:\Program Files\Git\cmd`. Adicione essa pasta ao **PATH** do sistema ou use o caminho completo:

```powershell
& "C:\Program Files\Git\cmd\git.exe" add .
& "C:\Program Files\Git\cmd\git.exe" commit -m "sua mensagem"
& "C:\Program Files\Git\cmd\git.exe" push origin main
```

## Identidade do Git (obrigatório para commit)

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

## Deploy na Vercel (HTML)

A Vercel **aceita HTML estático**; o que costuma confundir é que a URL raiz (`/`) procura **`index.html`**. Este projeto usa **`planilha-main.html`**, então há um **`vercel.json`** que redireciona internamente `/` para esse arquivo.

1. Conecte o repositório GitHub na Vercel e faça deploy do branch **`main`**.
2. Em **Framework Preset**, escolha **Other** (ou deixe em detecção automática; sem `package.json` costuma cair em site estático).
3. **Root Directory**: raiz do repo (`.`).
4. Não é obrigatório comando de build; os arquivos da raiz são publicados.

Depois do deploy, abra a URL do projeto: o dashboard deve abrir em `/`. Também funciona direto em `/planilha-main.html`.
