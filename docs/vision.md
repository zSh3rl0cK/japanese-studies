# Visão e Escopo do Projeto: Nihongo Satori (日本語悟り)

---

## 1. Definições e Glossário de Hierarquia do Conteúdo

Para garantir consistência nos requisitos e no modelo de dados, a estrutura pedagógica do aplicativo é dividida estritamente da seguinte forma:

* **Nível:** Grau macro de proficiência baseado no exame oficial JLPT (*Japanese-Language Proficiency Test*). Exemplo: *JLPT N5*.
* **Módulo:** Divisão temática principal dentro de um nível. Exemplo: *Módulo 1 – Fundamentos do N5 e Cortesia*.
* **Unidade:** Agrupamento de conteúdos gramaticais correlatos dentro de um módulo. Exemplo: *Unidade 2 – Partículas de Tópico e Sujeito (は e が)*.
* **Lição (ou Seção):** A unidade mínima de estudo do aluno, composta por **uma aula teórica** seguida por uma **bateria de exercícios de fixação e aplicação**.

---

## 2. Visão Geral do Produto

### 2.1 Problemática

Alunos autodidatas de língua japonesa frequentemente travam na transição do vocabulário decorado para a formulação de frases reais. Aplicativos populares focam em memorização mecânica por repetição espaçada, sem ensinar a lógica estrutural da língua, as diferenças essenciais entre registros de formalidade (*Teineigo* / Polido vs. *Casual*) e os motivos culturais por trás de cada construção gramatical.

### 2.2 Proposta de Valor

O **Nihongo Satori** atua como um tutor estruturado que ensina o "porquê" das regras gramaticais e a aplicação prática contextualizada. No MVP, essa proposta é validada por meio de:

1. **Aulas teóricas detalhadas** cobrindo nuances culturais e alertas de erros comuns.
2. **Exercícios de construção conversacional encadeada** (usando banco de blocos de palavras).
3. **Explicabilidade imediata nos erros**, apontando exatamente o motivo do equívoco gramatical ou de formalidade.
4. **Transição suave** do uso do *Rōmaji* para os caracteres nativos (*Hiragana* e *Katakana*).

### 2.3 Análise Competitiva

| Plataforma | Pontos Fortes | Lacunas / Pontos Fracos | Diferencial do Nihongo Satori |
| --- | --- | --- | --- |
| **Duolingo** | Alta gamificação e retenção de hábito | Não explica regras gramaticais; exercícios repetitivos e descontextualizados | Aulas expositivas do "porquê", foco em registros formal vs. informal |
| **Anki** | Memorização por repetição espaçada extremamente eficiente | Curva de aprendizado alta; exige criação manual de baralhos; sem trilha pedagógica | Trilha guiada e pronta, com exercícios dinâmicos e explicação de contexto |
| **Bunpro** | Foco completo em gramática para exames JLPT | Interface densa e complexa; explicações totalmente em inglês | Explicações em Português (PT-BR) voltadas para lusófonos com exemplos práticos |

---

## 3. Personas e Políticas de Acesso

### 3.1 Personas

1. **Lucas (Iniciante do Zero – 19 anos):** Estudante universitário, fã de cultura pop japonesa, nunca estudou o idioma. Não lê *Kana* (*Hiragana/Katakana*) e precisa de auxílio com *Rōmaji* no início para não desistir.
2. **Safira (Autodidata Estagnada – 24 anos):** Já conhece os alfabetos básicos, mas sente dificuldades para estruturar diálogos e compreender quando usar a linguagem polida (*Teineigo*) ou casual. Quer entender a lógica profunda para falar com confiança.
3. **Pedro (Autor & Operador do Sistema):** Desenvolvedor e curador do conteúdo. Precisa de um fluxo simples para inserir aulas, cadastrar questões com metadados de erro e acompanhar a telemetria de aprendizado dos alunos.

### 3.2 Políticas de Acesso e LGPD

* **Público Alvo e Restrição de Idade:** Exclusivamente para **maiores de 18 anos** no lançamento beta. Esta decisão simplifica a conformidade com a LGPD (evitando as exigências do Art. 14 relativas a dados de menores).
* **Modalidade de Onboarding:** Cadastro fechado/convite restrito para a fase de testes e validação técnica do MVP.

