# Introdução ao PHP 8 por meio de exemplos

📖 **Leia o tutorial: [https://stahe.github.io/br-php8-oct-2026/](https://stahe.github.io/br-php8-oct-2026/)**

Este curso ensina a linguagem [PHP](https://www.php.net) 8.5 **por meio de exemplos**: mais de 300 arquivos PHP, comentados linha a linha, com os resultados de execução reproduzidos. Começa pelos fundamentos da linguagem e avança até web services e uma aplicação web MVC.

Esta é uma reescrita para PHP 8 do curso [Introdução ao PHP 7 por meio de exemplos](https://stahe.github.io/br-php7-juillet-2019/) (2019): mesmo roteiro, mesmos exemplos, mesmo fio condutor, mas com código atualizado. Entre o PHP 7 e o PHP 8.5, muitos recursos se tornaram **obsoletos** (deprecated): o código deste curso não usa **nenhum** deles. Todos os scripts foram executados com o PHP 8.5 configurado para relatar tudo (`error_reporting = E_ALL`): nenhuma mensagem `Deprecated` aparece em suas saídas.

| Curso PHP 7 (2019) | Curso PHP 8 (2026) |
|---|---|
| PHP 7.3 | PHP 8.5 |
| NetBeans | VS Code + PHP Intelephense |
| Codeception | PHPUnit 12 |
| Postman | curl |
| SwiftMailer, hMailServer | Symfony Mailer, Mailpit |
| funções `imap_*` (removidas do núcleo do PHP na 8.4) | clientes POP3/IMAP escritos com sockets |
| propriedades dinâmicas, getters/setters | propriedades tipadas, `readonly`, promoção de parâmetros do construtor |
| `switch`, constantes de classe | `match`, enumerações (`enum`) |
| `PDO::MYSQL_ATTR_*` (obsoleto na 8.5) | `PDO::connect()`, `Pdo\Mysql`, `Pdo\Pgsql` |
| `deny from all` (Apache 2.2) | um diretório `public/` e `Require all denied` (Apache 2.4) |

## Roteiro do curso

| Capítulo | Conteúdo |
|---|---|
| Instalação | Laragon 8 (PHP 8.5, Apache, MySQL, PostgreSQL, Redis), VS Code, Composer |
| Fundamentos do PHP | variáveis, tipagem estrita, arrays, strings, funções (argumentos nomeados, `match`, arrow functions, operador pipe `\|>` do PHP 8.5), arquivos de texto, JSON |
| Classes, interfaces | atributos tipados, promoção de construtor, `readonly`, property hooks e visibilidade assimétrica (PHP 8.4), enumerações, `#[\Override]`, `clone` com modificações (PHP 8.5), tipos de interseção |
| Exceções e erros | a hierarquia `Throwable` no PHP 8, avisos do PHP 7 convertidos em exceções |
| Traits, aplicações em camadas | reutilização de código; arquitetura [DAO] / [lógica de negócio] / [console] |
| Testes | PHPUnit 12: data providers via atributos, exceções esperadas |
| Bancos de dados | PDO com MySQL 8 e PostgreSQL: prepared statements, transações |
| Funções de rede | TCP, HTTP, SMTP, POP3, IMAP, implementados com sockets e depois com bibliotecas |
| Web services | páginas dinâmicas, JSON, parâmetros GET/POST, sessões, autenticação, HTTPS |
| XML | SimpleXML e a nova API `Dom\XMLDocument` do PHP 8.4 |

## O fio condutor: um calculador de imposto de renda em 13 versões

Ao longo do curso, versão após versão, construímos um **calculador de imposto de renda**:

- **versões 1 e 2**: um script, funções, arquivos de texto e JSON;
- **versão 3**: classes; **versão 4**: uma arquitetura em camadas, testada com PHPUnit;
- **versões 5 a 7**: dados de imposto em um banco de dados MySQL, depois PostgreSQL e, por fim, qualquer um dos dois;
- **versões 8 a 11**: um web service e seu cliente de console: autenticação, sessões, logs, notificações por e-mail ao administrador em caso de erros, cache Redis, respostas em JSON e depois em XML;
- **versão 12**: uma aplicação web **MVC** que devolve respostas em JSON, XML ou HTML (Bootstrap 5), com um cliente de console para o serviço JSON;
- **Versão 13**: Segurança dos arquivos da aplicação (somente a pasta `public/` fica visível pela web).



## Tecnologias

PHP 8.5 · Apache 2.4 · MySQL 8.4 · PostgreSQL · Redis · Composer · PHPUnit 12 · Symfony HttpFoundation 8 · Symfony HttpClient 8 · Symfony Mailer 8 · Predis 3 · zbateson/mail-mime-parser 3 · Mailpit · Bootstrap 5 · Laragon 8 · VS Code

## Pré-requisitos

- Experiência prévia de programação em qualquer linguagem.
- Windows e [Laragon](https://laragon.org) 8 (que inclui PHP 8.5, Apache, MySQL, PostgreSQL, Redis e Composer), [VS Code](https://code.visualstudio.com) e sua extensão PHP IntelliSense. As instruções de instalação são fornecidas no início do curso.

## Autor

Este curso e seu código foram escritos por **Claude**, a IA da [Anthropic](https://www.anthropic.com) (outubro de 2026), a pedido de Serge Tahé, com base em seu curso de PHP 7 de 2019.
