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




---

# 🧭 Tipos de Commits e Operações no Git

## 🧱 Tipos principais de commits e quando usá-los

| Tipo de Commit | Comando principal | Cria novo commit? | Quando usar | Descrição |
|----------------|------------------|-------------------|--------------|------------|
| **Commit normal** | `git commit -m "mensagem"` | ✅ Sim | A cada mudança estável | Registra alterações no histórico local. |
| **Commit amend (edição)** | `git commit --amend` | 🆕 Substitui o último | Corrigir última mensagem ou incluir arquivo esquecido | Reescreve o último commit (muda o hash). Não use se já foi enviado. |
| **Merge commit** | `git merge nome-da-branch` | ✅ Sim (com `--no-ff`) | Quando integra uma branch na atual | Junta duas histórias. Cria commit especial de mesclagem. |
| **Fast-forward merge** | `git merge nome-da-branch` (sem `--no-ff`) | ❌ Não | Quando branch está linearmente à frente | Apenas move o ponteiro da branch. |
| **Rebase commit** | `git rebase nome-da-branch` | 🆕 Reescreve commits | Para manter histórico linear | Move commits para “cima” da nova base. |
| **Interactive rebase** | `git rebase -i HEAD~N` | ✅ (vários) | Para reordenar, juntar ou editar commits | Ferramenta poderosa para limpeza de histórico. |
| **Revert commit** | `git revert <hash>` | ✅ Sim | Para desfazer alteração já enviada | Cria novo commit que reverte outro — seguro em equipe. |
| **Cherry-pick commit** | `git cherry-pick <hash>` | ✅ Sim | Aplicar commit específico em outra branch | Copia commits isolados. Ideal para hotfixes. |
| **Squash commit** | `git rebase -i` (usando `squash`) | ✅ Sim | Para juntar vários commits pequenos | Une múltiplos commits em um só. |
| **Fixup commit** | `git commit --fixup <hash>` | ✅ Sim | Para corrigir commit anterior | Usado com `git rebase --autosquash`. |
| **Merge com conflito resolvido** | `git merge` → resolver → `git commit` | ✅ Sim | Quando há conflitos ao mesclar | Cria commit manual de merge. |
| **Rebase com conflito resolvido** | `git rebase` → resolver → `git rebase --continue` | ✅ Sim | Para completar rebase interrompido | Reaplica commits após resolver conflitos. |
| **Tag (referência)** | `git tag -a v1.0 -m "Release 1.0"` | ❌ Não | Para marcar versões (releases) | Tag aponta para um commit existente. |
| **Merge revert** | `git revert -m 1 <hash-merge>` | ✅ Sim | Para desfazer merge específico | Reverte o commit de merge mantendo histórico. |

---

## 🧩 Ações relacionadas (não criam novos commits)

| Comando | Efeito | Quando usar |
|----------|---------|-------------|
| `git reset --soft HEAD~1` | Desfaz último commit, mantendo alterações | Para editar mensagem ou refazer commit. |
| `git reset --mixed HEAD~1` | Desfaz commit, mantém arquivos alterados | Para re-adicionar seletivamente. |
| `git reset --hard HEAD~1` | Apaga commit e alterações | ⚠️ Destrutivo — use com cuidado. |
| `git stash` / `git stash pop` | Guarda e restaura alterações não commitadas | Ideal pra trocar de branch sem perder progresso. |

---

## 🧠 Fluxo prático corporativo comum

```bash
git checkout -b feature/nova-funcionalidade
git add .
git commit -m "feat: adiciona tela de login"
git commit -m "fix: corrige validação de senha"
git rebase -i HEAD~2
git fetch origin
git rebase origin/main
git rebase --continue
git push -u origin feature/nova-funcionalidade
```

---

## 🏁 Resumo visual

```
commit normal          → git commit -m
commit amend           → git commit --amend
merge commit           → git merge --no-ff
rebase (linear)        → git rebase main
revert commit          → git revert <hash>
cherry-pick commit     → git cherry-pick <hash>
fixup/squash           → git rebase -i
reset commit           → git reset --soft / --hard
```

