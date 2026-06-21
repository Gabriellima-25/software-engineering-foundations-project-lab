#  Documento de Requisitos e Projeto de Software

---

##  1. Introdução

### 1.1 Objetivo
Este documento tem como objetivo descrever os requisitos funcionais e não funcionais do sistema StockFácil, um software web voltado à gestão de estoque de pequenas empresas e e-commerces varejistas. O sistema foi desenvolvido com foco na simplicidade de uso, permitindo que qualquer usuário opere a plataforma sem necessidade de treinamento prévio.
### 1.2 Escopo
O StockFácil é uma plataforma web que permite às empresas controlar o fluxo de estoque de forma digital e centralizada. O sistema contempla o cadastro de produtos, fornecedores e usuários, o registro de entradas e saídas, a geração de relatórios, alertas automáticos e um painel de indicadores em tempo real.
Está fora do escopo deste sistema:
- Emissão de notas fiscais ou integração com sistemas contábeis.
- Funcionalidades de ponto de venda (PDV).
- Gestão financeira ou contas a pagar/receber.
- Integração nativa com plataformas de e-commerce de terceiros.

### 1.3 Definições, Acrônimos e Abreviações
Para garantir o alinhamento de toda a equipe e facilitar a leitura deste documento, definem-se os seguintes termos: 

- SKU: Stock Keeping Unit – código único de identificação de produto.
- RF: Requisito Funcional.
- RNF: Requisito Não Funcional.
- CNPJ: Cadastro Nacional da Pessoa Jurídica.
- Dashboard: Painel visual com indicadores e resumo de informações do sistema.
- bcrypt: Algoritmo de hash criptográfico utilizado para armazenamento seguro de senhas.
- TLS: Transport Layer Security – protocolo de criptografia de dados.

---

##  2. Product Vision

### 2.1 Problema
Muitas empresas e pequenos negócios enfrentam dificuldades no controle de estoque interno, como falta de organização, erros manuais, perda de produtos, dificuldade em acompanhar entradas e saídas e ausência de dados em tempo real. Esses problemas podem gerar prejuízos financeiros, desperdício de recursos e baixa eficiência operacional.

### 2.2 Solução
O StockFácil permite que as empresas monitorem o fluxo de estoque em tempo real, acompanhando as entradas e saídas de produtos. Além disso, o sistema gera relatórios personalizados com base nesses dados como listas de saldos atuais e resumo de movimentações e oferece alertas automáticos para estoque abaixo do nível mínimo configurado ou acima do esperado.

### 2.3 Público-Alvo
Os principais usuários do aplicativo serão:
-	Pequenos comerciantes com lojas físicas e/ou virtuais (e-commerce)
-	Empreendedores do varejo que precisam controlar produtos, entradas e saídas.
-	Equipes de almoxarifado
-	Gestores de microempresas que desejam substituir controles manuais ou planilhas
-	Equipes de estoque com múltiplos operadores e necessidade de controle de acesso

### 2.4 Proposta de Valor
O StockFácil oferece a pequenas empresas acesso a um sistema moderno e acessível para controle de estoque, substituindo planilhas desorganizadas e processos manuais por uma plataforma centralizada, visual e de fácil operação. O sistema entrega visibilidade em tempo real sobre os produtos, reduzindo perdas, evitando rupturas de estoque e aumentando a eficiência operacional.

### 2.5 Diferencial
O principal diferencial do StockFácil é a simplicidade de uso. A interface foi projetada para ser intuitiva e autoexplicativa, dispensando treinamentos formais para a operação do dia a dia. Diferentemente de sistemas ERP complexos, o StockFácil foca exclusivamente na gestão de estoque, com fluxos simplificados e alertas proativos que apoiam a tomada de decisão mesmo por usuários sem experiência com software de gestão.

### 2.6 Funcionalidades principais (alto nível)
- Cadastro e gestão de produtos com código SKU, categoria e unidade de medida.
- Registro de entradas e saídas de estoque com histórico completo.
- Dashboard com indicadores em tempo real: saldo total, produtos críticos e últimas movimentações.
- Alertas automáticos de estoque mínimo e excesso.
- Geração de relatórios por período, produto ou categoria.
- Controle de acesso por perfis de usuário (administrador, operador, visualizador).
- Importação e exportação de dados em CSV/Excel.
---

##  3. Visão Geral do Sistema

