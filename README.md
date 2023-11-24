<h1 align="center"> GLOBAL SOLUTION - 2° SEMESTRE :earth_americas: </h1>

<br>

<h2  align="center"> Introdução ao problema </h2>
<p align="justify">A Saúde é um tópico muito importante em todo mundo, ja que, é através da saúde que conseguimos ter qualidade de vida, bem-estar e proporcionar um futuro melhor para todos. Ao longo dos anos a área da saúde sofreu diversas mudanças devido
aos avanços tecnológicos que ocorreram, possibilitando melhora na qualidade dos cuidados médicos, cirurgias e atendimentos. A tendencia e o nosso comprometimento é criar soluções inovadoras que possam moldar o futuro da saúde, melhorando a precisão, 
prevenção e automação dessa área.</p>

<br>


<h2  align="center"> Projeto de solução :bulb: </h2>
<p align="justify"> Pensando em mais uma melhoria na área da saúde, vamos desenvolver um aplicativo que mostra e monitora a fila de espera em hospitais. Essa solução pode ser muito útil para melhorar a experiência dos pacientes, permitindo que os usuários acompanhassem em tempo real a posição na fila de espera, fornecendo informações sobre o tempo estimado de espera e atualizações em caso de atrasos ou mudanças na ordem de atendimento, além de informar também as situações dos hospitais através do aplicativo, mostrando se estão cheios ou vazios. O aplicativo também vai contar com um sistema de notificação, informando ao paciente a proximidade do atendimento e com a opção de agendar consultas remotamente.</p>
<p align="justify"> Utilizamos o site "Wokwi" para desenvolver um projeto que simula o sistema de notificação e a fila de espera em hospitais, para isso utilizamos os seguintes componentes: </p>
<ul> 
  <li> Placa de ensaio; </li> 
  <li> ESP32; </li>
  <li> BUZZER; </li>
  <li> LED; </li>
  <li> Resistor de 10kΩ. </li>
  <li> Display LCD 20 x 4 (I2C); </li>  
</ul>

<p align="center"> Montando o projeto com essas peças, é possível chegar nesse resultado: </p>
<div align="center">
<img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/fed1ae08-c5bf-47d2-bade-0ab135d8b944" alt="Construção do projeto">
</div>

<br>

<h2 align="center"> Análise dos Componentes :wrench: </h2>
<p align="justify"> Iniciaremos a explicação com a Placa de Ensaio, peça fundamental neste projeto. É nela que acomodaremos o resistor, LED e o BUZZER, assegurando o correto funcionamento do projeto. </p>
<p align="justify"> O ESP32 desempenha um papel crucial neste projeto ao estabelecer a conexão com a internet. Além disso, é responsável por coordenar o funcionamento do Display LCD 20x4 (I2C). Por meio do ESP32, os dados coletados tornam-se acessíveis através da nuvem. Isso significa que, contanto que haja conexão com a internet, é possível acessar o projeto de qualquer região do mundo. </p>
<p align="justify"> O Display LCD 20x4 (I2C) desempenha um papel crucial na transmissão de informações para o usuário. Através dele, é possível identificar o número do paciente e o consultório no qual ele deve se dirigir. </p>

<br>

<h2 align="center"> Montagem do Código :bomb: </h2>
<p> Após a montagem, devemos partir para o código, que estará disponível nesse repositório. </p>
<p> Devemos começar com as importações das bibliotecas.</p>
<div>
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/17c17d3d-3a24-40a5-b55b-bac6e0ffe0d0">
</div>
<br>
<div>
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/141d9c96-904b-4aac-83ab-bd62444e14f9">
</div>

<br>

<p> :warning: Note que as bibliotecas "WiFi.h" e "Wire.h" não serão possiveis de instalar no site, porém seu funcionamento continua normal. :warning: </p>
<hr>

<br>


<img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/6d1f74ad-0bd8-4c56-a8ee-60ec41c13b06">
<p>-Em seguida é necessário definir os tópicos que enviarão as informações do paciente e do consultório para o servidor (Linhas 10 e 11)</p>

<p>No void loop colocamos os seguintes códigos:</p>

<div>
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/de40179f-95d6-426a-980e-3cce5fc1e344">
</div>

<p>Esse código vai permitir com que as informações do número do paciente e o número do consultório sejam enviadas para servidor, possibilitando ser vizualizada através do servidor IOT.</p>

