# M7-P2 - AWS

## Banco de dados

1. Dentro do RDS selecionei para criar uma nova base de dados - Botão grande e laranja no extermo direito
2. Selecioneio na tela de criação, comeicei selecionando o tipo do banco, no caso foi "Postgres"

   ![1696010129128](image/README/1696010129128.png)
3. Escolhi a opção free tier já que é só para a prova

   ![1696010154599](image/README/1696010154599.png)
4. Em settings, escolhi o nome do banco na aws `m7-p2-pratica` (e não o nome do database, dexei o por padrão mesmo), o acesso de usuario como username = `admin123` e a password= `admin123`

   ![1696010264842](image/README/1696010264842.png)
5. Marco a opção de acesso publico e crio um novo security group para o banco com o nome `sg-m7-p2`
   ![1696010482589](image/README/1696010482589.png)
6. As demais configurações deixo por padrão, já que não preciso altear muito por ser uma aplicação menor e clico em criar.

   ![1696010662471](image/README/1696010662471.png)
7. Por ultimo, no grupo de segurança, nas regras de entrada, eu retiro o ip da minha maquina, que por padrão a aws cria, ele não funciona que o ip de rede do inteli é dinamico.

   ![1696010869042](image/README/1696010869042.png)

   ![1696010909951](image/README/1696010909951.png)
8. Depois de criar, rodei a arquivo `criar_banco.py`, passando as credenciais de conexão:
   ![1696011189580](image/README/1696011189580.png)

## EC2 Front-end
1. Já na pagina de criação de EC2, ja começo configurando o nome `m7-p2-frontend` e tipo da imagem instancia `ubuntu`
   ![1696011502093](image/README/1696011502093.png)
3. Seleciono o tipo da instancia `t3.micro`, já que vou rodar uma imagem container posteriormente.
   ![1696011639241](image/README/1696011639241.png)
4. Crio um par de chave para a instancia, ao qual vou sar tanto na instancia do front, quanto do back.
   ![1696011622308](image/README/1696011622308.png)
5. Também crio um novo security group para a instancia, esse sg vou fazer de modo que sirva para o back e para o frontend. Além de aumentar o tamnho do volume de armazenamento da EC2 de 8 para 16 GB.
   ![1696011722717](image/README/1696011722717.png)
6. Por fim a pré-vizualização de configuração deve estar assim:
![1696011803805](image/README/1696011803805.png)
7. Por fim, temos que alocar um ip elastico para uma ec2, já que estamos no ambiente da academy e os endereços de EC2 mudam conforme ele se encerra. Não altero nenhuma configuração na pagina de alocar um endereço ip.
   ![1696011859223](image/README/1696011859223.png)
8. Após criar, clico em associar endereço, para linkar esse IP, a minha EC2.
   ![1696011923679](image/README/1696011923679.png)
9. Seleciono a minha instacia e as configurações devem ficar assim:
![1696011982846](image/README/1696011982846.png)
10. Clico em associar e devo obter sucesso nessa etapa, o quadro de status do IP deve mudar:
![1696012025221](image/README/1696012025221.png)

## EC2 Back-end

1. Para criar a instacia do Back-end, repeti o mesmo processo que fiz na hora de criar a instancia do Front-end

## Configurando as EC2
1. Dentro da minha instancia, vou clicar em conexão, já que optei por usar o terminal da web da aws
![1696012435978](image/README/1696012435978.png)

2. Clico em conectar:
![1696012505743](image/README/1696012505743.png)

3. No terminal, já tenho a chance de começar a configurar com os comandos `sudo apt-get update && sudo apt-get upgrade`
   ![1696012553232](image/README/1696012553232.png)
   ![1696012636176](image/README/1696012636176.png)

4. Instalando o docker no EC2 pelo documentação do docker `https://docs.docker.com/engine/install/ubuntu/`
   ![1696012892553](image/README/1696012892553.png)

## Vídeo Conclusão:

[Acesse aqui](https://drive.google.com/file/d/1ySjT6aDBkKIDl6HLtYKcWQg7QBkcK0mT/view?usp=drive_link)

## Para rodar o projeto
Na pasta raiz, rode o comando:
`Docker compose up`