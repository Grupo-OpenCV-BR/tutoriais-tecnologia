# Bibliotecas e padrões para acelerar visão computacional

Um projeto pode combinar processamento em CPU com GPUs e outros aceleradores. A escolha depende dos algoritmos, do dispositivo de destino e dos requisitos de latência, memória e energia.

Este panorama reúne bibliotecas de uso geral, ferramentas de fabricantes e padrões abertos. Elas atuam em diferentes partes de um sistema: processamento de imagens, execução de grafos, programação paralela ou intercâmbio de modelos.

## Compare as opções

| Tecnologia | Tipo e finalidade | Quando avaliar |
| --- | --- | --- |
| [OpenCV](opencv.md) | Biblioteca de visão computacional de uso geral | Aprendizado, prototipagem e aplicações com algoritmos variados |
| [OpenVX](openvx.md) | Padrão de API para processamento por grafos | Pipelines embarcados e execução em hardware heterogêneo |
| [rocCV](roccv.md) | Biblioteca AMD de pré e pós-processamento com HIP | Processamento de imagens em GPUs compatíveis com ROCm |
| [MIVisionX](mivisionx.md) | Toolkit AMD com implementação OpenVX e ferramentas de inferência | Integração de processamento de imagens e modelos em grafos |
| [VPI](vpi.md) | Biblioteca NVIDIA com diferentes backends de execução | Pipelines em Jetson e plataformas NVIDIA compatíveis |
| [NNEF](nnef.md) | Formato aberto de intercâmbio de redes neurais | Transferência de modelos entre ferramentas compatíveis |

## Uso geral: OpenCV

OpenCV é um ponto de partida para experimentar algoritmos e estabelecer uma referência de resultados. Também oferece caminhos de aceleração: módulos CUDA e a Transparent API (T-API), que utiliza `cv::UMat` para operações com suporte a OpenCL. A disponibilidade depende da compilação, do runtime e da operação escolhida. Consulte a [configuração oficial do OpenCV](https://docs.opencv.org/doc/doxygen/html/db/d05/tutorial_config_reference.html).

## Ecossistema AMD

[rocCV](roccv.md) concentra-se no pré e pós-processamento de imagens em GPU. [MIVisionX](mivisionx.md) reúne uma implementação de OpenVX e ferramentas para integrar visão computacional e inferência. As páginas individuais apresentam seus requisitos e referências oficiais.

## Ecossistema NVIDIA

Além do [VPI](vpi.md), duas bibliotecas atendem necessidades diferentes:

- **CV-CUDA:** biblioteca de código aberto para pré e pós-processamento acelerado por GPU em aplicações de IA visual. É uma opção para avaliar quando essas etapas limitam a vazão do pipeline. [Página oficial do CV-CUDA](https://developer.nvidia.com/cv-cuda).
- **NPP — NVIDIA Performance Primitives:** primitivas de processamento de imagens e sinais em CUDA, úteis para compor operações com controle mais direto sobre buffers e chamadas. [Documentação oficial do NPP](https://docs.nvidia.com/cuda/npp/index.html).

## Ecossistema Intel e programação com SYCL

**Intel IPP — Integrated Performance Primitives** oferece funções otimizadas para processamento de imagens, sinais e visão computacional em CPUs Intel, aproveitando instruções SIMD, como AVX2 e AVX-512, conforme a plataforma. [Página oficial do Intel IPP](https://www.intel.com/content/www/us/en/developer/tools/oneapi/ipp.html).

**SYCL** é um padrão Khronos para programação paralela em C++. Ele permite desenvolver operações para hardware heterogêneo; não define, por si só, um catálogo de algoritmos de visão chamado “SYCL Vision”. [Visão geral oficial do SYCL](https://www.khronos.org/sycl/).

**oneAPI** reúne especificações para programação entre arquiteturas, e **DPC++** é uma implementação de SYCL. O uso em CPUs, GPUs ou FPGAs depende do compilador, dos backends e do suporte à plataforma escolhida. Consulte a [especificação oneAPI](https://oneapi-spec.uxlfoundation.org/specifications/oneapi/v1.2-rev-1/) e o [guia do compilador DPC++](https://intel.github.io/llvm/GetStartedGuide.html).

## Padrões abertos: OpenVX e NNEF

[OpenVX](openvx.md) organiza operações em grafos que uma implementação pode otimizar para o hardware. [NNEF](nnef.md) descreve redes neurais e seus parâmetros para intercâmbio. Eles podem se complementar quando a implementação oferece os recursos necessários.

## Como escolher para seu projeto

Use esta sequência como roteiro de avaliação:

1. **Defina o problema:** resolução, quantidade de câmeras, latência máxima e consumo de memória aceitável.
2. **Crie uma referência:** implemente uma versão simples e registre os resultados esperados.
3. **Meça o pipeline completo:** inclua captura ou decodificação, processamento, inferência, transferências e sincronização.
4. **Verifique a compatibilidade:** confira os algoritmos, formatos de imagem, drivers e dispositivos suportados pela versão pretendida.
5. **Compare nas mesmas condições:** use as mesmas entradas, precisão, tamanho de lote e regras de medição. Em chamadas assíncronas, aguarde a conclusão antes de encerrar a medida.

Ganhos de desempenho precisam ser medidos no cenário real. O custo de transferir dados entre CPU e GPU pode mudar o resultado da comparação; a biblioteca do fabricante não garante vantagem em todos os casos.

Para conectar essas escolhas às etapas da aplicação, consulte o [pipeline de visão computacional](../pipeline/Pipeline.md).
