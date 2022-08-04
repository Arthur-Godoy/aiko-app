![aiko-app_1](https://user-images.githubusercontent.com/80718197/182913822-3850726a-ae4d-46a6-8f62-695bcf298d79.gif)
# **Observações:**

1. O projeto foi feito usando MUI, que já possui vários componentes prontos e estilizados, substituindo as tags HTML padrão, porém acabei usando algumas tags html, para conseguir dar um estilo totalmente diferente.

2. O projeto é organizado em pastas, e cada uma possui seu respectivo index.jsx e caso use CSS teria um arquivo CSS próprio. (vi esse modelo de organização no projeto do EM SUMA, e aderi até então).

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 002](https://user-images.githubusercontent.com/80718197/182905696-6d2d619a-fb1c-4aee-ab2f-9ee982817bbb.png)

2. Fiz o Histórico de Posições de 3 maneiras:

-A primeira seria como uma tabela (igual ao histórico de estados) e mantive essa parte no código, por mais que não esteja utilizando.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 003](https://user-images.githubusercontent.com/80718197/182905629-2311d2e6-0a8e-4896-ada6-a17cce068682.png)

-A segunda é mostrando no mapa as posições com uma linha, mas não ficou muito organizado

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 004](https://user-images.githubusercontent.com/80718197/182905632-8d4ad320-05c3-4544-8e4d-09edb65a6e24.png)

\- A terceira são com pontos, das posições anteriores, onde mostra a data da posição. E essa é a mantida no projeto.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 005](https://user-images.githubusercontent.com/80718197/182905637-64f0b95c-d46a-4417-954e-a0a4fc4f9f4d.png)
# **Views:**

### **-Home**

`	`Esse projeto possui somente uma view, que é a Home, o que pode ser que deixa ele um pouco redundante, uma vez que poderia somente carregar os componentes no App.jsx, na Home são renderizados os componentes TopBar 	e Map.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 006](https://user-images.githubusercontent.com/80718197/182905641-f237b2f0-8029-46ef-b1ec-6ab6f36557c5.png)

Também possui a função getNameSearch que serve para pegar o valor do Selection do componente TopBar (explicação mais a frente)


# **Tratamento de Dados:**
#
`	`Os Dados estão todos guardados na pasta chamada Data. Onde estão todos os arquivos JSON e o arquivo dataTratement.js.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 007](https://user-images.githubusercontent.com/80718197/182905643-83171034-7f89-4b60-b056-e76ed1c2245c.png)

`	`Nesse projeto decidi criar um arquivo separado para organizar todos os meus dados de forma que ficasse muito mais fácil de lidar com eles, não tendo que organizar a cada vez que precisasse dos dados. Por isso criei o dataTratement.js.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 008](https://user-images.githubusercontent.com/80718197/182905644-c0f5575c-7437-47bb-ac0d-80a0469847c8.png)

Primeiramente Importei todos os meu arquivos JSON, depois criei uma classe, meu objetivo era ter um objeto do equipamento com todos seus dados prontos e organizados, nele temos o Id, nome, modelo, todo o historico de posição e estado, e também a posição e estado atual, Também capturei todos os dados de ganhos, porém não deu tempo de utiliza-lo.

`	`Para conseguir todas as informações precisei criar funçoes separadas para cada propriedade da classe.
###
### **-Funções:**
`	`-GetState: A função getState irá receber um idState, e irá retornar um Array, com o nome do estado e a respectiva cor.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 009](https://user-images.githubusercontent.com/80718197/182905647-1a19804b-cf0c-4b34-8f98-36d56b18237d.png)

`	`-GetModelandEarnings: Essa função receberá um id de modelo, e irá retornar um array com o nome do modelo e o “hourlyEarning”

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 010](https://user-images.githubusercontent.com/80718197/182905652-5f34b49e-3a9e-44df-86d5-2f8a2b544be7.png)

`	`-getPositionHistory: Essa função irá retornar um array com todas as posições do equipamento, cada posição do array principal possui outro array com a data, latitude e lontitude. Essa função precisa de um id de equipamento como parâmetro.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 011](https://user-images.githubusercontent.com/80718197/182905654-1579c1dc-cf69-4e7d-94ac-42a263154d79.png)







-getStateHistory: Essa função irá retornar um array com todas os estados do equipamento, cada posição do array principal possui outro array com o nome do estado sua cor e data, o nome e cor são pegos da função getState. Essa função precisa de um id de equipamento como parâmetro.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 012](https://user-images.githubusercontent.com/80718197/182905657-44795f6d-6896-424b-9131-e7a957958871.png)

-generateEquipmentsObj: Essa é a função que irá gerar o array de objetos, nele nós temos um .map dos equipments, e depois vai criando variáveis com os valores de retorno das funções anteriores, 

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 013](https://user-images.githubusercontent.com/80718197/182905660-acb06294-c96d-4ce9-bc4d-a26ba5751bd9.png)

Por fim o dataTreatement irá exportar um Arr de objetos, que é declarado e exportado ao final.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 014](https://user-images.githubusercontent.com/80718197/182905663-27c4647f-4d7d-462b-9398-ec914bc8d234.png)

### **
# **Componentes:**

**-TopBar**
**

**
`	`O componente Top Bar, é o componente da barra de navegação de cima.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 015](https://user-images.githubusercontent.com/80718197/182905668-016963f2-621d-4bc4-871d-83b6c3a8d7f4.png)



Ele possui um Select onde todos os nomes dos Equipamentos são listados, O nome selecionado é enviado para o componente pai através de uma função.

Essa função é passada da view Home para o componente filho TopBar, que por sua vez altera o valor da variável no componente Pai, do componente pai ele é enviado para outro componente filho que é o map, onde ele faz a  tratativa para centralizar o respectivo equipamento.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 016](https://user-images.githubusercontent.com/80718197/182905671-81d8dcd4-75ff-48a0-8b8d-512bf74fed1a.png)
### **-Map:**
Esse componente irá retornar o mapa, o mapa é carregado da biblioteca do Leaflet, nele nós temos a propriedade nameSearch, que é para mostrar o marcador conrrespondente da pesquisa, para isso tem a variável position com o hook useState, e depois um hook useEffect para pegar a posição através do nome do equipamento. ![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 017](https://user-images.githubusercontent.com/80718197/182905672-685ccd00-8c78-42ae-a206-114cf02e660b.png)

Após isso o MapContainer possui uma key igual a position, e será centralizado no position. Caso o nameSeach for diferente de ‘ ‘, ou seja, caso tenha alguma pesquisa, o zoom também será mudado de 10 para 14 e também aparecerá um círculo no marcador.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 018](https://user-images.githubusercontent.com/80718197/182905675-619866b6-53ad-46f9-b130-5ddc63f0eac9.png)

### **-Markers:**
`	`Esse componente irá retornar os marcadores do mapa, e é o componente com mais funcionalidades na aplicação, primeiramente nós temos três variáveis que são as responsáveis por mudar o tipo de ícone do marcador na aplicação. (Acabei misturando o inglês com o portugues ali kkkk).

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 019](https://user-images.githubusercontent.com/80718197/182905678-f242a6b0-00fb-4484-b352-358fdbd691b8.png)



`	`Depois temos um .map do equipmentArr (do DataTratment), esse .map irá passar por 3 if/else, para verificar o tipo do ícone, se irá ser caminhão, garra ou trator,  cada um desse retornará um Marker, e um Popup com o nome, modelo e estado, e dois botões, um para ver o historico de posições e outro para o historico de estados. 

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 020](https://user-images.githubusercontent.com/80718197/182905681-795ba67c-b8aa-4442-8f22-32e7bbe61e9d.png)

`	`O historico de posições e de estados tem um if ternário, onde irá renderizar o componente do historico somente se for true, eu estava tendo um problema que eu estava fazendo a mesma verificação para abrir todos, e fechar todos, então quando se abria um ele abria normal, mas depois quando ia abrir outro se abria os 2 juntos, e assim em diante, então resolvi esse problema adicionando mais uma verificação.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 021](https://user-images.githubusercontent.com/80718197/182905683-323ecd06-f45d-42b5-945a-98180d7a0d83.png)

Essas variaveis de controle, além de ter o falso (fechado), e true(aberto), vão ter também um Id, esse id será o do Marker dentro do .map. Então agora sempre que eu abro um modal, a variável é alterada para [true, id], e depois fechada para, [false,id], e as verificações ternárias passou a ser se é verdadeiro e se o id da variável é igual ao id do equipamento.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 022](https://user-images.githubusercontent.com/80718197/182905684-7d1f4a71-653a-45c1-9781-99b24c64cb77.png)
`	`Com certeza existem maneiras melhores, mas essa foi uma gambiarra que encontrei e funcionou muito bem para minha situação. Caso ele clique para ver o historico de posições sé um .map, onde será retornado um circle vermelho, para cada posição do historico. 

### **-StateHistory:**
`	`Esse componente recebe como props uma variável contendo o objeto do equipamento que deverá ser mostrado o historico e também recebe uma função do componente pai (Markers) chamada close, que é usada para fechar o componente.

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 023](https://user-images.githubusercontent.com/80718197/182905686-8e913c52-92a3-4c90-8fee-24e1e79b3516.png)

![Aspose Words 9b1917df-3c40-492a-85e7-aa8648c56ee8 024](https://user-images.githubusercontent.com/80718197/182905690-75f808cd-bec6-4b17-b76b-6e7519e60f85.png)

`	`Ele renderiza um Modal, e dentro desse modal existe uma tabela,  e dentro do TableBody, tem um .map onde será renderizado um TableCell, contendo a Data, Hora e Estado. E ao final um botão de fechar que irá usa a função do componente pai, para fecha-lo dentro do próprio componente pai.