### 3.1 Descrição Geral
O StockFácil é um aplicativo web para gestão de estoque de pequenas empresas e e-commerces varejistas. A plataforma permite registrar e monitorar movimentações de produtos em tempo real, com alertas de reposição e relatórios dinâmicos, substituindo planilhas manuais e processos desorganizados. O sistema é acessível via navegador web em dispositivos desktop e móveis, garantindo flexibilidade operacional para equipes de estoque.

### 3.2 Stakeholders
Liste os principais envolvidos:
- Usuários
- Clientes
- Desenvolvedores
- Outros

---

##  4. Requisitos Funcionais
- FR01 - Permitir o cadastro de usuários com diferentes perfis de acesso (administrador, operador, visualizador).
- FR02 - Permitir o login com autenticação por e-mail e senha.
- FR03 - Permitir o cadastro, edição e exclusão de produtos com nome, código SKU, categoria, unidade de medida e descrição.
- FR04 - Registrar entradas e saídas de estoque com data, quantidade e responsável.
- FR05 - Exibir o saldo atual de cada produto em tempo real.
- FR06 - Emitir alertas automáticos quando o estoque de um produto atingir o nível mínimo configurado.
- FR07 - Permitir a geração de relatórios de movimentação por período, produto ou categoria.
- FR08 - Permitir o cadastro de fornecedores com nome, CNPJ, contato e produtos associados.
- FR09 - Registrar o histórico completo de todas as movimentações de estoque.
- FR10 - Permitir a importação e exportação de dados em formato CSV/Excel.
- FR11 - Exibir um dashboard com indicadores gerais: total de itens, produtos em falta, últimas movimentações.
- FR12 - Permitir a busca e filtragem de produtos por nome, categoria ou código.
- FR13 - Permitir o controle de múltiplos locais de armazenamento (filiais, depósitos).
- FR14 - Registrar o custo de compra dos produtos para cálculo de valor total do estoque .
- FR15 - Permitir a recuperação de senha via e-mail.

**Detalhamento dos requisitos principais:**

### RF01 - Cadastro de usuario
**Descrição:**  
Permitir o cadastro de usuários com diferentes perfis de acesso (administrador, operador, visualizador).

**Prioridade:** Alta  
**Entradas:** Nome completo, e-mail, senha, perfil de acesso selecionado. 
**Saídas:** Usuário cadastrado e ativo no sistema, com permissões aplicadas conforme o perfil.
**Regras de negócio:**
Apenas administradores podem criar, editar ou excluir usuários. O e-mail deve ser único por conta. Não é possível excluir o último administrador ativo.

---

### RF03 - Cadastro de produtos
**Descrição:**  
O sistema deve permitir o cadastro, edição e exclusão de produtos, incluindo os campos: nome, código SKU, categoria, unidade de medida, descrição, quantidade mínima e custo de compra.

**Prioridade:** Alta  
**Entradas:** Nome do produto, SKU, categoria, unidade de medida, descrição, quantidade mínima, custo unitário.
**Saídas:** Produto criado, editado ou removido do catálogo. Saldo inicial registrado.
**Regras de negócio:**
O código SKU deve ser único por empresa. A exclusão de produto só é permitida se não houver movimentações vinculadas. Somente administradores e operadores podem cadastrar ou editar produtos.

---

### RF04 - Registro de Entradas e Saídas
**Descrição:**  
O sistema deve permitir o registro de movimentações de estoque (entrada ou saída), informando o produto, a quantidade, a data e o usuário responsável. O saldo do produto deve ser atualizado automaticamente.

**Prioridade:** Alta  
**Entradas:** Tipo de movimentação (entrada/saída), produto, quantidade, data, observação opcional. 
**Saídas:** Movimentação registrada, saldo atualizado em tempo real, histórico atualizado.
**Regras de negócio:**
Não é permitido registrar saída com quantidade superior ao saldo disponível. Movimentações não podem ser excluídas, apenas estornadas. O usuário responsável é registrado automaticamente pela sessão ativa.

---

### RF06 - Alertas Automáticos de Estoque
**Descrição:**  
Permitir o cadastro de usuários com diferentes perfis de acesso (administrador, operador, visualizador).

