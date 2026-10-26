# rocCV — processamento de imagens com AMD HIP

**rocCV** é uma biblioteca de pré e pós-processamento de imagens acelerada por GPU, construída sobre a plataforma HIP da AMD. O projeto oferece biblioteca C++ e módulo Python. [Repositório oficial do rocCV](https://github.com/ROCm/rocCV).

## Quando usar

Avalie rocCV quando a preparação ou transformação das imagens for um gargalo em um pipeline executado em GPUs AMD compatíveis. Compare-a com a implementação de referência usando as mesmas imagens e critérios de qualidade.

## Requisitos e primeiros passos

1. Confira os requisitos de GPU, sistema operacional e ROCm na [documentação do rocCV](https://rocm.docs.amd.com/projects/rocCV/en/latest/index.html).
2. Use as instruções correspondentes à versão escolhida para instalar ou compilar a biblioteca.
3. Execute os exemplos oficiais antes de integrar suas próprias imagens.
4. Meça também as transferências de memória e a sincronização entre etapas.

## Maturidade da versão

A documentação do **ROCm 7.2.2** classifica rocCV como acesso antecipado e desaconselha seu uso em produção nessa versão. Confira o estado da versão que pretende adotar. [Nota oficial do ROCm 7.2.2](https://rocm.docs.amd.com/en/docs-7.2.2/what-is-rocm.html).

Para processamento por grafos com OpenVX no ecossistema AMD, consulte também [MIVisionX](mivisionx.md).

[Voltar ao panorama de aceleração](aceleracao.md).
