# Docker: Utilização prática no cenário de Microsserviços

## Descrição do Projeto

Este projeto tem como objetivo demonstrar a utilização prática do Docker em um cenário de microsserviços. Ele abrange a configuração de um servidor Nginx, um script PHP para interação com um banco de dados MySQL e um arquivo SQL para criação de tabelas.

## Estrutura do Projeto

- **`nginx.conf`**: Arquivo de configuração do Nginx, incluindo balanceamento de carga.
- **`index.php`**: Script PHP para inserção de dados no banco e exibição da versão do PHP.
- **`dockerfile`**: Dockerfile para criação de uma imagem personalizada do Nginx.
- **`banco.sql`**: Script SQL para criação da tabela `dados` no banco de dados.
- **`README.md`**: Documentação do projeto.

## Como Executar

1. Certifique-se de ter o Docker instalado em sua máquina.
2. Construa a imagem Docker:
   ```bash
   docker build -t meu-nginx .
   ```
3. Execute o container:
   ```bash
   docker run -d -p 4500:4500 meu-nginx
   ```
4. **Acesse o serviço no navegador em** [http://localhost:4500](http://localhost:4500).

## Configuração do Banco de Dados

Certifique-se de que o banco de dados MySQL esteja configurado e acessível. Utilize o script `banco.sql` para criar a tabela necessária:

```sql
CREATE TABLE dados (
    AlunoID int,
    Nome varchar(50),
    Sobrenome varchar(50),
    Endereco varchar(150),
    Cidade varchar(50),
    Host varchar(50)
);
```
## Observações

- O arquivo `index.php` utiliza credenciais de exemplo para conexão com o banco de dados. Ajuste-as conforme necessário.
- O balanceamento de carga no Nginx está configurado para múltiplos servidores fictícios. Atualize os endereços IP no arquivo `nginx.conf` conforme sua necessidade.

## Referências

Este projeto faz parte do curso ministrado por **Denilson Bonatti** na plataforma Digital Innovation One.