**Prioridade:** Alta  
**Entradas:** Nome completo, e-mail, senha, perfil de acesso selecionado. 
**Saídas:** Usuário cadastrado e ativo no sistema, com permissões aplicadas conforme o perfil.
**Regras de negócio:**
Os limites mínimo e máximo são definidos individualmente por produto. Alertas repetidos para o mesmo produto não devem ser gerados mais de uma vez por hora.

---

### RF07 - Geração de Relatórios
**Descrição:**  
O sistema deve permitir a geração de relatórios de movimentação de estoque, podendo ser filtrados por período, produto ou categoria. Os relatórios devem ser exportáveis em PDF e CSV.

**Prioridade:** Média
**Entradas:** Filtros selecionados: período (data inicial e final), produto e/ou categoria.
**Saídas:** Relatório exibido em tela e disponível para download em PDF ou CSV.
**Regras de negócio:**
Relatórios de períodos superiores a 12 meses devem exigir confirmação do usuário. Apenas administradores e visualizadores têm acesso à geração de relatórios completos.

---

### RF11 - Dashboard de Indicadores
**Descrição:**  
O sistema deve exibir um painel visual com os principais indicadores do estoque: total de itens cadastrados, produtos com estoque crítico (abaixo do mínimo), produtos com excesso, valor total do estoque e as últimas movimentações realizadas.

**Prioridade:** Alta  
**Entradas:** Dados consolidados do banco de dados em tempo real
**Saídas:** Painel atualizado automaticamente com gráficos e números-chave do estoque.
**Regras de negócio:**
O dashboard deve ser a primeira tela exibida após o login. Deve ser carregado em no máximo 3 segundos. Os dados devem refletir o estado atual do estoque sem necessidade de atualização manual.

---

##  5. Requisitos Não Funcionais

### 5.1 Usabilidade
- O sistema deve ser totalmente responsivo, adaptando-se a dispositivos móveis, tablets e desktops.
- O usuário deve conseguir registrar uma entrada ou saída de estoque em no máximo 3 cliques a partir do menu principal.
- O sistema deve exibir mensagens de erro claras e orientações de correção sempre que uma ação falhar.
- O dashboard principal deve apresentar os indicadores mais importantes de forma visual e de fácil interpretação.
- O sistema deve seguir padrões de acessibilidade WCAG 2.1 nível AA.

---

### 5.2 Eficiência
- O sistema deve responder a qualquer requisição do usuário em até 2 segundos em condições normais de uso.
- O sistema deve suportar até 500 usuários simultâneos sem degradação de desempenho.
- Operações de busca e filtro de produtos devem retornar resultados em menos de 1 segundo.

### 5.3 Desempenho
- •
- O carregamento inicial do dashboard não deve ultrapassar 3 segundos em conexões de banda larga.
- A geração de relatórios de até 12 meses de histórico deve ser concluída em no máximo 5 segundos.
- O sistema deve processar o registro de uma movimentação e atualizar o saldo em menos de 1 segundo.

### 5.4 Espaço
- Cada empresa contratante terá uma cota inicial de armazenamento de até 5 GB para dados e históricos de movimentações.
- Arquivos importados via CSV/Excel não devem ultrapassar 10 MB por operação.
- O sistema deve utilizar compressão de dados e paginação para minimizar o consumo de memória nas consultas.
- Logs de auditoria devem ser retidos por no mínimo 12 meses e arquivados automaticamente após esse período.

### 5.5 Confiabilidade
- O sistema deve ter disponibilidade mínima de 99,5% ao mês, exceto em manutenções programadas com aviso prévio.
- Em caso de falha, o sistema deve se recuperar automaticamente sem perda de dados já confirmados.
- Todas as operações críticas (registros de movimentação, alterações de cadastro) devem utilizar transações atômicas no banco de dados.
- O sistema deve realizar backups automáticos diários dos dados com retenção de 30 dias.

### 5.6 Segurança (Proteção)
- O sistema deve criptografar senhas utilizando algoritmo de hash seguro (bcrypt com salt).
- O sistema deve implementar autenticação com bloqueio após 5 tentativas incorretas consecutivas.
- O sistema deve restringir o acesso às funcionalidades conforme o perfil do usuário (administrador, operador, visualizador).
- Todas as comunicações devem ser realizadas via HTTPS (TLS 1.2 ou superior).
- Tokens de sessão devem expirar após 8 horas de inatividade, exigindo novo login.
- O sistema deve registrar logs de auditoria para ações críticas, como exclusão de produtos e alterações de estoque.

