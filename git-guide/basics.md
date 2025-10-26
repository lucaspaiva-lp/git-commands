## 🔧 Configuração

git config --global user.name "Seu Nome" — define seu nome para commits.

git config --global user.email seu-email@exemplo.com — define seu email para os commits.

git config --list — mostra todas as configurações ativas.

## 📂 Inicialização / Clonagem

git init — inicializa um novo repositório local.

git clone <url-do-repositório> — clona um repositório remoto para local.

## 📋 Estado / Snapshot

git status — mostra o estado dos arquivos (modificados, staged etc).

git add <arquivo> — adiciona um arquivo específico à staging area.

git add . — adiciona todos os arquivos modificados à staging area.

git commit -m "mensagem" — grava as alterações preparadas como um commit.

## 🌿 Branches

git branch — lista as branches locais.

git branch <nome-da-branch> — cria uma nova branch.

git checkout <nome-da-branch> — muda para a branch especificada.

git checkout -b <nome-da-branch> — cria uma nova branch e já muda para ela.

git merge <nome-da-branch> — une a branch especificada com a branch atual.

## 🔁 Remoto e sincronização

git remote -v — exibe os repositórios remotos configurados (nome + URL).

git push origin <nome-da-branch> — envia seus commits para o repositório remoto.

git pull — puxa as últimas alterações do remoto para sua branch atual.

## 🕵️ Histórico / Log

git log — mostra o histórico de commits.

git log --oneline — mostra resumo curto do histórico (uma linha por commit).

git diff — mostra diferenças entre arquivos modificados e a última versão commitada.