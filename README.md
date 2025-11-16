# 🧠💻 Sistema Especialista – Diagnóstico de Placa-mãe

Este projeto consiste em um Sistema Especialista desenvolvido em Python utilizando a biblioteca Experta para a materia de Inteligencia Artificial, que simula a lógica de diagnósticos realizada por placas-mãe durante o POST (Power-On Self Test).

O sistema recebe sintomas do computador — como bipes, status de LEDs, ventoinhas, cheiro de queimado e reinicialização em loop — e fornece automaticamente um diagnóstico provável do problema.

---

## 📌 Objetivo

Auxiliar usuários ou técnicos na identificação de falhas relacionadas à placa-mãe, CPU, memória RAM, BIOS ou placa de vídeo, com base em códigos sonoros e sinais físicos apresentados pelo computador.

---

## 🧩 Tecnologias utilizadas
| Tecnologia | Função |
|----------|--------|
| Python 3 | Linguagem principal |
| Experta (baseado em CLIPS) | Motor de inferência baseado em regras |
| Jupyter Notebook | Interface de execução e testes |

---

## 🚀 Como executar

1️⃣ Certifique-se de ter o Python 3.9+ instalado

2️⃣ Instale a biblioteca Experta:

```bash
pip install experta
```

3️⃣ Execute o Jupyter Notebook e rode as células do projeto:

```bash
jupyter notebook
```

## 🧠 Funcionamento do Sistema Especialista

O sistema trabalha com regras, divididas em dois tipos:

### 🔊 Diagnóstico com bipes (baseado em BIOS AMI/Gigabyte)

Nº de bipes	Diagnóstico provável
- 1	Erro de memória RAM
- 2	Erro de paridade da memória
- 3	Erro de endereço na memória básica (64K)
- 4	Mau funcionamento do RTC
- 5	Erro na CPU
### 🖥️ Diagnóstico sem bipes (análise física)
| Sintoma | Possível causa |
|----------|--------|
| Liga + tela preta + ventoinhas não giram + LEDs acesos | Falha na placa de vídeo ou BIOS |
| Liga + tela preta + ventoinhas giram |	Problema na RAM ou CPU |
| Reinicia em loop	| BIOS corrompida, térmica ou energia |
| Nada liga + cheiro de queimado |	Curto na placa-mãe | 

## 🎯 Modo Interativo 

O notebook contém um modo em que o sistema faz perguntas ao usuário para coletar informações e gerar o diagnóstico automaticamente:

```bash
engine = DiagnosticoPlacaMae()
engine.reset()
engine.declare(SintomasComputador(**dados))
engine.run()
```

## 🧪 Exemplo de execução

Entrada do usuário:
```bash
A placa-mãe está emitindo bipes? → Sim
Quantidade de bipes: 5
```

Saída:
```bash
Diagnóstico: CPU error. Erro na CPU
```
## 📁 Estrutura do Projeto
```bash
📂 sistema_especialista_placa_mae
│
├── sistema_experto.ipynb   # Notebook com o código completo do projeto
├── README.md               # Documentação (este arquivo)
```
## 🛠️ Melhorias futuras

- Interface gráfica para facilitar uso por leigos

- Expansão da base de regras com mais códigos de fabricantes (Dell, ASUS, MSI)

- Exportação do diagnóstico como relatório PDF

- Suporte a diagnóstico de outros componentes (HD/SSD, PSU)

## 👨‍💻 Autor

Desenvolvido por **Diogo Augusto** como prática de desenvolvimento de sistemas especialistas com Python para a materia de **Inteligencia Artificial**.