---

##  6. Requisitos Organizacionais

### 6.1 Ambientais
- •	O sistema deve ser hospedado em infraestrutura de nuvem (AWS, GCP ou Azure), utilizando serviços gerenciados de banco de dados e balanceamento de carga.
- •	O ambiente de produção deve ser separado dos ambientes de desenvolvimento e homologação.
- •	O sistema deve ser compatível com os navegadores Google Chrome, Mozilla Firefox, Microsoft Edge e Safari nas duas versões mais recentes.
- •	O servidor de aplicação deve operar em Linux (Ubuntu 22.04 LTS ou superior).

### 6.2 Operacionais
- O sistema deve registrar logs de acesso, erros e ações críticas em formato estruturado (JSON) para facilitar a análise e auditoria.
- Deve haver monitoramento contínuo de disponibilidade e desempenho, com alertas automáticos para a equipe de operações em caso de incidentes.
- Manutenções programadas devem ser comunicadas com pelo menos 48 horas de antecedência e realizadas preferencialmente fora do horário comercial.
- O sistema deve disponibilizar uma página de status pública informando a saúde dos serviços em tempo real.

### 6.3 Desenvolvimento
- O versionamento do código-fonte deve ser realizado com Git, utilizando o modelo de branches GitFlow (main, develop, feature, hotfix).
- O código deve seguir os padrões de clean code, com nomenclatura clara, funções com responsabilidade única e ausência de duplicação desnecessária.
- Devem ser implementados testes automatizados unitários e de integração, com cobertura mínima de 80% nas funcionalidades críticas.
- O processo de CI/CD deve garantir que todo código mesclado na branch principal seja validado automaticamente antes da implantação em produção.
- A documentação técnica das APIs deve ser mantida atualizada utilizando o padrão OpenAPI (Swagger).

---

##  7. Requisitos Externos

### 7.1 Reguladores
- O sistema deve estar em conformidade com a Lei Geral de Proteção de Dados (LGPD — Lei nº 13.709/2018), garantindo que os dados pessoais dos usuários.
- O sistema deve manter registros de consentimento e logs de acesso a dados pessoais para fins de auditoria regulatória.

### 7.2 Éticos
- O sistema não deve adotar qualquer mecanismo que discrimine usuários com base em raça, gênero, idade, localização ou qualquer outro fator pessoal no acesso às funcionalidades.
- O sistema não deve coletar dados além do estritamente necessário para o funcionamento da plataforma.
- Em caso de alterações nos termos de uso ou política de privacidade, os usuários devem ser notificados com antecedência e de forma clara.

### 7.3 Legais
- O sistema deve estar em conformidade com o Marco Civil da Internet (Lei nº 12.965/2014), respeitando as diretrizes de privacidade, neutralidade e responsabilidade no ambiente digital.
- Os contratos de uso da plataforma devem estar alinhados ao Código de Defesa do Consumidor (Lei nº 8.078/1990), garantindo clareza nas condições de serviço.
- O armazenamento e o tratamento de dados devem respeitar as legislações brasileiras vigentes sobre proteção de dados e segurança da informação.

### 7.4 Segurança Externa
- O sistema deve possuir mecanismos de proteção contra invazoes, vazamento de dados e acessos não autorizados, ultilizando sistemas de criptografia, altenticadores e sistemas de monitoramento.
- Deve ser realizada pelo menos uma auditoria de segurança externa anualmente, com relatório de vulnerabilidades e plano de correção.
  

### 7.5 Contábeis
- O sistema deve registrar todas as movimentações de estoque com data, hora e usuário responsável, garantindo rastreabilidade completa para fins contábeis.
- O sistema deve permitir a exportação dos dados de movimentação em formatos compatíveis com ferramentas contábeis (CSV e Excel).

---

##  8. Arquitetura do Sistema

### 8.1 Visão Geral
O StockFácil adota uma arquitetura monolítica modular, onde frontend e backend são desenvolvidos de forma separada, mas implantados em um único servidor de aplicação. Essa abordagem foi escolhida por ser adequada ao porte inicial da plataforma e simplificar o processo de desenvolvimento, manutenção e deploy. A separação clara entre camadas garante coesão interna e facilita a evolução futura para microsserviços, caso a escala da aplicação exija.
A aplicação segue o padrão de três camadas (three-tier architecture):
- Camada de Apresentação (Frontend): interface web responsiva acessada pelo navegador.
- Camada de Aplicação (Backend): lógica de negócio, APIs RESTful e controle de autenticação.
- Camada de Dados (Banco de Dados): armazenamento persistente de todas as entidades do sistema.

