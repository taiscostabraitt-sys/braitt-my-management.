# BRAITT | My Management — proposta do produto

## Propósito
Um centro pessoal de comando para organizar o tempo, executar prioridades, conduzir projetos e acompanhar resultados profissionais e pessoais, com identidade visual executiva em grafite, marfim e dourado discreto.

## Usuária principal e plataformas
Gestora com rotina multiáreas, necessidade de separar trabalho, equipe, desenvolvimento de carreira e família. A aplicação deverá ser responsiva, funcionando em computador e celular.

## Módulos
1. Painel executivo: tarefas do dia, atrasos, taxa geral de conclusão, três prioridades e projetos.
2. Atividades: cadastro/edição/exclusão, prioridade, prazo, horário, área, duração e conclusão.
3. Agenda: calendário mensal com atividades por data e horário.
4. Projetos: cadastro, descrição, área, prazo e estado.
5. Delegação: responsável vinculado a uma tarefa e acompanhamento do seu estado.
6. Carreira/estudos: tarefas e metas específicas para desenvolvimento profissional.
7. Pessoal/família: tarefas e metas pessoais.
8. Metas/indicadores: acompanhamento de objetivos mensuráveis e KPIs básicos.
9. Assistente: briefing e sugestões determinísticas de prioridades.
10. Dados: exportação/importação JSON e limpeza local.

## Como usar o protótipo
Abrir `index.html` em um navegador moderno. Os registros são guardados por localStorage naquele navegador. Para transferi-los, utilizar Exportar dados e Importar backup JSON. O arquivo é autocontido e não requer instalação de servidor.

## Limites da V1
A V1 é um protótipo individual. Não oferece autenticação, sincronização entre dispositivos, edição colaborativa, notificações, envio de atividades delegadas, integração ativa com Google Calendar, nem IA generativa. A lista de atividades iniciais é apenas ilustrativa. Não guardar dados sensíveis de terceiros.

## Arquitetura proposta para evolução
- Frontend: React/Next.js responsivo e Progressive Web App (PWA).
- Backend: API protegida com PostgreSQL hospedado e autenticação.
- Segurança: controles de acesso por função, criptografia em trânsito, backups, logs, políticas de retenção, segregação entre dados pessoais e corporativos, LGPD.
- Integrações: Google Calendar via OAuth e sincronização bidirecional com tratamento de conflitos; push notifications; tarefas compartilhadas por equipe mediante consentimento/permissão.
- IA: motor de sugestões (V1) evoluindo para assistente com modelo via backend, consentimento por fonte, limitação de acesso e confirmação humana para reagendar ou delegar.

## Roadmap priorizado
**Fase 1 — MVP individual:** formulários robustos, filtros, agenda, projetos, metas, indicadores, exportação (incluído neste protótipo).
**Fase 2 — Produção segura:** login, banco de dados, acesso em vários aparelhos, backups automáticos, PWA e notificações.
**Fase 3 — Colaboração e integrações:** membros, permissões, delegação real, Calendar e trilha de auditoria.
**Fase 4 — IA contextual:** planejamento de blocos de foco, resumo semanal, sugestões com base em agenda e tarefas, aprovação de ações.

## Critérios de sucesso
- Registro de tarefas em menos de 30 segundos.
- Visibilidade diária das três prioridades.
- Separação clara de vida pessoal, carreira, projetos e trabalho.
- Visão explícita de responsáveis, prazos e atrasos.
- Acompanhamento semanal de conclusão, carga de trabalho e andamento de metas.


## Versão 1.1: voz, alocação e radar
- Gravação por reconhecimento de voz disponível apenas em navegadores compatíveis, com permissão de microfone; pode exigir HTTPS/localhost. Não há gravação ou armazenamento de áudio pelo aplicativo. Dependendo do navegador, a transcrição pode depender de serviço externo do fornecedor.
- Intérprete local baseado em padrões (não é IA generativa): cria tarefas, classifica prioridade e registra hábitos por frases identificáveis.
- Agenda automática escolhe a primeira janela livre em até 14 dias segundo blocos locais, duração informada, horário de trabalho e limite de carga. Sem acesso a calendários externos, não garante ausência de conflitos reais.
- Radar informa janelas livres, conflitos, excesso de compromissos e mínimo semanal de exercícios. A expressão dia estressante é uma inferência de carga e conflitos, não avaliação clínica de estresse.
- Metas programadas: sono 6–8 h; atividade 5x ideal / 3x mínimo por semana; água 2 L/dia; estudos 2 h úteis e 4–6 h nos fins de semana; transição de carreira 90 min/dia; leitura 5 páginas/dia com +2 páginas a cada 14 dias; podcast 3x/semana como sugestão; oração/devocional diariamente e prática de aprendizado 15 min/dia.
- Para evitar inserção manual recorrente, metas são geradas por regras e os registros podem ser feitos por voz, mas conclusão real requer confirmação do usuário ou integração com fonte autorizada.
- Limitações: sem lembretes em segundo plano, sem push quando fechado, sem sincronização, sem IA conversacional e sem conexão com Google Calendar nesta versão.


## Versão 1.2 — Foco 80/20
- Caixa de entrada para colar várias pendências sem categorização inicial.
- Triagem sugerida: executar, planejar, delegar ou adiar/eliminar.
- Nota de impacto ajustável (1 a 5) e indicação de possibilidade de delegação.
- Três focos de alto impacto e aviso de excesso de tarefas para o dia.
- Alocação de tarefas selecionadas nos horários disponíveis usando o planejamento local.
- As recomendações são heurísticas; não enviam mensagens, não transferem responsabilidades e não excluem tarefas automaticamente.
- A entrada de voz continua disponível no módulo Rotina automática, com as limitações de navegador explicadas anteriormente.


## Versão 1.3: Dashboard de autoanálise

A primeira aba passa a apresentar análises diária, semanal e mensal: execução planejada, prioridades de maior impacto, pendências atrasadas, delegações, estimativa de tempo, riscos de sobrecarga e hábitos registrados (sono, água, exercício, estudos e carreira). O painel apresenta recomendações automáticas baseadas em regras e informa quando faltam dados; não dispõe de IA generativa nem de notificações em segundo plano. Conclusões registradas a partir desta versão passam a ter carimbo de data/hora para evolução dos indicadores. Ainda é necessário implementar a reformulação solicitada das demais abas, sincronização com nuvem e Google Calendar.
