# Proposta de Dissertação UFPel 2019-1

## Escalonador de Memórias Transacionais para arquitetura NUMA

Michael Alexandre Costa

### Resumo

Memórias Transacionais (MT) são apresentadas como alternativas à sincronização com locks e monitores. MTs utilizam conceitos de transações semelhantes aos existentes em bancos de dados. Estes conceitos permitem ao programador escrever programas paralelos em mais alto nível, reduzindo a complexidade da sincronização.

Ambientes altamente paralelos possuem potencial para um alto número de conflitos entre as transações executadas. Para solucionar estes conflitos e manter consistente a execução da aplicação, sistemas com Software Transactional Memory}~(STM) cancelam uma das transações conflitantes e executam ela novamente após o término da outra transação.

Cancelar as transações conflitantes é eficiente para manter a consistência da aplicação, mas geram um custo de processamento muito elevado. Para reduzir este custo, estudos atuais utilizam escalonadores de transações em STM. Os escalonadores atuam identificando transações conflitantes e manipulando as threads em execução para minimizar o número de conflitos futuros.

Estes estudos mostram-se promissores, permitindo reduzir consideravelmente o overhead de execução existente em ambientes de alta contenção. Ajustando estas políticas de escalonamento para avaliar a arquitetura utilizada pela aplicação, as aplicações de STM podem ter um ganho de desempenho ainda maior.

Arquiteturas do tipo Non Uniform Memory Access (NUMA) oferecem maior capacidade de paralelismo quando comparadas as arquiteturas do tipo Uniform Memory Access (UMA). Porém, os escalonadores e bibliotecas de STM possuem suas aplicações e seu foco de estudo em arquiteturas UMA.

Considerar as diferenças entre as arquiteturas existentes pode fornecer um escalonador de STM que otimiza a execução da aplicação. Esta avaliação da arquitetura deve ser feita pelo escalonador, assim, a biblioteca de STM se mantém simples para o programador, o que facilita o desenvolvimento de programas paralelos complexos.

O objetivo deste trabalho é propor a modificação de um escalador de STM, estendendo este para que em tempo de execução avalie as características de uma arquitetura NUMA. Com o conhecimento sobre a arquitetura o escalonador pode otimizar o tempo de execução, executando as transações no processador que obtenha a menor latência de acesso à memória.