### 8.2 Componentes
### Frontend
renderizar a interface do usuário e consumir a API REST do backend. A comunicação ocorre via HTTPS com troca de tokens JWT para autenticação. O frontend é servido por um servidor de arquivos estáticos (ex.: Nginx) e é totalmente responsivo, compatível com dispositivos móveis, tablets e desktops.
Principais módulos do frontend:
- Módulo de Autenticação: login, recuperação de senha e controle de sessão.
- Dashboard: painel de indicadores em tempo real com gráficos e KPIs.
- Módulo de Produtos: cadastro, edição, exclusão e busca de produtos.
- Módulo de Movimentações: registro de entradas e saídas, histórico e estornos.
- Módulo de Fornecedores: CRUD de fornecedores com produtos associados.
- Módulo de Relatórios: geração e exportação em PDF e CSV.
- Módulo de Usuários: gerenciamento de perfis e permissões de acesso.
### Backend  
O backend é uma API RESTful desenvolvida em Node.js com o framework Express.js. Ele encapsula todas as regras de negócio do sistema, valida dados de entrada, aplica controle de acesso por perfil (RBAC – Role-Based Access Control) e persiste informações no banco de dados. A comunicação com o frontend é stateless, utilizando tokens JWT com expiração configurada em 8 horas.
Principais serviços do backend:
- Auth Service: emissão, validação e renovação de tokens JWT.
- User Service: CRUD de usuários com controle de perfis (admin, operador, visualizador).
- Product Service: gerenciamento de produtos, categorias e SKUs.
- Stock Service: registro de movimentações, cálculo de saldos e alertas automáticos.
- Supplier Service: gerenciamento de fornecedores.
- Report Service: consolidação de dados e geração de relatórios em PDF/CSV.
- Notification Service: disparo de alertas de estoque mínimo e máximo por e-mail ou notificação in-app.
### Banco de dados  
O sistema utiliza o PostgreSQL como banco de dados relacional principal, hospedado em um serviço gerenciado na nuvem (ex.: Amazon RDS ou Cloud SQL). O modelo relacional foi escolhido pela natureza estruturada dos dados e pela necessidade de transações atômicas nas operações de movimentação de estoque.


| Entidade | Descrição | Relacionamentos Principais |
|---|---|---|
| Usuario | Dados de autenticação e perfil de acesso | Movimentacoes, Logs |
| Produto | Catálogo de produtos com SKU, categoria e custo | Movimentacoes, Fornecedor, LocalEstoque |
| Movimentacao | Registro de entradas e saídas de estoque | Produto, Usuario |
| Fornecedor | Dados de fornecedores com CNPJ e contato | Produto |
| LocalEstoque | Filiais e depósitos da empresa | Produto, Movimentacao |
| AlertaEstoque | Registros de alertas gerados automaticamente | Produto |
| LogAuditoria | Histórico de ações críticas para auditoria | Usuario |

---

### APIs externas  
O StockFácil integra as seguintes APIs e serviços externos:
- Serviço de E-mail (SendGrid ou AWS SES): envio de e-mails transacionais para recuperação de senha e alertas de estoque.
- Serviço de Armazenamento em Nuvem (AWS S3 ou Google Cloud Storage): armazenamento de arquivos importados e relatórios exportados.
- Serviço de Monitoramento (Datadog ou AWS CloudWatch): monitoramento de disponibilidade, desempenho e alertas de incidentes.
- Serviço de Autenticação SMTP: para envio de notificações automáticas.

