## ICP


De forma geral, o ICP é um algoritmo para fazer alinhamento entre dois conjuntos de dados, podem ser 2D, que chamamos de Affine ICP, e o ICP em 3D. No contexto de navegação autônoma, o ICP é usado para determinar a trajetória percorrida entre dois scans de point clouds obtidos de um sensor chamado LiDAR. O LiDAR é uma espécie de radar, vulgarmente falando, que emite feixes de luz para determinar o ponto 3D do ambiente ao seu redor, por isso ele é o Light Radar (LiDAR).

 Uma das tecnologias que a gente desenvolve é em odometria de LiDAR para carros autônomos com uma empresa norte-americana. O ICP é utilizado em nosso algoritmo, bem como outros algoritmos e sensores para melhorar a precisão da odometria. Odometria é a tarefa de estimar, em 6 graus de liberdade ou menos, o movimento (translação + rotação) de um corpo rígido. Para isso, podemos usar o LIDAR, Câmera, IMU, GPS, ou combinar todos esses sensores para melhorar a precisão do algoritmo.


 Mas nem sempre o ICP é usado, existem outras formas de fazer odometria, como no paper do [LOAM](https://www.ri.cmu.edu/pub_files/2014/7/Ji_LidarMapping_RSS2014_v8.pdf) que ele ele usa um detector de quinas na point cloud.

Se você se interessa por isso, eu recomendaria você estudar C++ e Estimação de Estado. C++ eu recomendo porque nessa indústria de navegação autônoma, é importante termos segurança, que um código de C++ oferece, e também usamos ele por questão de performance (velocidade e uso de multiprocessos, coisa que em Python é mais complicado).

Estimação de Estado existem vários livros, um deles é do [Sebastian Thrun](https://www.amazon.com/Probabilistic-Robotics-INTELLIGENT-ROBOTICS-AUTONOMOUS/dp/0262201623 ) tem bastante matemática, se você gosta, vai fundo. Já C++, acredito que você pode procurar por cursos online, no YouTube, que você vai provavelmente achar algum material que se adeque ao seu estilo de aprendizado.

### Referências interessantes 

[ICP(Iterative Closest Point) Algorithm ](https://medium.com/@michaelscheinfeild/icp-iterative-closest-point-algorithm-32ecaf58e9da)
[John Lambert](https://johnwlambert.github.io/icp/)

<br>

## Video rápido explicando o algoritmo:
<br>
<iframe width="1136" height="639" src="https://www.youtube.com/embed/QWDM4cFdKrE" title="Iterative Closest Point (ICP) - 5 Minutes with Cyrill" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br>


## Playlist de ICP: 
<br>

<iframe width="1136" height="639" src="https://www.youtube.com/embed/dhzLQfDBx2Q?list=RDCMUCi1TC2fLRvgBQNe-T4dp8Eg" title="ICP & Point Cloud Registration - Part 1: Known Data Association & SVD (Cyrill Stachniss, 2021)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>

<iframe width="1136" height="639" src="https://www.youtube.com/embed/ktRqKxddjJk?list=RDCMUCi1TC2fLRvgBQNe-T4dp8Eg" title="ICP & Point Cloud Registration - Part 2: Unknown Data Association (Cyrill Stachniss, 2021)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>


<iframe width="1136" height="639" src="https://www.youtube.com/embed/CJE59i8oxIE" title="ICP & Point Cloud Registration - Part 3: Non-linear Least Squares (Cyrill Stachniss, 2021)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>



## Implementação do ICP


[ClayFlannigan](https://github.com/ClayFlannigan/icp/blob/master/icp.py) <br>
[KojiKobayashi](https://github.com/KojiKobayashi/iterative_closest_point_2d)<br>
[richardos](https://github.com/richardos/icp)<br>


## Libs que possam ser interessantes

[ICP - A Python module for registering a photo with a database image of the same scene ](https://pypi.org/project/ICP/) <br>
[Open3D -  A Modern Library for 3D Data Processing](http://www.open3d.org/) <br>