---

## 4. Objetivos e Métricas de Sucesso (KPIs)

O projeto possui dois pilares de objetivos: validação do produto pedagógico e evolução em engenharia de software.

### 4.1 Piloto de Produto e Aprendizado (Grupo Beta com 10 a 15 Alunos)

* **Métrica Principal (North Star):** **Taxa de Conclusão de Seção de Primeira Tentativa ≥ 70%**.
* *Definição:* Porcentagem de alunos que atingem o critério de aprovação (≥ 80% de acertos) na primeira tentativa de uma lição.
* *Fonte dos dados:* Banco de dados de logs de tentativas.


* **Retenção Semanal (Engagement):** **≥ 60% dos usuários beta** concluindo pelo menos 2 lições por semana durante o período de testes de 4 semanas.
* **Eficácia do Reforço Pedagogico:** **Redução de ≥ 40% na taxa de erro** ao refazer lições não concluídas.
* *Definição:* Comparação entre a taxa de erro da 1ª tentativa e da 2ª tentativa (utilizando questões equivalentes do banco de reserva, evitando memorização visual exata).



### 4.2 Métricas de Engenharia de Software (Projeto Pessoal)

* **Cobertura de Testes Automatizados:** **≥ 80% de cobertura** nos módulos críticos de aplicação de regras de progressão, validação de respostas e cálculo de estatísticas.
* **Automação de CI/CD:** Pipeline de compilação, execução de testes e deploy automático (Vercel) concluído em **menos de 3 minutos** por *commit*.
* **Estabilidade:** **Zero erros não tratados (HTTP 500)** registrados durante a fase de testes do grupo piloto.

---

## 5. Escopo do MVP (Matriz MoSCoW)

### 5.1 Must-Have (Essencial para a Validação da Proposta de Valor)

#### Autenticação & Gestão de Perfil

* Cadastro e login de usuários (restrito a maiores de 18 anos).
* Perfil básico do aluno com histórico de lições concluídas.

#### Conteúdo do MVP (Dimensionamento Reduzido)

* **JLPT N5 – Módulo 1:** Alfabetização inicial em *Kana* (*Hiragana* e *Katakana*) + 5 Unidades Gramaticais Essenciais:
1. Estrutura básica de frases (SOV) e Verbo *Desu* (です/だ).
2. Registros de formalidade: Linguagem Polida (*Teineigo*) vs. Casual.
3. Partículas de Tópico (*Wa* - は) e Sujeito (*Ga* - が).
4. Partículas de Objeto e Direção (*O* - を, *Ni* - に, *De* - で).
5. Perguntas e Negação (*Ka* - か, *Dewa Arimasen* / *Ja Nai*).


* **Produção do Conteúdo:** Criado pelo autor do projeto (com auxílio de LLMs para geração de rascunhos e revisão pedagógica manual prévia).

#### Estrutura de Aulas & Exercícios

* **Aulas Expositoras:** Explicação da regra, o "porquê" cultural/gramatical e tabela comparativa de formalidade.
* **Suporte Pedagógico de Leitura:** Exibição inicial em *Rōmaji* com opção de ocultação gradual à medida que o aluno avança no estudo de *Kana*.
* **Player de Áudio:** Reprodução de áudio nativo para vocabulário e frases de exemplo.
* **Formatos Determinísticos de Exercício:**
1. *Banco de Blocos (Word Bank):* Ordenação de blocos em *Kana/Rōmaji* para tradução e montagem de frases.
2. *Construção Conversacional por Blocos:* Montagem de minidiálogos encadeados (3+ falas) escolhendo a resposta/registro correto.
3. *Lacunas com Múltipla Escolha:* Seleção da partícula ou conjugação adequada ao contexto de formalidade indicado.


* **Feedback Imediato & Explicabilidade:** Mensagem explicativa ao errar, indicando o motivo específico da falha (ex.: "Neste contexto, o uso do registro casual com um superior é inadequado").

#### Regra de Progressão, Reforço e Telemetria (Infraestrutura Invisível)

