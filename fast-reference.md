# **Guia Rápido de Git**

---

## **Estados dos arquivos**

- **Modificado (modified):** Alterações feitas no working directory.
- **Preparado (staged/index):** Arquivos adicionados à staging area (`git add`).
- **Consolidado (committed):** Alterações registradas no repositório local (`git commit`).

---

## **Ajuda**

- **Geral:** `git help`
- **Comando específico:** `git help <comando>`
- **Exemplo:** `git help add` ou `git help commit`

---

## **Configuração**

As configurações do Git ficam em `~/.gitconfig` (Linux/macOS) ou `C:\Users\<usuário>\.gitconfig` (Windows).

<pre class="overflow-visible!" data-start="795" data-end="1242"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span># Configurar usuário</span><span>
git config --global user.name </span><span>"Leonardo Comelli"</span><span>

</span><span># Configurar e-mail</span><span>
git config --global user.email leonardo@software-ltda.com.br

</span><span># Configurar editor padrão</span><span>
git config --global core.editor vim

</span><span># Configurar ferramenta de merge</span><span>
git config --global merge.tool vimdiff

</span><span># Configurar arquivo global de exclusão (.gitignore)</span><span>
git config --global core.excludesfile ~/.gitignore

</span><span># Listar configurações</span><span>
git config --list
</span></span></code></div></div></pre>

---

## **Ignorar arquivos**

- **Global:** arquivos ignorados em todos os repositórios (`core.excludesfile`).
- **Por repositório:** arquivo `.gitignore` no diretório do projeto.

---

## **Repositório local**

### Criar e gerenciar

<pre class="overflow-visible!" data-start="1488" data-end="1577"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span># Criar novo repositório</span><span>
git init

</span><span># Verificar status dos arquivos</span><span>
git status
</span></span></code></div></div></pre>

### Adicionar arquivos

<pre class="overflow-visible!" data-start="1602" data-end="1841"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git add arquivo.txt       </span><span># adicionar arquivo específico</span><span>
git add diretorio/        </span><span># adicionar diretório</span><span>
git add .                 </span><span># adicionar todos os arquivos</span><span>
git add -f arquivo.txt    </span><span># forçar adicionar arquivo do .gitignore</span><span>
</span></span></code></div></div></pre>

### Commit

<pre class="overflow-visible!" data-start="1854" data-end="2028"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git commit arquivo.txt -m </span><span>"mensagem do commit"</span><span></span><span># commit de um arquivo</span><span>
git commit -m </span><span>"mensagem"</span><span></span><span># commit de todos arquivos staged</span><span>
</span></span></code></div></div></pre>

### Remover arquivos

<pre class="overflow-visible!" data-start="2051" data-end="2102"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git </span><span>rm</span><span> arquivo.txt
git </span><span>rm</span><span> -r diretorio/
</span></span></code></div></div></pre>

---

## **Histórico**

<pre class="overflow-visible!" data-start="2130" data-end="2740"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git </span><span>log</span><span></span><span># histórico completo</span><span>
git </span><span>log</span><span> -p -2                       </span><span># últimos 2 commits com diff</span><span>
git </span><span>log</span><span> --</span><span>stat</span><span></span><span># resumo de commits (+/-)</span><span>
git </span><span>log</span><span> --pretty=oneline             </span><span># hash completo + comentário</span><span>
git </span><span>log</span><span> --pretty=format:</span><span>"%h - %an, %ar : %s"</span><span></span><span># formatação customizada</span><span>
git </span><span>log</span><span> -- <arquivo>                 </span><span># histórico de um arquivo</span><span>
git </span><span>log</span><span> --diff-filter=M -- <arquivo> </span><span># histórico de modificações de um arquivo</span><span>
git blame -L 12,22 arquivo.txt       </span><span># autor e linha modificada</span><span>
git </span><span>log</span><span> --author=usuario             </span><span># histórico de um autor específico</span><span>
</span></span></code></div></div></pre>

---

## **Desfazendo alterações**

<pre class="overflow-visible!" data-start="2780" data-end="2944"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span># Alterações locais (NÃO adicionadas à staging)</span><span>
git checkout -- arquivo.txt

</span><span># Alterações na staging</span><span>
git reset HEAD arquivo.txt
git checkout arquivo.txt
</span></span></code></div></div></pre>

---

## **Repositório remoto**

<pre class="overflow-visible!" data-start="2981" data-end="3273"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span># Listar repositórios remotos</span><span>
git remote -v

