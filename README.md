# Project Instructions — Prontuário & Agenda (Saúde)

## Objetivo
Construir um app web de prontuário médico + agenda de pacientes, com autenticação, CRUD completo e trilha de auditoria.

## Requisitos Funcionais
1) Pacientes: cadastro, busca, edição, arquivamento.
2) Atendimentos (encounters): data/hora, motivo, histórico, exame psíquico/ físico, hipóteses diagnósticas (CID-10), plano, anexos.
3) **Medicamentos**: nome, dose, via, frequência, datas (início/fim), indicação, prescrito por, “ativo”.
4) **Exames laboratoriais**:
   - Pedidos (lab_orders): exame, prioridade, data, status.
   - Resultados (lab_results): valor, unidade, referência, flag, arquivo anexo.
5) Agenda: criação e gestão de consultas, confirmação/cancelamento, status (scheduled/confirmed/no-show).
6) Auditoria: quem alterou o quê e quando.
7) Exportar PDF (evolução, prescrição).
8) RBAC simples: admin, profissional (leitura/escrita), recepção (agenda/pacientes).

## Requisitos Não Funcionais
- Next.js 14 (App Router), TypeScript, Tailwind, shadcn/ui.
- Prisma + PostgreSQL; variáveis em `.env`.
- Testes mínimos (unitários para utilitários e e2e leve).
- Acessibilidade (labels, aria), i18n pt-BR prontos para crescer.

## Diretrizes de Código
- Padrão de pastas “feature based”: `app/`, `server/`, `components/`, `lib/`, `db/`.
- Schemas Zod para inputs; React Hook Form nos formulários.
- Server Actions para CRUD e/ou rotas em `app/api/*`.
- Componentes UI reusáveis (Form, Modal, Table, Badge, StatusDot).

## Entregas (MVP)
- Auth pronta.
- Tabelas e migrações geradas.
- Páginas:
  - `/dashboard`
  - `/pacientes` (listar/criar/editar)
  - `/prontuario/[id]` (abas: Dados, Atendimentos, Medicamentos, Exames, Arquivos, Auditoria)
  - `/agenda` (calendário semanal + criar/editar consulta)
- Export PDF básico (atendimento + prescrição).

## Qualidade
- ESLint/Prettier configurados.
- Mensagens de commit claras.
- Scripts npm para dev/build/test/db.

## Passos Automáticos
1) Inicializar o app Next.js + Tailwind + shadcn.
2) Adicionar Prisma, criar schema e rodar `prisma migrate`.
3) Implementar Auth.js (credenciais).
4) Criar páginas e componentes base.
5) Implementar CRUDs e validações.
6) Adicionar auditoria (middleware + tabela).
7) Export PDF.
8) Seed de dados e testes básicos.

## Observações de Segurança
- Sanitizar upload; limitar tipos de arquivo.
- Nunca logar dados sensíveis no client.
- RBAC checado no servidor.


