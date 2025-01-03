# Computação Gráfica
## Toon Shader with Outline lines - Unity
### Micael Teixeira - 22208717

#### github: https://github.com/Drackout/CG-ToonShader-Unity
#### Build: https://drive.google.com/drive/folders/1VrzDJoSbdiaVxUfgIEHsm-yJsEiVirNx?usp=sharing

## Technicas utilizadas:

### Cel-shading:
O Cel-Shading sendo uma sub-parte do toonshader, este foi o utilizado como base do projeto. Utilizando o normal vector do mundo e utilizado e a direção da luz no produto escalar, calcula-se a quantidade de luz que uma superfície recebe e faz com que se saiba o que é luz e o que é sombra. Dividindo o valor obtido e usando o node Floor para separar entre a luz e a sombra. 

Após a sombra do modelo ter sido criada, pode-se mudar o seu brilho e vai-se buscar a textura do modelo a ser afetado pelo shader, multiplica-se o valor para a textura obter a sombra e volta-se a multiplicar com um node de remap que faz com que o modelo obtenha a incidência mais brilhante da luz com uma divisão de 1 pelo valor indicado (valor por defeito 0.48) fazendo com que se aumente ou diminua o efeito da sombra/luz no modelo.

Por fim é aplicada uma multiplicação por uma cor, permitindo mudar a cor do modelo e as suas sombras, esta parte foi mantida por ficar interessante com a aplicação de possíveis luzes coloridas no ambiente.

### Fresnel (for Outline lines):

Para a criação das linhas à volta do modelo a utilizar o shader, foi utilizado o efeito Fresnel, este com uma variável que permite alterar a grossura da linha e logo de seguida utilizar o node de Step para que fique apenas com o preto e o branco.

É utilizado vindo do cel-shading a sombra e a iluminação em que é utilizado o minimum e o maximum para que o que seja afetado seja a luz e a sombra previamente criados, multiplica-se o que veio do cel-shading com o Fresnel para aplicar as linhas a volta do modelo e de seguida aplica-se a cor que se quer dar, irá ser aplicado tanto na luz como na sombra separadamente, em que na sombra ficará mais escuro do que na luz. Depois adiciona-se um ao outro e no fim faz-se um maximum do que vem do cel-shading com a sua textura e as linhas de Outline criadas a partir do Fresnel.

### Notas:
- A utilização da cor preta não funciona para as linhas do outline, tentando por preto irá apenas retirar o outline. Foram feitas várias tentativas  mas no final não consegui fazer algo que ficasse com o aspeto desejado.

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

### 3D Models

Char1 and Char2, Adobe mixamo
https://www.mixamo.com/#/?page=1&type=Character

Picola Inc, PicoChan
https://assetstore.unity.com/packages/3d/characters/humanoids/picochan-220038

ithappy, Animals FREE - Low Poly Asset Pack by ithappy
https://assetstore.unity.com/packages/3d/characters/animals/animals-free-low-poly-asset-pack-by-ithappy-260727

Symphonie Studio, Stylize Tree &Grassess samples
https://assetstore.unity.com/packages/3d/vegetation/trees/stylize-tree-grassess-samples-304714

GVOZDY, Water Fountain Round Four-Tier PBR
https://assetstore.unity.com/packages/3d/props/exterior/water-fountain-round-four-tier-pbr-299380