</span><span># Vincular repositório local</span><span>
git remote add origin git@github.com:usuario/repositorio.git

</span><span># Exibir informações de remoto</span><span>
git remote show origin

</span><span># Renomear remoto</span><span>
git remote rename origin novo-nome

</span><span># Remover remoto</span><span>
git remote </span><span>rm</span><span> nome
</span></span></code></div></div></pre>

### Enviar e atualizar

<pre class="overflow-visible!" data-start="3298" data-end="3602"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git push -u origin master      </span><span># primeiro push</span><span>
git push                        </span><span># pushes subsequentes</span><span>
git pull                        </span><span># atualizar repositório local</span><span>
git fetch                       </span><span># baixar alterações sem aplicar</span><span>
git </span><span>clone</span><span> git@github.com:usuario/repositorio.git  </span><span># clonar remoto</span><span>
</span></span></code></div></div></pre>

---

## **Tags**

<pre class="overflow-visible!" data-start="3625" data-end="3959"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git tag vs-1.1                  </span><span># tag leve</span><span>
git tag -a vs-1.1 -m </span><span>"mensagem"</span><span></span><span># tag anotada</span><span>
git tag -s vs-1.1 -m </span><span>"mensagem"</span><span></span><span># tag assinada (GPG)</span><span>
git tag -a vs-1.2 <</span><span>hash</span><span>>        </span><span># criar tag a partir de commit</span><span>
git push origin vs-1.2           </span><span># enviar tag para remoto</span><span>
git push origin --tags           </span><span># enviar todas tags locais</span><span>
</span></span></code></div></div></pre>

---

## **Branches**

- `master/main`: branch principal
- `HEAD`: ponteiro para o branch atual

<pre class="overflow-visible!" data-start="4063" data-end="4817"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git branch                      </span><span># listar branches</span><span>
git branch -v                   </span><span># listar com últimos commits</span><span>
git branch --merged             </span><span># branches já mergeados</span><span>
git branch --no-merged          </span><span># branches não mergeados</span><span>

</span><span># Criar branch</span><span>
git branch bug-123
git checkout bug-123           </span><span># trocar de branch</span><span>
git checkout -b bug-456        </span><span># criar e trocar</span><span>

</span><span># Voltar ao master/main</span><span>
git checkout master

</span><span># Merge</span><span>
git merge bug-123
</span><span># Resolver conflitos manuais se necessário</span><span>

</span><span># Apagar branch local</span><span>
git branch -d bug-123

</span><span># Branch remoto</span><span>
git push origin bug-123          </span><span># criar branch remoto</span><span>
git push origin bug-123:new-branch
git checkout -b bug-123 origin/bug-123  </span><span># baixar branch remoto</span><span>
git push origin :bug-123         </span><span># apagar branch remoto</span><span>
</span></span></code></div></div></pre>

---

## **Rebasing**

<pre class="overflow-visible!" data-start="4843" data-end="5124"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git checkout experiment
git rebase master               </span><span># aplica mudanças de master no branch</span><span>
git rebase -i HEAD~3            </span><span># reescrever últimos 3 commits</span><span>
git commit --amend -m </span><span>"Nova msg"</span><span></span><span># alterar mensagem do commit</span><span>
git rebase --</span><span>continue</span><span></span><span># continuar rebase</span><span>
</span></span></code></div></div></pre>

---

## **Stash**

<pre class="overflow-visible!" data-start="5147" data-end="5436"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git stash                        </span><span># criar stash</span><span>
git stash list                   </span><span># listar stashes</span><span>
git stash apply                  </span><span># aplicar último stash</span><span>
git stash apply stash@{2}       </span><span># aplicar stash específico</span><span>
git stash branch meu_branch      </span><span># criar branch a partir do stash</span><span>
</span></span></code></div></div></pre>

---

## **Bisect (debug de commits)**

<pre class="overflow-visible!" data-start="5479" data-end="5680"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>git bisect start
git bisect bad                  </span><span># commit com bug</span><span>
git bisect good <tag/commit>    </span><span># commit bom</span><span>
</span><span># Git navega pelos commits</span><span>
git bisect reset                 </span><span># finalizar bisect</span></span></code></div></div></pre>

**Tip**: Este guia é uma referência enxuta, mas cobre **todas as operações básicas e avançadas** que provavelmente vai usar em projetos acadêmicos  ou  pessoais.
