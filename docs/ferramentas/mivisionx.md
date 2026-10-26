# MIVisionX — visão computacional e inferência na AMD

**MIVisionX** é um conjunto de bibliotecas, utilitários e aplicações para visão computacional e inferência. Inclui a implementação AMD de [OpenVX](openvx.md) e um compilador e otimizador de modelos com suporte aos formatos ONNX e [NNEF](nnef.md). [Documentação oficial do MIVisionX](https://rocmdocs.amd.com/projects/MIVisionX/en/latest/index.html).

## Quando usar

Avalie o toolkit para integrar processamento de imagens e inferência em um pipeline por grafos. Ele também é um caminho para estudar uma implementação concreta de OpenVX.

## Como começar

1. Confira os pré-requisitos e o backend adequado ao seu hardware na documentação oficial.
2. Execute uma aplicação de exemplo e verifique entradas e saídas.
3. Ao importar um modelo, confira os operadores suportados e compare os resultados com o framework de origem.
4. Meça o pipeline completo no dispositivo de destino.

O toolkit dispõe de caminhos para diferentes plataformas; o suporte efetivo depende da versão, dos componentes e do backend selecionados. Não presuma compatibilidade apenas pelo fabricante da GPU.

## Relação com rocCV

[rocCV](roccv.md) pode ser avaliado para pré e pós-processamento de imagens com HIP. MIVisionX oferece ferramentas de integração por grafos e compilação de modelos. Escolha a abordagem conforme as etapas do projeto.

[Voltar ao panorama de aceleração](aceleracao.md).
