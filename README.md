# Big-Data-Stream
ATIVIDADE SOMATIVA 1: SPARK STREAMING
Olá, caro estudante! Como uma das formas de avaliar o conhecimento obtido até este momento, vamos 
trabalhar com um projeto de modernização de uma demanda fictícia do Ministério da Saúde. Veja os detalhes 
abaixo.
Projeto de modernização
O Ministério da Saúde está com uma emergência e necessita que sejam tomadas as medidas adequadas em 
tempo hábil para combater a Covid-19. Devido aos sintomas mais comuns para casos positivos para 
coronavírus no último minuto e à atualização a cada 30 segundos da testagem em massa da população, está 
sendo gerado um grande número de informações que chegam a todo tempo de todos os estados e cidades 
do Brasil. Dado tal contexto, surgiu a necessidade de processar esse fluxo de dados em tempo real para que 
as medidas de controle da pandemia sejam tomadas de forma mais eficaz.
Para tal demanda, o Ministério Público abriu um edital emergencial para contratar um profissional que seja 
responsável por migrar o sistema tradicional de big data que está processando em lotes (batches) para 
processamento contínuo, ou seja, big data stream.
A modernização será feita com base nos exercícios da semana 3, com pequenas mudanças no enunciado, 
porém foi mantido o mesmo número da questão. É necessário modernizar a coleta de sete informações, 
sendo que três delas já foram atualizadas para big data stream por outra pessoa que também foi contratada 
para cumprir a demanda; as outras quatro informações estão sob sua responsabilidade. Você pode usar as 
informações resolvidas como exemplo para a resolução dos outros exercícios. Considerando o dataset
detalhado a seguir, extraia o conjunto de informações solicitadas.
Dataset de dados de Covid-19 no Brasil
Os dados utilizados neste trabalho são os mesmos do dataset da semana 3, porém é simulada uma stream
de dados. O dataset é enviado para um socket de rede na porta 4545. Cada linha do dataset é enviado para 
o socket a cada 100 milissegundos.
▪ Para alimentar a stream de dados, execute no terminal:
o cd ~/BigDataStream/apache_spark/Semana_4
o ./alimenta_stream.sh projeto (mantenha o comando executando)
▪ Dados relativos a pacientes que realizaram exames de Covid-19 no Brasil
▪ ~1k de instâncias
# Nome do campo Descrição
0 Id Identificador
1 dataNotificacao Data da notificação
2 dataInicioSintomas Data do início dos sintomas
 

# Nome do campo Descrição
3 dataNascimento Data de nascimento
4 sintomas Sintomas do paciente
5 profissionalSaude Relacionado a profissional de saúde
6 cbo Ocupação
7 condicoes Condições do paciente
8 estadoTeste Estado do teste
9 dataTeste Data do teste
10 tipoTeste Tipo de teste realizado
11 resultadoTeste Resultado do teste
12 paisOrigem País de origem do paciente
13 sexo Sexo do paciente
14 bairro Bairro do paciente
15 estado Estado do paciente
16 estadoIBGE Estado do paciente IBGE
17 municipio Município do paciente
18 municipioIBGE Município do paciente IBGE
19 cep CEP
20 origem Origem do paciente
21 cnes Código da unidade de saúde
22 estadoNotificacao Estado da notificação
23 estadoNotificacaoIBGE Estado da notificação IBGE
24 municipioNotificacao Município da notificação
25 municipioNotificacaoIBGE Município da notificação IBGE
26 numeroNotificacao Número da notificação
27 excluido ID de exclusão
28 validado Local de validação
29 idade Idade do paciente
30 dataEncerramento Data do encerramento da avaliação do paciente
31 evolucaoCaso Evolução do caso do paciente
32 classificacaoFinal Avaliação final do caso


# Informações a ser extraídas
1. Quantidade de pacientes positivos para coronavírus no último minuto e atualização a cada 30 segundos 
(resultadoTeste).
3. Quantidade de pacientes de acordo com o sexo e o resultado do teste nos últimos 50 segundos e atualização 
a cada 20 segundos (resultadoTeste).
4. Sintomas mais comuns para casos positivos para coronavírus no último minuto e atualização a cada 30 
segundos.
6.  Quantidade de casos positivos no Paraná nos últimos 40 segundos e atualização a cada 20 segundos.
15. Idade das mulheres positivas para Covid-19.
16. Município do Paraná com a maior quantidade de mulheres positivadas para Covid-19 no último minuto e 
atualização a cada 20 segundos.
17. Dia da semana com a maior quantidade de testes realizados nos últimos dois minutos e atualização a cada 
40 segundos.










ATIVIDADE SOMATIVA 2: Administração Apache Kafka


Você foi contratado por uma empresa para modernizar a forma como o fluxo de dados é transmitido. Atualmente, a empresa realiza a transmissão do fluxo de dados por meio de um socket de rede e gostaria que você, como um conhecedor dos conceitos e tecnologias de gestão de dados, o migrasse para o ambiente do Kafka. Esse projeto de modernização consiste em três etapas, descritas a seguir (você pode utilizar as videoaulas da semana 6 para auxiliar no desenvolvimento).
Criar um tópico com duas partições, chamado s7projeto.
Alimentar esse tópico com dois produtores. O primeiro produtor deve enviar as linhas do dataset da Covid-19, enquanto o segundo produtor deve enviar dados de clientes fake.
Criar um consumidor em Python que leia as duas partições do tópico s7projeto. O resultado deve mostrar as linhas do dataset da Covid-19 e os dados de clientes fake no mesmo tópico.
A entrega deve ser realizada no link indicado na semana 8.