### 8.3 Tecnologias
| Camada | Tecnologia | Justificativa |
|---|---|---|
| Frontend | React.js + TypeScript | Ecossistema maduro, componentização e tipagem segura |
| Estilização | Tailwind CSS | Design responsivo com produtividade e consistência visual |
| Backend | Node.js + Express.js | Alta performance I/O, ampla comunidade, JSON nativo |
| Banco de Dados | PostgreSQL 15 | Transações ACID, confiabilidade e suporte a JSON |
| ORM | Prisma ORM | Type-safe, migrations automáticas e produtividade de desenvolvimento |
| Autenticação | JWT + bcrypt | Padrão do mercado para APIs stateless e hash seguro de senhas |
| Cache | Redis | Cache de sessões, filas de alertas e dados do dashboard |
| Servidor Web | Nginx | Proxy reverso, servir estáticos e TLS termination |
| Infraestrutura | AWS (EC2, RDS, S3, CloudWatch) | Alta disponibilidade, escalabilidade gerenciada e SLAs confiáveis |
| CI/CD | GitHub Actions | Automação de testes, build e deploy integrados ao GitFlow |
| Contêineres | Docker + Docker Compose | Padronização de ambientes e facilidade de deploy |
| Documentação API | Swagger / OpenAPI 3.0 | Conformidade com o requisito RO-DEV e autodocumentação |

### 8.4 Decisões Arquiteturais
Esta seção descreve como as escolhas tecnológicas e o modelo de arquitetura adotados para o StockFácil atendem diretamente aos Requisitos Não Funcionais (RNFs) de Desempenho, Segurança e Escalabilidade estabelecidos para a plataforma. 

**Desempenho:**
A arquitetura do StockFácil foi projetada para garantir que as operações de busca ocorram em menos de 1 segundo e o carregamento do dashboard não ultrapasse 3 segundos. As decisões que sustentam esse RNF incluem: 
-  Camada de Cache com Redis: O Redis é utilizado para realizar o cache dos dados consolidados do dashboard e gerenciar as filas de alertas de estoque. Isso evita consultas repetitivas e custosas ao banco de dados relacional a cada novo login, garantindo o carregamento da tela inicial dentro do limite de 3 segundos exigido pelas regras de negócio. 
-  Backend Assíncrono com Node.js e Express.js: A escolha do Node.js fornece alta performance em operações de I/O (Entrada/Saída), permitindo que múltiplas requisições simultâneas sejam processadas sem bloqueio da thread principal, o que apoia o RNF de tempo de resposta geral do sistema em até 2 segundos. 
-  Servidor Web Nginx: Configurado como proxy reverso e responsável por servir os arquivos estáticos do frontend (React.js) otimizados, além de realizar o TLS termination de forma eficiente, reduzindo a carga de processamento do servidor de aplicação. 
-  Estratégias de Banco de Dados: O uso do PostgreSQL 15 combinado com paginação de consultas e compressão de dados minimiza o consumo de memória e acelera o tempo de retorno nas buscas por produtos e históricos de movimentação. 
 
   **Segurança:**
 A proteção dos dados e o controle rigoroso de acessos cumprem as exigências regulatórias (LGPD e Marco Civil) e os RNFs de segurança do sistema: 
- 	Autenticação Stateless com JWT: O controle de sessão é feito via tokens JWT com tempo de expiração definido em 8 horas de inatividade. A comunicação ocorre obrigatoriamente através do protocolo HTTPS (criptografia em trânsito com TLS 1.2 ou superior) gerenciado pelo Nginx. 
- 	Criptografia de Senhas com bcrypt: Nenhuma senha é armazenada em texto plano. O sistema aplica a função de hash criptográfico bcrypt com adição de salt no Auth Service do backend antes da persistência no banco de dados. 
- 	Controle de Acesso Baseado em Perfis (RBAC): O User Service aplica de maneira rígida o controle de permissões em nível de API, bloqueando ações críticas (como criação de usuários e exclusão de produtos) para perfis que não sejam "Administrador". 
- 	Transações Atômicas (ACID) e Logs de Auditoria: Para mitigar falhas e garantir a confiabilidade, o Prisma ORM e o PostgreSQL asseguram transações atômicas nas movimentações de estoque (se uma etapa falhar, toda a operação é revertida). Além disso, ações críticas geram logs estruturados em formato JSON para auditoria imediata. 
 
 **Escalabilidade:**
