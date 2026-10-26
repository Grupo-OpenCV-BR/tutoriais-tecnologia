# VPI — Vision Programming Interface da NVIDIA

**VPI** é uma biblioteca NVIDIA de visão computacional e processamento de imagens com interfaces para C/C++ e Python. Oferece backends como CPU, CUDA e aceleradores presentes em dispositivos compatíveis, incluindo PVA, VIC e OFA. [Documentação oficial do VPI](https://docs.nvidia.com/vpi/index.html).

## Quando usar

Avalie VPI em projetos com Jetson ou GPUs NVIDIA compatíveis, especialmente quando houver oportunidade de distribuir etapas entre diferentes motores de processamento. Por exemplo, o pré-processamento pode usar um acelerador disponível enquanto a GPU executa outra etapa.

## Como começar

1. Confira os algoritmos e backends suportados pelo seu dispositivo e pela versão do VPI.
2. Execute um exemplo oficial próximo do seu caso de uso.
3. Integre uma operação por vez e compare resultados e latência.
4. Inclua transferências e sincronização na medição.

## Memória e desempenho

O compartilhamento de memória sem cópia (*zero-copy*) depende da plataforma, dos formatos e da forma de alocar ou compartilhar buffers. Nem todo algoritmo está disponível em todo backend. A documentação descreve essas condições; valide-as antes de projetar a integração.

Para pré e pós-processamento em GPU, considere também CV-CUDA e NPP, apresentados no [panorama de aceleração](aceleracao.md). Compare o pipeline completo antes de escolher.
