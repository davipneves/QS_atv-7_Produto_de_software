# Atividade 07 - Qualidade do Produto de Software


**Disciplina:** Qualidade de Software

**Aluno:** Davi Pereira Neves


### Git
Sistema de controle de versionamento distribuído, rápido e escalável. Cada cópia do repositório contém o histórico completo. O Git oferece comandos de alto nível (*porcelain*) e de baixo nível (*plumbing*).

### clone (`git-clone`)
Cria uma cópia de um repositório existente em um novo diretório. O comando:
1. cria uma *remote-tracking branch* para cada branch do repositório de origem;
2. registra o repositório de origem como remoto, por padrão com o nome `origin`;
3. faz *checkout* da branch inicial (normalmente a branch ativa do repositório de origem).

### commit (`gitglossary` e `git-commit`)
- **Substantivo:** objeto armazenado no banco de objetos que representa um *snapshot* (estado completo rastreado) do projeto. Contém referência ao(s) commit(s) pai, nome do autor, data e mensagem.
- Verbo (`git commit`): grava o conteúdo do *index* (área de preparação) no repositório como um novo commit.

### branch (`gitglossary` e `git-branch`)
Linha ativa de desenvolvimento. O commit mais recente de uma branch é sua ponta (*tip*). Tecnicamente, uma branch é uma referência (*ref*) que aponta para um commit. O comando `git branch` lista, cria ou remove branches.

### push (`git-push`)
Atualiza referências do repositório remoto usando as referências locais, enviando os objetos necessários para completá-las. Por padrão, só aceita atualizações *fast-forward* (em que o commit remoto é ancestral do commit local). Outras atualizações exigem `--force`.

### pull (`git-pull`)
Incorpora mudanças de um repositório remoto na branch atual. Equivale a executar `git fetch` seguido de `git merge` (ou `git rebase`, se configurado ou solicitado com `--rebase`).

### clean (`git-clean`)
Remove da *working tree* (árvore de trabalho) os arquivos **não rastreados** (*untracked*), a partir do diretório atual. Pontos relevantes:
- `-n` (*dry run*) mostra o que seria removido, sem remover;
- `-f` (*force*) é exigido por padrão (`clean.requireForce`);
- `-d` inclui diretórios não rastreados;
- arquivos ignorados pelo `.gitignore` só são removidos com `-x`;
- a remoção é irreversível, pois os arquivos não estão no banco de objetos.



### fork
Cópia de um repositório criada no servidor da plataforma, na conta do usuário, que mantém vínculo com o repositório original. Permite alterar o projeto sem ter permissão de escrita no original. Em termos de Git, é um clone do original publicado em outro repositório remoto, e o vínculo entre eles é metadado da plataforma.

### PR (*Pull Request*)
Solicitação, registrada na plataforma, para que os commits de uma branch (do mesmo repositório ou de um fork) sejam integrados a outra branch. Normalmente envolve revisão de código e discussão antes do *merge*. No GitLab o equivalente é o *Merge Request*. O comando relacionado do Git é `git request-pull` (`git-request-pull`), que apenas gera um texto resumindo as mudanças pendentes, para envio por e-mail.

## Resumo comparativo

| Termo | Origem | Opera sobre | Altera o repositório remoto? |
|---|---|---|---|
| clone | Git | Cria repositório local a partir do remoto | Não |
| commit | Git | Repositório local (a partir do *index*) | Não |
| branch | Git | Referências locais | Não |
| pull | Git | Branch local, com dados do remoto | Não |
| push | Git | Referências remotas | Sim |
| clean | Git | Working tree (arquivos não rastreados) | Não |
| fork | Plataforma | Repositório no servidor | Cria outro repositório remoto |
| PR | Plataforma | Solicitação de integração entre branches | Somente após o *merge* |