* **Regra de Aprovação:** Exigência de **≥ 80% de acerto** na bateria de 10 questões para concluir a lição.
* **Mecanismo de Falha e Reforço:** Se o aluno tirar < 80%, a lição é marcada como "Em Reforço". Na nova tentativa, o sistema sorteia novas questões do banco e adiciona 2 questões focadas na categoria onde o aluno cometeu mais erros.
* **Registro Detalhado de Tentativas (Telemetria):** Cada resposta é salva no banco de dados com a tag da categoria do erro (*Partícula*, *Conjugação*, *Registro de Cortesia*, *Vocabulário*).

---

### 5.2 Should-Have (Próximas Prioridades Pós-MVP)

* **Revisão Inteligente Personalizada:** Módulo de revisão gerado automaticamente com base no histórico de tags de erro salvas no banco de dados.
* **JLPT N5 – Módulo 2:** Expansão do conteúdo para cobrir a segunda metade do nível N5 (Adjetivos, Verbos de Existência *Iru/Aru*, Passado).
* **Mecanismos de Hábito:** Contagem de dias consecutivos (*Streak*) e acúmulo de pontos de experiência (XP).
* **Digitação Direta com Auto-Kana (IME Integrado):** Permitir que o aluno digite em *Rōmaji* no teclado e o campo converta automaticamente para *Hiragana/Katakana* em tempo real.

---

### 5.3 Could-Have (Médio Prazo / Evolução)

* **Camada Social e Perfil Público:** Ranking entre amigos e personalização simples de perfil (avatar e bio).
* **Treino de Escrita Manual:** Reconhecimento do desenho de traços para *Kana* e *Kanji* em telas sensíveis ao toque.
* **Ligas e Torneios:** Classificação semanal por pontos acumulados.

---

### 5.4 Won't-Have (Fora do Escopo Inicial)

* Monetização, assinaturas ou processamento de pagamentos dentro do aplicativo.
* Mural de metas pessoais customizáveis digitadas livremente pelo usuário.
* Conteúdo avançado cobrindo os níveis JLPT N3, N2 e N1.
* Reconhecimento de voz para avaliação de pronúncia (devido à inconsistência do suporte da *Web Speech API* entre navegadores).
* Tutores humanos ao vivo ou correção manual de textos livres não estruturados.
* Suporte a usuários menores de 18 anos.

---

## 6. Posição de Produto sobre Correção de Respostas

Para evitar a complexidade técnica de processamento de linguagem natural (NLP) e incertezas no MVP, **todas as correções serão 100% fechadas e determinísticas**:

1. **Tradução e Formação de Frases:** Serão realizadas prioritariamente por **Banco de Blocos de Palavras (Word Bank)**, garantindo que a combinação de respostas pertença a um conjunto finito e validável.
2. **Exercícios de Digitação (Quando aplicável):** Utilizarão uma **lista restrita de variações aceitas** previamente cadastradas no banco de dados (exemplo de aceitação simultânea: `わたしは` e `私 は`).

---

## 7. Restrições e Premissas do Projeto

* **Capacidade de Desenvolvimento:** 1 Desenvolvedor (Pedro Henrique) com dedicação estimada em **10 a 12 horas semanais**, utilizando IAs gerativas como assistentes de codificação e rascunho de conteúdo.
* **Orçamento:** **R$ 0,00 (Nulo)**. A infraestrutura utilizará exclusivamente os planos gratuitos das plataformas:
* Hospedagem e CI/CD: Vercel (Uso não comercial).
* Banco de Dados: Supabase / MongoDB Atlas (Free Tier).
* Repositório e Automações: GitHub Actions.


* **Plataforma Alvo:** Aplicação Web Responsiva (*Mobile-First*), acessível via navegadores modernos de smartphones e computadores.
* **Idioma da Interface:** Português (PT-BR).
* **Licenciamento:**
* Código-fonte do projeto: Licença **MIT**.
* Conteúdo pedagógico original: Licença **Creative Commons (CC BY-NC-SA 4.0)**, garantindo originalidade e proibindo cópia direta de livros didáticos comerciais.