Embora o sistema adote uma arquitetura monolítica modular inicial devido ao porte do projeto, ele possui bases sólidas para escala horizontal e isolamento de componentes: 
- 	Modularidade e Separação de Responsabilidades: O backend é dividido internamente em serviços independentes bem definidos (Product Service, Stock Service, Notification Service, etc.). Essa separação clara de camadas facilita uma eventual transição futura para uma arquitetura de microsserviços caso a demanda cresça exponencialmente. 
- 	Arquitetura Stateless e Balanceamento de Carga: Como o backend não armazena o estado das sessões dos usuários (fator garantido pelo uso de JWT), a aplicação pode ser facilmente duplicada em múltiplas instâncias na infraestrutura de nuvem (AWS EC2) atrás de um balanceador de carga. Isso garante o suporte ao RNF de até 500 usuários simultâneos sem degradação do ambiente. 
- 	Uso de Serviços Gerenciados: A delegação de armazenamento de arquivos (relatórios e CSVs) para o AWS S3 e o uso de banco de dados gerenciado (Amazon RDS) retiram o gargalo de armazenamento do servidor principal, permitindo que o espaço em disco e a capacidade de processamento de dados cresçam de forma elástica.

---

## 9. Casos de Uso e Diagramas UML

Esta seção deve representar visualmente e descritivamente o funcionamento do sistema.

Os diagramas ajudam na:
- modelagem do sistema;
- comunicação entre equipe;
- entendimento da arquitetura e funcionalidades;
- documentação técnica do projeto.

---

# 9.1 Casos de Uso

Os casos de uso representam as interações entre usuários (atores) e o sistema.

---

### UC01 - Realizar Login

**Ator:** Usuário  

**Descrição:**  
Permite que o usuário acesse o sistema utilizando credenciais válidas.

---

### Fluxo principal
1. Usuário acessa a tela de login  
2. Usuário informa e-mail e senha  
3. Sistema valida credenciais  
4. Sistema libera acesso  

---

### Fluxo alternativo
- Credenciais inválidas  
- Usuário esqueceu senha  

---

## Exemplo de Diagrama de Caso de Uso

[Usuário]

    |
    
    | ---- (Realizar Login)
    
    | ---- (Cadastrar Conta)
    
    | ---- (Recuperar Senha) 

---

## 9.2 Diagrama de Classes (UML)

O diagrama de classes representa:

- estrutura do sistema;
- entidades;
- atributos;
- métodos;
- relacionamentos.

---

### Exemplo

```text
+------------------+
|     Usuário      |
+------------------+
| - id             |
| - nome           |
| - email          |
| - senha          |
+------------------+
| + login()        |
| + logout()       |
+------------------+
```

---

### Exemplo com relacionamento

```text
+------------------+        +------------------+
|     Usuário      | 1    * |      Pedido      |
+------------------+--------+------------------+
| id               |        | id               |
| nome             |        | valor            |
+------------------+        +------------------+
```

---

## 9.3 Diagrama de Atividades (UML)

Representa o fluxo de execução de processos no sistema.

---

### Exemplo

```text
[Início]
   |
[Acessar sistema]
   |
[Inserir login]
   |
{Credenciais válidas?}
   | Sim
[Acessa sistema]
   |
[Fim]

   | Não
[Mensagem de erro]
```

---

## 9.4 Diagrama de Sequência (UML)

Representa a comunicação entre objetos ao longo do tempo.

---

### Exemplo

```text
Usuário -> Sistema: realizar login
Sistema -> Banco: validar usuário
Banco -> Sistema: usuário válido
Sistema -> Usuário: acesso liberado
```

---

## 9.5 Diagrama de Componentes

Representa os módulos e componentes principais do sistema.

---

### Exemplo

```text
[Frontend]
     |
     v
[API Backend]
     |
     v
[Banco de Dados]
```

---

## 9.6 Diagrama de Implantação (Deployment)

Representa onde o sistema será executado.

---

### Exemplo

```text
[Usuário]
     |
Internet
     |
[Servidor Web]
     |
[Servidor Banco de Dados]
```

---

## 9.7 Ferramentas Recomendadas

Os diagramas podem ser feitos utilizando:

- Draw.io
- Lucidchart
- StarUML
- Visual Paradigm
- PlantUML
- Mermaid
- Figma

---

## 9.8 Observações Importantes

- Os diagramas devem representar o sistema REAL do grupo;
- Evitem diagramas genéricos;
- Mantenham consistência entre requisitos e diagramas;
- Diagramas devem possuir nomes claros;
- Atualizem os diagramas conforme o sistema evoluir.

---

# Regra importante

> “Diagramas não são apenas desenhos: eles representam decisões arquiteturais e técnicas do sistema.”

---

##  10. Plano de Testes

