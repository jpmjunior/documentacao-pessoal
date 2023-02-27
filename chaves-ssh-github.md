# Configurando chaves SSH para autenticação no GitHub

O GitHub está usando agora uma autenticação criptografada por um par de chaves, uma chave pública que você pode compartilhar e uma chave secreta, que somente você deve ter acesso.

Seguem os passo para você gerar as chaves e cadastrar no GitHub, é importante que você use o Git Bash para executar os comandos, caso esteja usando o Windows.

- Criando o par de chaves, recomenda-se usar o mesmo e-mail cadastrado no GitHub. Ao executar, serão feitas duas perguntas, a primeira é sobre o diretório onde se deseja armazenar as chaves, apenas aperte enter para manter o padrão. A segunda pergunta é sobre a proteção da sua chave privada com uma senha, que também é opcional, mas é ideal que você crie uma senha para maior segurança. Caso configure a senha, ela será solicitada toda vez que a chave for usada:
```bash
ssh-keygen -t ed25519 -C seu@email.com
```
- Verifique se no diretório do SSH se as chaves foram criadas:
```bash
ls $HOME/.ssh
```
- Você deverá ver dois arquivos, o id_ed25519 é sua chave privada e o id_ed25519.pub é sua chave pública:

![download](https://user-images.githubusercontent.com/15961779/221672337-38fbe7d2-ba89-48a8-8cb1-bad5202d3a98.png)

- Inicie o ssh-agent:
```bash
eval $(ssh-agent -s)
```
- Informe sua chave privada ao ssh-agent:
```bash
ssh-add $HOME/.ssh/id_ed25519
```
- Agora você terá que informar sua chave pública ao GitHub, para exibir digite:
```bash
cat $HOME/.ssh/id_ed25519.pub
```
- Copie o resultado do comando anterior na seção `SSH e GPG Keys` das configurações do seu GitHub, clique em `New SSH Key`:

![download](https://user-images.githubusercontent.com/15961779/221672629-2152c2e1-2c55-40b1-b225-76c56847c2e1.png)

- Copie sua chave pública no campo `Key`, no campo `Key type` pode deixa como na imagem e em `Title` você pode criar, como exemplo "Meu Notebook"

Pronto agora você deve estar apto a se autenticar usando suas chaves criptográficas, para testar pode usar o seguinte comando:

```bash
ssh -T git@github.com
```
Você deverá obter uma resposta semelhante a esta:

![download](https://user-images.githubusercontent.com/15961779/221673139-705a8aba-afac-4536-95ef-84168746b497.png)

