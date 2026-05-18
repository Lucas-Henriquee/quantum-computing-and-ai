# Implementação e Análise do Algoritmo de Estimativa de Fase Quântica via QFT

Projeto desenvolvido para a disciplina **Computação Quântica e Inteligência Artificial (FIS088)**.

## Descrição

Este repositório contém a implementação e análise do algoritmo de **Estimativa de Fase Quântica** (*Quantum Phase Estimation*, QPE) utilizando o framework **Qiskit** em Python.

O projeto inclui:

- implementação manual da **Transformada de Fourier Quântica (QFT)**;
- implementação da **QFT inversa**;
- construção completa do circuito **QPE**;
- análise do mecanismo de *phase kickback*;
- validação numérica da identidade $QFT \cdot QFT^\dagger = I$;
- comparação entre distribuições teóricas e resultados obtidos por simulação;
- análise da relação entre número de qubits de contagem, precisão da estimativa e probabilidade de sucesso.

Os experimentos foram realizados utilizando o backend `AerSimulator` do Qiskit.

## Estrutura do Repositório

```text
.
├── FIS088_QPE_Final_Report.pdf
├── FIS088_QPE_Project_Pitch.pdf
└── quantum_phase_estimation_qiskit.ipynb
```

## Arquivos

### `quantum_phase_estimation_qiskit.ipynb`

Notebook principal contendo a implementação da QFT, da QFT inversa, do circuito QPE, simulações, histogramas, comparação teoria vs. simulador e análise de precisão.

### `FIS088_QPE_Final_Report.pdf`

Relatório final em formato artigo contendo fundamentação teórica, derivação matemática, descrição do algoritmo, implementação, resultados experimentais e comparação com a teoria apresentada por Nielsen & Chuang.

### `FIS088_QPE_Project_Pitch.pdf`

Proposta inicial do projeto.

## Principais Resultados

### Caso exato — porta T

Para o autovetor `|1>`, a porta T satisfaz:

$$
T|1\rangle = e^{2\pi i(1/8)}|1\rangle
$$

Nesse caso, o QPE recupera:

$$
\phi = \frac{1}{8}
$$

com probabilidade aproximadamente igual a 100% utilizando 3 qubits de contagem.

### Caso não exatamente representável — phi = 1/3

Para:

$$
\phi = \frac{1}{3} = 0.010101\ldots_2
$$

o algoritmo produz uma distribuição de probabilidades centrada na melhor aproximação binária disponível para cada número de qubits de contagem `t`.

Os resultados mostram que o erro decai aproximadamente como:

$$
\mathcal{O}\left(\frac{1}{2^t}\right)
$$

em concordância com o Teorema 5.1 de Nielsen e Chuang.

## Referências

- Michael A. Nielsen, Isaac L. Chuang.  
  *Quantum Computation and Quantum Information*.  
  Cambridge University Press, 2010.

- Equipe Qiskit.  
  *Qiskit Textbook — Learn Quantum Computation Using Qiskit*.  
  IBM Quantum, 2023.  
  Disponível em:  
  https://github.com/Qiskit/textbook/tree/main/notebooks/ch-algorithms  
  Acesso em: 18 de maio de 2026.

- Qiskit Documentation:  
  https://qiskit.org/