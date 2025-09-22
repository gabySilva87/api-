# Firebase Studio
Objetivo: O projeto é uma aplicação web para a empresa de logística "LogiDesk". O foco é fornecer aos motoristas uma interface para autenticação e visualização de suas rotas de entrega pendentes.

Estrutura e Funcionalidades:

Página de Login (/):

Apresenta um formulário de login com um design limpo e moderno, solicitando Nome e CPF do motorista.
Utiliza uma Server Action do Next.js para capturar e validar os dados do formulário de forma segura no servidor.
Fluxo de Autenticação:

A Server Action (login em actions.ts) envia as credenciais para uma API interna (/api/login).
A API (/api/login/route.ts) se conecta a um banco de dados MySQL (usando as credenciais do seu arquivo .env.local).
Ela verifica se existe um motorista na tabela tb_motorista que corresponda ao nome e CPF fornecidos.
Se as credenciais estiverem corretas, a API retorna uma resposta de sucesso.
O frontend, ao receber a confirmação, redireciona o motorista para a página do painel de controle (/dashboard).
O sistema também inclui tratamento detalhado de erros, exibindo mensagens claras para o usuário em caso de falha na conexão com o banco ou credenciais inválidas.
Dashboard do Motorista (/dashboard):

Esta é uma página acessível apenas após o login.
Mostra uma saudação de boas-vindas e o layout principal da aplicação.
Notificações de Rotas: O componente principal (RouteNotifications) busca e exibe dinamicamente as encomendas pendentes.
API de Rotas: A página do dashboard chama a API /api/routes, que consulta a tabela tb_encomenda no banco de dados e retorna todas as encomendas com o status "pendente".
A página também possui um card estático de "Próxima Entrega", que pode ser desenvolvido para exibir a primeira rota da lista.
Tecnologias Utilizadas:

Framework: Next.js 15 com App Router (Renderização no Servidor).
Linguagem: TypeScript.
UI e Estilização: Tailwind CSS e componentes shadcn/ui com um tema personalizado (dark-mode com detalhes em amarelo/âmbar).
Backend e API: Server Actions e Route Handlers do Next.js.
Banco de Dados: MySQL, acessado através da biblioteca mysql2.
Em suma, criamos a espinha dorsal de um portal de motoristas funcional e seguro, com um fluxo de autenticação robusto e uma base sólida para a exibição de dados dinâmicos a partir de um banco de dados real