<br>

<p>Depois disso seguimos os seguintes passos: </p>
<div>
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/8a36c0b5-03cd-4249-a822-3d7ed6343eab">
</div>

<p>-Definimos o pino em que o LED e o BUZZER estão conectados (Linhas 14 e 16) </p>
<p>-Criamos duas variasveis chamadas "pacientes" e "consultorio" e atribuimos o valor 0 e 4 respectivamente. (Linhas 18 e 19)</p>
<p>-Por fim, é necessário também configurar as linhas de conexão com a internet. Para isso, siga as instruções no código e insira o nome e a senha da sua rede Wi-Fi nas posições indicadas. Isso possibilitará que o ESP32 se conecte à rede e envie os dados para a nuvem. (Linhas 22 e 23) </p>

<br>

<p align="justify"> Neste caso estamos usando o nome da rede “Wokwi-GUEST”, porque o site está fornecendo essa rede para ser feito os testes necessários, garantindo o funcionamento do ESP32 ao enviar os dados na nuvem. Após realizar essas modificações, verifique o restante do código, execute e aguarde a mensagem indicando que o ESP32 está tentando se conectar à rede. Isso confirma que as configurações foram feitas corretamente e o dispositivo está buscando ativamente a conexão com a rede especificada. </p>

<div align="center">
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/521e2a47-55fa-4269-8c94-95fbd79d82b2">
</div>

<br>

<p align="justify"> Se você estiver realizando o procedimento com o material em mãos, lembre-se de pressionar o botão "BOOT" do ESP32 para estabelecer a conexão. Isso é necessário para iniciar o processo de conexão com a rede após as modificações no código. </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/61e46b3e-1612-4cc8-9ccd-6da7be441294">
</div>

<br>

<p align="center"> Após a conexão ser feita, vai aparecer a seguinte informação: </p>

<div align="center">
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/4106e6a4-8ed8-4604-a33f-f8576c2c33ff">
</div>

<br>

<p>Antes de iniciar o programa vale lembrar que no "Void loop" do código acrescentamos uma somatória na variavel "pacientes" e "consultorio"</p>

<div align="center">
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/691af268-8115-4a6f-b2d8-d638cfb0ecaa"
</div>

<br>
  
<p align="center"> Após esse procedimento, o número do paciente e o consultório que ele deve se dirigir vão aparecer no Display LCD 20x4 (I2C): </p>

<br>

<div align="center">
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/dcfeac55-2c5f-4050-a192-7bc3459c7fcd">
</div>

<p>Junto com o Display LCD um alerta sonoro e visual serão emitidos no programa</p>

<br>

<div align="center">
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/f39e8150-7832-4a58-b3e8-315cc49ef0b3">
</div>

<br>

<p>No código colocamos a função "If()" e passamos o seguinte parâmetro: </p>

<div align="center">
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/9b4ac998-ceca-4b68-be6e-09a5033200a7">
</div>

<br>

<p>Isso significa que quando o número do paciente for igual a 10 e o número do consultório for igual a 14, o loop vai encerrar através da função "while(1)" que trava o ESP32 finalizando sua ação. Para voltar o loop novamente é necessário apertar o botão reset do ESP32</p>

<div align="center">
  <img src="https://github.com/limas0209/Global-Solution---2---Semestre/assets/127214958/b70c8a61-a7b3-44a0-adfd-a6fc53ac4511">
</div>

<h2 align="center"> Considerações Finais 📘 </h2>
<p align="center"> Diante de todos esses passos, podemos afirmar que o projeto está concluído. Se todos os procedimentos foram seguidos corretamente, será possível verificar que o projeto está funcionando conforme o esperado, lembrando que o intuito do projeto é simular o sistema de notificação e fila de espera em hospitais, a ideia é que essas informações estajam disponiveis não só no display do hospital, mas também no aplicativo. Agradecemos pela atenção e pelo esforço ao acompanhar essas etapas! </p>
<hr>
<br>

<h2 align="center">Autores :muscle:</h2>
<h3>Henrique Lima - RM 551528</h3> 
https://www.linkedin.com/in/henrique-lima-463686277/
/
https://github.com/limas0209"

<h3>Guilherme Fazito - RM 550539</h3>
https://github.com/GuilhermeFazito
