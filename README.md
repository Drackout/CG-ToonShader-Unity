# Computação Gráfica
### Toon Shader with Outline lines - Unity
### Made by Micael Teixeira - 22208717


## Technicas utilizadas:

### Cel-shading:
O Cel-Shading sendo uma subpart do toonshader, foi o utilizado como base do projeto. Utilizando o normal vector do mundo e utilizado e a direção da luz no produto escalar, calcula-se a quantidade de luz que uma superficie recebe e faz com que se saiba o que é luz e o que é sombra. Dividindo o valor obtido e usando o node Floor para separar entre a cor e a sombra. 
Após a sombra do modelo ter sido criada, pode-se mudar o seu brilho e vai-se buscar a textura do modelo a ser afetado pelo shader, multiplica-se o valor para a textura obter a sombra e volta-se a multiplicar com um node de remap que faz com que o modelo obtenha a incidencia mais brilhante da luz com uma divisão de 1 pelo valor indicado (valor por defeito 0.48) fazendo com que se aumente ou diminua o efeito da sombra/luz no modelo.
Por fim é aplicada uma multiplicação por uma cor, permitindo mudar a cor de todo o modelo e as suas sombras, esta parte foi mantida por ficar interessante com a aplicação de possiveis luzes coloridas no ambiente.

### Fresnel (for Outline lines):
Para a criação das linhas à volta do modelo a utilizar o shader, foi utilizado o efeito Fresnel, este com uma variavel que permite alterar a grossura da linha e logo de seguida utilizar o node de Step para separar o preto do branco. É utilizado vindo do cel-shading a sombra e a iluminação, em que é utilizado o minimum e o maximum para que o que seja afetado seja a luz e a sombra previamente criada, multiplica-se o que veio do cel-shading com o Fresnel para aplicar as linhas a volta do modelo e de seguida aplica-se a cor que se quer que sejam as linhas a volta do modelo, isto irá aplicar tanto na luz como na sombra separadamente, que depois se adiciona um ao outro e no fim faz-se um maximum do que vem do cel-shading com a sua textura e as linhas de Outline criadas a partir do Fresnel. 

### Notas:
A utilização da cor preta não funciona para as linhas do outline, foram feitas várias tentativas  mas no final não consegui fazer com que ficasse com um aspeto decente.

## Bibliography

### TOON SHADER

Unity, Getting started with Unity Toon Shader, https://docs.unity3d.com/Packages/com.unity.toonshader@0.7/manual/GettingStarted.html

Panthavma, Toon Shading Fundamentals (2023)
https://panthavma.com/articles/shading/toonshading/

Minions Art, Lit Toon Shader Graph
https://www.patreon.com/posts/lit-toon-shader-54740865

Unreal Dev Hub, UE5 Toon Shader Material For Beginners
https://80.lv/articles/tutorial-ue5-toon-shader-material-for-beginners/

gamesplusjames, How To Create A Toon Shader using Shader Graph in Unity
https://www.youtube.com/watch?v=lYGWP0UpiO0

### OUTLINE LINES

Mali Makes (whateep), Basic TOON SHADER In UNITY Using Shader Graph
https://www.youtube.com/watch?v=rCvISlussGE