### 10.1 Estratégia de Teste
A estratégia de testes do StockFácil combina testes automatizados e manuais, aplicados em diferentes níveis do sistema:
- Testes unitários cobrem as regras de negócio isoladas (ex.: cálculo de saldo, validação de SKU único), executados a cada commit via CI/CD (GitHub Actions).
- Testes de integração validam a comunicação entre os serviços do backend e o banco de dados (ex.: registro de movimentação com atualização de saldo em transação atômica).
- Testes de sistema validam fluxos completos ponta a ponta (login → cadastro de produto → movimentação → relatório).
- Testes de aceitação são conduzidos com usuários representativos (operadores e administradores) para validar usabilidade e aderência aos requisitos funcionais antes da liberação em produção.
- A cobertura mínima exigida é de 80% nas funcionalidades críticas (FR04, FR06, FR11), conforme RO-DEV.

### 10.2 Tipos de Teste
- Unitário  
- Integração  
- Sistema  
- Aceitação  

### 10.3 Casos de Teste

#### CT01 - Cadastro de Usuário com E-mail Duplicado
**Requisito relacionado:** RF01  
**Descrição:**  Verificar se o sistema impede o cadastro de dois usuários com o mesmo e-mail.
**Entrada:**  E-mail já existente no sistema.
**Resultado esperado:**   Sistema rejeita o cadastro e exibe mensagem de erro indicando e-mail duplicado.

#### CT02 - Registro de Saída Maior que o Saldo Disponível
**Requisito relacionado:** RF04 
**Descrição:**   Verificar se o sistema bloqueia uma saída de estoque superior ao saldo atual do produto.
**Entrada:**  Produto com saldo de 10 unidades; tentativa de saída de 15 unidades.
**Resultado esperado:**  Sistema impede a operação e exibe mensagem de saldo insuficiente.

#### CT03 -  Disparo de Alerta de Estoque Mínimo
**Requisito relacionado:** RF06
**Descrição:**  Verificar se o alerta é gerado quando o saldo atinge o limite mínimo configurado.
**Entrada:**  Produto com mínimo configurado em 5 unidades; saída que leva o saldo a 4 unidades.
**Resultado esperado:**  Sistema gera o alerta automaticamente e não duplica o envio caso outra saída ocorra na mesma hora.

#### CT04 -  Geração de Relatório com Período Superior a 12 Meses
**Requisito relacionado:** RF07
**Descrição:** Verificar se o sistema solicita confirmação ao gerar relatório de período extenso.
**Entrada:**  Filtro de data com intervalo de 14 meses.
**Resultado esperado:**   Sistema exibe alerta de confirmação antes de processar o relatório.

#### CT05 - Carregamento do Dashboard em até 3 Segundos
**Requisito relacionado:** RF11 
**Descrição:**  Verificar o tempo de carregamento do dashboard após login.
**Entrada:**  Login de usuário com dados consolidados em cache (Redis).
**Resultado esperado:**  Dashboard carregado em no máximo 3 segundos.

#### CT06 -  Exclusão do Último Administrador Ativo
**Requisito relacionado:** RF01  
**Descrição:**  Verificar se o sistema impede a exclusão do único administrador ativo.
**Entrada:**  Tentativa de exclusão do último usuário com perfil "administrador".
**Resultado esperado:** Sistema bloqueia a ação e exibe mensagem informando que deve haver ao menos um administrador ativo.

---

### 10.4 Testes de Requisitos Não Funcionais
## Performance:
- Testes de carga simulando até 500 usuários simultâneos (ferramenta sugerida: k6 ou JMeter), validando tempo de resposta ≤ 2s.
= Teste de tempo de busca/filtro de produtos, validando retorno ≤ 1s.

## Segurança:
- Teste de força bruta simulando 5+ tentativas de login incorretas, validando bloqueio automático da conta.
- Verificação de que senhas são armazenadas com hash bcrypt (nunca em texto plano).
- Teste de acesso indevido: usuário com perfil "visualizador" tentando excluir produto deve ser bloqueado (RBAC).
- Verificação de uso obrigatório de HTTPS/TLS em todas as requisições.

## Usabilidade:
- Teste de fluxo de registro de movimentação, validando conclusão em até 3 cliques a partir do menu principal.
- Teste de responsividade em resoluções mobile, tablet e desktop.
- Verificação de conformidade com WCAG 2.1 nível AA (contraste, navegação por teclado, leitores de tela).
---

