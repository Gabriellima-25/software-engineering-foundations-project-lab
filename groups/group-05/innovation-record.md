# Registro de Inovação

## Nome da Solução
StockFácil — Sistema Web de Gestão de Estoque para Pequenos Negócios e E-commerces Varejistas

---

## Problema
Muitas pequenas empresas e e-commerces varejistas ainda controlam seu estoque por meio de planilhas manuais ou processos desorganizados, o que gera falta de confiabilidade nas informações armazenadas, inconsistências operacionais, dificuldade em identificar perdas, e erros em registros de entradas e saídas de produtos. Essa fragilidade compromete a eficiência do gerenciamento de estoque e dificulta análises auditoriais e a tomada de decisão em tempo real.

---

## Solução Proposta
O StockFácil resolve esse problema oferecendo uma plataforma web centralizada que substitui controles manuais por um sistema digital de gestão de estoque em tempo real. O sistema permite o cadastro estruturado de produtos, fornecedores e usuários, o registro de entradas e saídas com histórico completo e rastreável, e a atualização automática de saldos a cada movimentação. Para aumentar a confiabilidade das informações, todas as operações críticas utilizam transações atômicas no banco de dados (garantindo que nenhuma movimentação seja registrada de forma incompleta) e logs de auditoria estruturados registram ações como exclusões e alterações de estoque. Alertas automáticos de estoque mínimo e máximo, somados a um dashboard com indicadores em tempo real, permitem identificar rapidamente discrepâncias, perdas e riscos de ruptura, dando suporte direto a análises auditoriais e à gestão proativa do estoque.

---

## Diferencial Inovador
O diferencial está focado na facilidade de ultilizar, sem a necessidade de treinamentos.

---

## Potencial de Aplicação
A solução pode ser aplicada por:
- Pequenos comerciantes com lojas físicas e/ou virtuais (e-commerce);
- Empreendedores do varejo que precisam controlar entradas e saídas de produtos;
Equipes de almoxarifado e depósitos de microempresas;
- Gestores de microempresas que hoje utilizam planilhas desorganizadas;
- Equipes de estoque com múltiplos operadores que necessitam de controle de acesso por perfil (administrador, operador, visualizador);

---

## Tecnologias Utilizadas
- React.js + TypeScript (Frontend)
- Tailwind CSS (Estilização e responsividade)
- Node.js + Express.js (Backend / API RESTful)
- PostgreSQL 15 (Banco de dados relacional)
- Prisma ORM (Camada de acesso a dados)
- Redis (Cache de sessões e dashboard)
- JWT + bcrypt (Autenticação e segurança de senhas)
- Nginx (Proxy reverso e TLS termination)
- AWS (EC2, RDS, S3, CloudWatch) (Infraestrutura em nuvem)
- Docker + Docker Compose (Containerização)
- GitHub Actions (CI/CD)
- Swagger / OpenAPI 3.0 (Documentação de API)


---

## Possível contribuição científica ou tecnológica
No âmbito acadêmico, o projeto serve como estudo de caso aplicado de arquitetura de software em camadas (three-tier), práticas de RBAC (Role-Based Access Control), e estratégias de desempenho com cache distribuído (Redis), podendo subsidiar pesquisas em engenharia de software, sistemas de informação e gestão de operações. No âmbito social, o sistema democratiza o acesso a tecnologia de gestão profissional para microempreendedores que normalmente não têm orçamento para soluções ERP corporativas, contribuindo para a formalização e profissionalização da gestão de pequenos negócios brasileiros — alinhando-se também às exigências da LGPD quanto à proteção de dados pessoais. No âmbito comercial, a solução tem potencial de escalar como produto SaaS (Software as a Service), com possibilidade de monetização por assinatura e expansão futura para funcionalidades como integração com e-commerce e módulos financeiros, hoje fora do escopo inicial.

---

## Data de Registro
21/06/2026

---

## Autores
- André Rufino
- Gabriel Lima
- Igor
- Marcilene Mendes

---
