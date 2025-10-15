# 🧰 Git Cheatsheet Corporativo

## ⚙️ Configuração Inicial
| Comando | Descrição |
|----------|------------|
| `git config --global user.name "Seu Nome"` | Define o nome do autor dos commits. |
| `git config --global user.email "email@empresa.com"` | Define o email do autor dos commits. |
| `git config --list` | Mostra as configurações atuais. |
| `git config --global color.ui auto` | Habilita cores no terminal. |

---

## 📦 Inicialização e Clonagem
| Comando | Descrição |
|----------|------------|
| `git init` | Cria um repositório local. |
| `git clone <url>` | Clona um repositório remoto. |
| `git clone --branch <nome>` | Clona uma branch específica. |
| `git clone --depth 1` | Clona apenas o último commit. |

---

## 🧱 Status e Histórico
| Comando | Descrição |
|----------|------------|
| `git status` | Mostra o estado atual dos arquivos. |
| `git log` | Mostra o histórico de commits. |
| `git log --oneline --graph --decorate --all` | Mostra o histórico resumido e visual. |
| `git show <hash>` | Exibe detalhes de um commit específico. |

---

## ✏️ Adicionando e Commitando
| Comando | Descrição |
|----------|------------|
| `git add .` | Adiciona todas as mudanças. |
| `git add -p` | Adiciona mudanças por pedaço. |
| `git commit -m "mensagem"` | Cria um novo commit. |
| `git commit -a -m "mensagem"` | Adiciona e commita arquivos rastreados. |
| `git commit --amend` | Edita o último commit. |

---

## 🌿 Branches
| Comando | Descrição |
|----------|------------|
| `git branch` | Lista branches locais. |
| `git branch -a` | Lista todas (locais e remotas). |
| `git branch nome` | Cria uma nova branch. |
| `git branch -d nome` | Deleta uma branch. |
| `git switch nome` | Troca de branch. |
| `git switch -c nome` | Cria e muda para nova branch. |

---

## 🔄 Merge e Rebase
| Comando | Descrição |
|----------|------------|
| `git merge nome-branch` | Mescla branch com a atual. |
| `git merge --no-ff nome-branch` | Força commit de merge (mantém histórico). |
| `git rebase main` | Rebase na branch principal. |
| `git rebase -i HEAD~3` | Rebase interativo dos últimos 3 commits. |

---

## ☁️ Repositórios Remotos
| Comando | Descrição |
|----------|------------|
| `git remote -v` | Mostra os repositórios remotos. |
| `git remote add origin <url>` | Adiciona remoto. |
| `git pull` | Atualiza o branch atual. |
| `git pull --rebase` | Atualiza mantendo histórico linear. |
| `git push -u origin main` | Envia commits para o repositório remoto. |
| `git push --force-with-lease` | Força envio com segurança. |

---

## 🧹 Limpeza e Revisão
| Comando | Descrição |
|----------|------------|
| `git diff` | Mostra diferenças não commitadas. |
| `git stash` | Guarda alterações temporariamente. |
| `git stash pop` | Restaura alterações guardadas. |
| `git clean -fd` | Remove arquivos não rastreados. |

---

## 🏷️ Tags e Releases
| Comando | Descrição |
|----------|------------|
| `git tag v1.0` | Cria uma tag simples. |
| `git tag -a v1.0 -m "Versão 1.0"` | Cria tag anotada. |
| `git push origin --tags` | Envia tags ao remoto. |

---

## 🩹 Desfazer e Recuperar
| Comando | Descrição |
|----------|------------|
| `git reset arquivo.txt` | Remove da staging area. |
| `git reset --soft HEAD~1` | Desfaz commit, mantendo alterações. |
| `git reset --hard HEAD~1` | Desfaz commit e apaga alterações. ⚠️ |
| `git revert <hash>` | Reverte um commit de forma segura. |

---

## 🕵️ Extras Corporativos
| Comando | Descrição |
|----------|------------|
| `git blame arquivo.txt` | Mostra quem alterou cada linha. |
| `git cherry-pick <hash>` | Aplica commit específico de outra branch. |
| `git shortlog -sn` | Mostra ranking de commits por autor. |
| `git bisect start` | Ajuda a encontrar commit que introduziu bug. |

---

## 💡 Aliases Úteis
| Comando | Descrição |
|----------|------------|
| `git config --global alias.st status` | Atalho para `git status`. |
| `git config --global alias.co checkout` | Atalho para `git checkout`. |
| `git config --global alias.br branch` | Atalho para `git branch`. |
| `git config --global alias.cm "commit -m"` | Atalho para `git commit -m`. |
| `git config --global alias.lg "log --oneline --graph --decorate --all"` | Histórico resumido e visual. |
