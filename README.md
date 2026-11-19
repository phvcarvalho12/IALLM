# Projetos de IA LLM — PUC-SP

Este diretório contém dois notebooks independentes da disciplina de Inteligência Artificial:

1. **[IA LLM Web Services com Ollama local](PUCSP_CS_AI_16_AI_LLM_Local_Ollama.ipynb)** — edição local, sem chaves nem chamadas pagas à OpenAI/Hugging Face.
2. **[Projeto 9 — Calculadora e Avaliador de Expressões](Projeto_09_Agente_Calculadora_Sem_Chave_OpenAI.ipynb)** — agente que interpreta perguntas matemáticas e delega cálculos seguros para Python/SymPy.

## IA LLM Web Services com Ollama

Autores: **Pedro Henrique Vianna Carvalho (RA00333196)** e **Helio Masaru Sueta (RA00333246)**.

O notebook percorre chamadas HTTP/JSON, chat, histórico de conversa, streaming, temperatura, respostas estruturadas com validação, uso controlado de ferramentas SQL, análise opcional de imagens e benchmark de latência. As inferências de texto são executadas pelo Ollama usando o modelo local `qwen2.5:3b`; não é necessário preencher os Secrets `OPENAI_API_KEY` ou `HF_KEY`.

### Executar no Windows

1. Instale e abra [Ollama para Windows](https://ollama.com/download).
2. No PowerShell, baixe o modelo:
   ```powershell
   ollama pull qwen2.5:3b
   ```
3. Abra `PUCSP_CS_AI_16_AI_LLM_Local_Ollama.ipynb` no Jupyter ou VS Code.
4. Execute as células em ordem. A primeira célula instala as bibliotecas Python necessárias; mantenha o serviço do Ollama ativo.

### Executar no Google Colab

1. No Colab, use **Arquivo → Fazer upload de notebook** e selecione `PUCSP_CS_AI_16_AI_LLM_Local_Ollama.ipynb`.
2. Conecte-se a um ambiente de execução e execute as células de cima para baixo.
3. A célula de inicialização instala o Ollama e baixa `qwen2.5:3b` no ambiente temporário do Colab.

No Colab, `localhost` é o ambiente remoto do próprio Colab, não o computador Windows. O download do Ollama e do modelo requer conexão e espaço em disco. Ao encerrar ou reiniciar a sessão, será necessário iniciar o serviço e baixar o modelo novamente. A disponibilidade e os limites de GPU/tempo dependem da conta e da sessão do Colab.

### Modelo de visão opcional

A demonstração de imagem é opcional e vem desativada até que `IMAGE_PATH` seja preenchido. Ela baixa `qwen2.5vl:7b`, que ocupa mais espaço e pode exigir mais memória. A geração de imagens não está implementada nesta edição.

## Projeto 9 — Calculadora e Avaliador de Expressões

O Projeto 9 usa um modelo de linguagem para interpretar a solicitação e selecionar uma ferramenta matemática. O cálculo é realizado por Python com SymPy. Para instruções de instalação, execução, segurança e testes, consulte o próprio notebook e seu histórico de autoria.

## Segurança e chaves

- Não cole tokens ou chaves de API no código, notebooks ou README.
- A edição local de IA LLM deste diretório não usa chaves OpenAI/Hugging Face.
- A inferência local evita cobrança de API, mas utiliza recursos do computador ou da sessão do Colab.
- As consultas SQL do notebook de IA LLM são configuradas para somente leitura.
