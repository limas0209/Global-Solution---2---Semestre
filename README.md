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
<img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/6a152561-8539-43f1-b5e4-0d505cc2a248">

<br>

<h2 align="center"> Análise dos Componentes </h2>
<p align="justify"> Iniciaremos a explicação com a Placa de Ensaio, peça fundamental neste projeto. É nela que acomodaremos os demais componentes, assegurando o correto funcionamento do projeto. </p>
<p align="justify"> O ESP32 desempenha um papel crucial neste projeto ao estabelecer a conexão com a internet, possibilitando a visualização dos valores coletados pelos sensores na nuvem. Além disso, é responsável por coordenar o funcionamento do sensor de umidade e temperatura DHT22 (ou DHT11), bem como do Display LCD I2C. Por meio do ESP32, os dados coletados tornam-se acessíveis através da nuvem. Isso significa que, contanto que haja conexão com a internet, é possível acessar o projeto de qualquer região do mundo. </p>
<p align="justify"> Quanto ao sensor, o DHT22 é empregado para medir tanto a temperatura quanto a umidade. No entanto, no projeto físico, há também a opção do DHT11, que realiza as mesmas medições. Em resumo, independentemente da escolha entre DHT22 e DHT11, ambos proporcionarão resultados idênticos. </p>
<p align="justify"> O Display LCD I2C desempenha um papel crucial na transmissão de informações para o usuário. Através dele, é possível analisar o nível de umidade (em %), a temperatura e receber um alerta de enchente caso os valores atinjam níveis elevados. Sua interface intuitiva proporciona uma experiência de usuário eficaz na monitorização dos dados coletados. </p>

<br>

<h2 align="center"> Montagem do Código </h2>
<p> Após a conclusão da montagem do projeto, partiremos para o desenvolvimento do código. Sinta-se à vontade para acessar o código disponível neste repositório. No entanto, observe que será necessário efetuar algumas alterações nos tópicos marcados no código para estabelecer a conexão com a nuvem e visualizar os dados fornecidos pelo sensor DHT22. (Linhas 9, 10, 11, 12 e 13) </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/3915fb3c-ed1f-42b6-9108-b79fdefaa670">
</div>

<br>

<p align="justify"> Após realizar a alteração mencionada, é necessário configurar as linhas de conexão com a internet. Para isso, siga as instruções no código e insira o nome e a senha da sua rede Wi-Fi nas posições indicadas. Isso possibilitará que o ESP32 se conecte à rede e envie os dados do sensor para a nuvem. (Linhas 16 e 17) </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/3b954812-f646-4271-ad97-8d7bb09cd7ad">
</div>

<br>

<p align="justify"> Neste caso estamos usando o nome da rede “Wokwi-GUEST”, porque o site está fornecendo essa rede para ser feito os testes necessários, garantindo o funcionamento do ESP32 ao enviar os dados na nuvem. Após realizar essas modificações, execute o código e aguarde a mensagem indicando que o ESP32 está tentando se conectar à rede. Isso confirma que as configurações foram feitas corretamente e o dispositivo está buscando ativamente a conexão com a rede especificada. </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/3b1c6151-8b80-4205-9149-63f7a7e9b3be">
</div>

<br>

<p align="justify"> Se você estiver realizando o procedimento com o material em mãos, lembre-se de pressionar o botão "BOOT" do ESP32 para estabelecer a conexão. Isso é necessário para iniciar o processo de conexão com a rede após as modificações no código. </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/61e46b3e-1612-4cc8-9ccd-6da7be441294">
</div>

<br>

<p align="center"> Após a conexão ser feita, vai aparecer a seguinte informação: </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/aa4f816f-e963-405c-a923-18681dcf2265">
</div>

<br>

<p align="justify"> Após esse procedimento, os valores de temperatura e umidade serão adquiridos pelo sensor DHT22 e serão exibidos tanto no Monitor Serial quanto no Display LCD I2C: </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/2c742afb-ad54-4e2c-9d7b-dca568c88a82">
</div>

<br>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/3c42cb94-3b94-46e0-a161-84b9d4e0aca6">
</div>

<br>

<h2 align="center"> Acessando os Dados na Rede </h2>
<p align="justify"> Agora que o projeto está pronto e operacional, é crucial testar se os valores estão sendo enviados pela rede. Para isso, acesse o Google Colab e utilize o código disponibilizado neste repositório, especificamente o Paho MQTT. Essa ferramenta é fundamental para estabelecer a comunicação direta com o broker. </p>
<p> Primeiro faça a instalação do Paho MQTT </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/a299202b-d004-42aa-9f11-8dfc7e0e7bb9">
</div>

<br>

<p> Em seguida, realize as modificações nos tópicos conforme as instruções no código do projeto. Certifique-se de ajustá-los de acordo com as especificações fornecidas e, posteriormente, execute o código no Google Colab para garantir o correto envio e recebimento dos valores na rede. </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/4a345aa9-3a87-40b1-a0dd-3ebd7d28720b">
</div>

<br>

<p> Após executar o código, os valores de temperatura e umidade serão exibidos, semelhantemente ao que é mostrado no Monitor Serial e no Display LCD I2C. </p>

<div align="center">
  <img src="https://github.com/raigumieri/Sprint3_EDGE/assets/127215645/3dfa4131-2684-4d8c-8e41-d1dee3dea62a">
</div>

<h2 align="center"> Considerações Finais 📘 </h2>
<p align="center"> Diante de todos esses passos, podemos afirmar que o projeto está concluído. Se todos os procedimentos foram seguidos corretamente, será possível verificar que o projeto está funcionando conforme o esperado. Agradecemos pela atenção e pelo esforço ao acompanhar essas etapas! </p>
