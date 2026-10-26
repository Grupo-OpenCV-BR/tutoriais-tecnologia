# OpenVX

**OpenVX** é um padrão aberto do Khronos Group para aceleração de visão computacional. Sua API representa operações e dependências como um grafo, permitindo que uma implementação otimize a execução para CPUs, GPUs, DSPs ou outros processadores disponíveis. [Apresentação oficial do OpenVX](https://www.khronos.org/openvx/).

## Quando usar

Vale avaliar OpenVX em sistemas embarcados, robótica, inspeção visual e aplicações com requisitos de latência ou consumo de energia. A programação por grafos ajuda a expressar o pipeline completo.

## Como começar

1. Escolha uma implementação compatível com seu dispositivo, como a incluída no [MIVisionX](mivisionx.md).
2. Identifique os nós necessários e os formatos das imagens.
3. Comece com um grafo pequeno: entrada → processamento → saída.
4. Valide os resultados e meça a execução no hardware de destino.

## Compatibilidade

O padrão precisa de uma implementação para executar. A versão, os conjuntos de recursos e as extensões suportadas determinam quais operações estarão disponíveis, incluindo recursos de redes neurais e importação [NNEF](nnef.md). Consulte o [registro oficial de especificações e extensões](https://www.khronos.org/registry/OpenVX/).

A portabilidade da API não garante o mesmo desempenho ou a presença de todas as extensões em dispositivos diferentes.

[Voltar ao panorama de aceleração](aceleracao.md).
