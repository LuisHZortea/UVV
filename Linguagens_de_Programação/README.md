<div align="center">
 
  # Problem Set 1
  #### Aluno: Luis Henrique Gomes Zortea | Curso: Ciência da Computação | Turma: CC3M | Professor(a): Abrantes Araújo Silva Filho 
</div> 

- Este PSET é uma tradução da primeira tarefa de programação que os alunos da disciplina “MIT 6.009: Fundamentals of Programming” recebem logo no primeiro dia de aula, feita para os alunos da disciplina “Linguagens de Programação” na Universidade Vila Velha (UVV).

## Questões
- #### Questão 01 
> Se você passar essa imagem pelo filtro de inversão, qual seria o output esperado? Justifique sua resposta.
~~~
 O resultado será: [226, 166, 119, 55].
 Cálculo:
 255 - 29 => 226
 255 - 89 => 166
 255 - 136 => 119
 255 - 200 => 55
~~~
- #### Questão 02
> Faça a depuração e, quando terminar, seu código deve conseguir passar em todos os testes do grupo de teste TestInvertida (incluindo especificamente o que você acabou de criar). Execute seu filtro de inversão na imagem test_images/bluegill.png, salve o resultado como uma imagem PNG e salve a imagem em seu repositório GitHub.

![bluegillinvertido.png](https://github.com/LuisHZortea/uvv_lp_cc3m/blob/main/Imagens/bluegillinvertido.png) 
~~~
imagem_original = Imagem.carregar('bluegill.png')
imagem_nova = image.original.invertida()
imagem_nova.salvar('bluegillinvertido.png)
~~~

- #### Questão 03
> Considere uma etapa de correlacionar uma imagem com o seguinte kernel:
~~~~
0.00 -0.07 0.00
-0.45 1.20 -0.25
0.00 -0.12 0.00
~~~~
>Qual será o valor do pixel na imagem de saída no local indicado pelo destaque vermelho? Observe que neste ponto ainda não arredondamos ou recortamos o valor, informe exatamente como você calculou. Observação: demonstre passo a passo os cálculos realizados.
~~~
80 x 0 + (-0,07 x 53) + 99 x 0               -> 0 - 3,71 + 0        }
(-0,45 x 129) + 127 x 1,20 + (-0,25 x 148) + -> -58,05 + 152,4 - 37 } -> Ox,y = 32,76
175 x 0 + (-0,12 x 174) + 193 x 0            -> 0 - 20,88 + 0       }
~~~~

- #### Questão 04
> Quando você tiver implementado seu código, tente executá-lo em test_images/pigbird.png com o seguinte kernel 9 × 9. Ao rodar esse kernel, salve a imagem resultante em seu repositório GitHub.

![pigbirdcorrelacao.png](https://github.com/LuisHZortea/uvv_lp_cc3m/blob/main/Imagens/pigbirdcorrelacao.png)

~~~
kernel = [[0, 0, 0, 0, 0, 0, 0, 0, 0,],
             [0, 0, 0, 0, 0, 0, 0, 0, 0,],
             [1, 0, 0, 0, 0, 0, 0, 0, 0,],
             [0, 0, 0, 0, 0, 0, 0, 0, 0,],
             [0, 0, 0, 0, 0, 0, 0, 0, 0,],
             [0, 0, 0, 0, 0, 0, 0, 0, 0,],
             [0, 0, 0, 0, 0, 0, 0, 0, 0,],
             [0, 0, 0, 0, 0, 0, 0, 0, 0,],
             [0, 0, 0, 0, 0, 0, 0, 0, 0]]
im = Imagem.carregar('test_images/pigbird.png')
correlacaoIm = im.correlacao(kernel)
correlacaoIm.salvar('Imagens/pigbirdcorrelacao.png')
 ~~~~

- #### Questão 05
> Quando você terminar e seu código passar em todos os testes relacionados ao desfoque, execute seu filtro na imagem test_images/cat.png com um kernel de desfoque de caixa de tamanho 5, salve o resultado como uma imagem PNG e faça o upload para seu repositório GitHub.

![gato.png](https://github.com/LuisHZortea/uvv_lp_cc3m/blob/main/Imagens/gato.png)

~~~
imagem = Imagem.carregar('test_images/cat.png')
borrarIm = imagem.borrada(5)
Imagem.salvar(borrarIm, 'Imagens/gato.png')
~~~~

- #### Questão 06
> Se quisermos usar uma versão desfocada B que foi feita com um kernel de desfoque de caixa de 3 × 3, que kernel k poderíamos usar para calcular toda a imagem nítida com uma única correlação? Justifique sua resposta mostrando os cálculos.

![pythonfocada.png](https://github.com/LuisHZortea/uvv_lp_cc3m/blob/main/Imagens/pythonfocada.png)

- #### Questão 06
> Explique o que cada um dos kernels acima, por si só, está fazendo. Tente executar mostrar nos resultados dessas correlações intermediárias para ter uma noção do que está acontecendo aqui. Implemente o detector de bordas como o método bordas dentro da classe Imagem. O método deve retornar uma nova instância de Imagem resultante das operações acima. Quando terminar e seu código passar nos testes de detecção de borda, execute seu detector de borda na imagem test_images/construct.png, salve o resultado como uma imagem PNG e faça o upload para seu repositório GitHub.

![construcaobordas.png](https://github.com/LuisHZortea/uvv_lp_cc3m/blob/main/Imagens/construcaobordas.png)

O kernel Kx é tem a função de identificar as bordas no eixo x, ou seja, na horizontal, e o kernel Ky identifica o eixo y, na vertical.

