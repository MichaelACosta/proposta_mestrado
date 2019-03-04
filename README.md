# Proposta de Dissertação UFPel 2019-1

## Escalonador de Memórias Transacionais para arquitetura NUMA

Michael Alexandre composta

### Resumo

Memórias Transacionais (TM) são apresentadas como alternativas à sincronização com locks e monitores. Estes utilizam conceitos de transações semelhantes aos existentes em bancos de dados. Estes conceitos permitem ao programador escrever programas paralelos em mais alto nível, reduzindo a complexidade da sincronização.

Em ambientes altamente paralelos existe um alto número de conflitos entre as transações executadas. Para solucionar estes conflitos e manter consistente a execução da aplicação, sistemas com Software Transactional Memory}~(STM) cancelam uma das transações conflitantes e executam ela novamente após o termino da outra.

Cancelar as transações conflitantes são eficientes para manter a consistência da aplicação, mas geram um custo de processamento muito alto. Para reduzir este custo, estudos atuais utilizam escalonadores de STM. Os escalonadores atuam identificando transações conflitantes e manipulando as threads em execução para minimizar o número de conflitos.

Estes estudos mostram-se promissores, reduzindo consideravelmente o overhead de execução existente em ambientes de alta contenção. Por outro lado, os escalonadores não consideram a arquitetura na qual a aplicação esta executando.

Arquiteturas Non Uniform Memory Access (NUMA) fornecem maior capacidade de paralelismo mas possuem características distintas das arquiteturas Uniform Memory Access (UMA), onde os escalonadores e bibliotecas de STM são estudados e aplicados atualmente.

Considerar as diferenças entre as arquiteturas existentes podem fornecer um escalonador de STM que otimiza a execução da aplicação, sendo transparente ao programador da aplicação, o que prove a este maior facilidade ao desenvolver programas paralelos complexos.

O objetivo deste trabalho é propor a modificação de um escalador de STM, estendendo este para que em tempo de execução avalie as características da arquitetura NUMA. Assim, alem de minimizar o número de conflitos existentes em STMs, será possível tirar o melhor desempenho em uma arquitetura com alto nível de paralelismo.
