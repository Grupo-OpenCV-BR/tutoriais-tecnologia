# NNEF — Neural Network Exchange Format

**NNEF** é um formato aberto do Khronos Group para intercâmbio de redes neurais. Ele descreve a estrutura da rede e seus parâmetros, permitindo transferir modelos entre ferramentas de criação e ambientes de execução compatíveis. [Apresentação oficial do NNEF](https://www.khronos.org/nnef).

## Papel em visão computacional

NNEF pode fazer parte da implantação de modelos usados em tarefas de visão. O formato armazena a representação do modelo; sua execução depende de um compilador ou runtime que o aceite, como as ferramentas incluídas no [MIVisionX](mivisionx.md).

## Fluxo de estudo

1. Escolha um modelo e uma ferramenta de conversão compatível.
2. Exporte a rede e valide a representação NNEF.
3. Verifique os operadores, tipos de dados e recursos aceitos pelo runtime de destino.
4. Compare as saídas com as do modelo original usando as mesmas entradas.

O ecossistema inclui parsers, validadores e conversores, acessíveis pela página oficial. A compatibilidade precisa ser verificada para cada modelo e ferramenta.

## Relação com OpenVX

[OpenVX](openvx.md) pode oferecer integração com NNEF por recursos de importação de kernels. Confirme o suporte na implementação escolhida; ele não está garantido apenas pelo uso do nome OpenVX.

[Voltar ao panorama de aceleração](aceleracao.md).
