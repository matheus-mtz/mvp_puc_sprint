# mvp_puc_sprint1
MVP Pós-Graduação em Ciência de Dados e Analytics PUC-Rio
U.S. Powerlifting Competition Data 2015-2020

Download: https://www.kaggle.com/datasets/brianmcabee/us-powerlifting-competition-data-2015now
data e horário de download: 25/04/2023 14:00

Descrição da base de dados:

Este conjunto de dados é composto por levantadores de peso que competiram nos Estados Unidos em eventos de força total de 2015 até 2020.

Descrição das variáveis:

- Name (nome):

Obrigatório. O nome do levantador na codificação UTF-8.

Levantadores que compartilham o mesmo nome são distinguidos pelo uso de um símbolo # seguido por um número único. Por exemplo, dois levantadores chamados John Doe teriam os valores Name John Doe #1 e John Doe #2, respectivamente.

- Sex (sexo):

Obrigatório. A categoria de sexo na qual o levantador competiu, M, F ou Mx.

Mx (pronuncia-se Muks) é um título neutro em termos de gênero - como Mr e Ms - originário do Reino Unido. É uma categoria de sexo abrangente que é particularmente apropriada para levantadores não-binários.

- Event (evento):

Obrigatório. O tipo de competição que o levantador entrou. Para os fins deste conjunto de dados, todos os valores do evento serão SBD para levantadores que competiram em eventos testando seu agachamento, supino e levantamento terra.

- Equipment (equipamento):

Obrigatório. A categoria do equipamento sob a qual os levantamentos foram executados. Para os propósitos deste conjunto de dados, todos os valores serão Raw, pois contém informações sobre levantadores que utilizam equipamentos mínimos.

- Age (idade):

Opcional. A idade do levantador na data de início da competição, se conhecida.

As idades podem ser de dois tipos: exatas ou aproximadas. As idades exatas são fornecidas como números inteiros, por exemplo, 23. As idades aproximadas são fornecidas como um número inteiro mais 0,5, por exemplo, 23,5.

As idades aproximadas significam que o levantador pode ter uma das duas idades possíveis. Para uma idade aproximada de n + 0,5, as idades possíveis são n ou n+1. Por exemplo, um levantador com a idade especificada de 23,5 anos pode ter 23 ou 24 anos - não temos informações suficientes para saber.

As idades aproximadas ocorrem porque algumas federações nos fornecem apenas informações sobre o ano de nascimento. Portanto, outra maneira de pensar sobre as idades aproximadas é que 23,5 implica que o levantador fará 24 anos naquele ano.

- AgeClass:

Opcional. A classe de idade na qual o filtro se enquadra, por exemplo 40-45. Essas classes são baseadas na idade exata do levantador no dia da competição.

AgeClass é mais útil porque às vezes uma federação relata que um levantador competiu na divisão 50-54 sem fornecer mais informações sobre a idade. Dessa forma, ainda podemos marcá-los como 50-54, mesmo que a Agecoluna esteja vazia.

- BirthYearClass:

Opcional. A classe do ano de nascimento na qual o filtro se enquadra, por exemplo 40-49. As idades na faixa são as idades mais antigas possíveis para o levantador naquele ano. Por exemplo, 40-49significa "do ano em que o levantador completa 40 anos até o ano completo em que o levantador completa 49 anos".

BirthYearClass é usado principalmente pela IPF e pelas afiliadas da IPF. Federações não-IPF tendem a usar AgeClassem seu lugar.

- Division:

Opcional. Texto UTF-8 de formato livre descrevendo a divisão da competição, como Openou Juniors 20-23ou Professional.

Algumas federações são configuradas em nosso banco de dados, o que significa que concordamos com um conjunto limitado de opções de divisão para essa federação e reescrevemos seus resultados para usar apenas esse conjunto, e os testes reforçam isso. Mesmo assim, as divisões não são padronizadas entre as federações configuradas: é realmente um texto de formato livre, apenas para fornecer contexto.

Informações sobre idade não devem ser extraídas do Division, mas da AgeClasscoluna.

- Body Weight Kg:

Opcional. O peso corporal registrado do levantador no momento da competição, com duas casas decimais.

- WeightClassKg:

Opcional. A classe de peso em que o levantador competiu, com duas casas decimais.

As classes de peso podem ser especificadas como máximo ou mínimo. Máximos são especificados apenas pelo número, por exemplo 90significa "até (e incluindo) 90kg." os mínimos são especificados por um +à direita do número, por exemplo, 90+significa "acima (e excluindo) 90kg".

- Squat1Kg, Bench1Kg, Deadlift1Kg (Agachamento1Kg, Supino1Kg, Deadlift1Kg):

Opcional. Primeiras tentativas para cada agachamento, supino e levantamento terra, respectivamente. Máximo de duas casas decimais.

Valores negativos indicam tentativas com falha. 
Nem todas as federações relatam informações sobre tentativas. Algumas federações relatam apenas as melhores tentativas.

- Squat2Kg, Bench2Kg, Deadlift2Kg (Agachamento2Kg, Supino2Kg, Deadlift2Kg):

Opcional. Segundas tentativas para cada agachamento, supino e levantamento terra, respectivamente. Máximo de duas casas decimais.

Valores negativos indicam tentativas com falha.

Nem todas as federações relatam informações sobre tentativas. Algumas federações relatam apenas as melhores tentativas.

- Squat3Kg, Bench3Kg, Deadlift3Kg (Agachamento3Kg, Supino3Kg, Deadlift3Kg):

Opcional. Terceiras tentativas para cada agachamento, supino e levantamento terra, respectivamente. Máximo de duas casas decimais.

Valores negativos indicam tentativas com falha.

Nem todas as federações relatam informações sobre tentativas. Algumas federações relatam apenas as melhores tentativas.

- Squat4Kg, Bench4Kg, Deadlift4Kg (Agachamento4Kg, Supino4Kg, Deadlift4Kg):

Opcional. Quartas tentativas para cada agachamento, supino e levantamento terra, respectivamente. Máximo de duas casas decimais.

Valores negativos indicam tentativas com falha.

As quartas tentativas são especiais, pois não contam para o TotalKg. Eles são usados ​​para gravar registros de levantamento único.

- Best3SquatKg, Best3BenchKg, Best3DeadliftKg (Melhor3AgachamentoKg, Melhor3SupinoKg, Melhor3DeadliftKg):

Opcional. Máximo das três primeiras tentativas bem-sucedidas de levantamento.

Raramente pode ser negativo: é usado por algumas federações para relatar o menor peso que o levantador tentou e falhou.

- TotalKg:

Opcional. Soma de Best3SquatKg, Best3BenchKg, e Best3DeadliftKg, se todos os três levantamentos foram bem-sucedidos. Se um dos levantamentos falhou, ou o levantador foi desqualificado por algum outro motivo, o TotalKgestá vazio.

Raramente, principalmente para competições mais antigas, uma federação relatará o total, mas não qualquer informação de levantamento.

- Place (Colocação):

Obrigatório. A colocação registrada do levantador na divisão dada no final da competição.

Os valores são os seguintes:
Número positivo: o lugar onde o levantador entrou.
G: Levantador convidado. O levantador conseguiu, mas não era elegível para prêmios.
DQ: Desqualificado. Observe que o DQ pode ser por motivos processuais, não apenas por tentativas malsucedidas.
DD: Desqualificação por doping. O levantador falhou em um teste de drogas.
NS: No-Show. O levantador não apareceu no dia da competição.
Wilks
Opcional. Um número positivo se os pontos de Wilks pudessem ser calculados, vazio se o levantador fosse desqualificado.
Wilks é a fórmula mais comum usada para determinar o Melhor Levantador em uma competição de powerlifting.

- Tested (testado):

Opcional. Yesse o levantador entrou em uma categoria testada para drogas, deixe em branco caso contrário.

Observe que isso registra se os resultados contam como testado para drogas , o que não implica que o levantador realmente fez um teste de drogas. As federações não relatam quais levantadores, se houver, foram submetidos a testes de drogas.

- Federation (Federação):

Obrigatório. A federação que sediou o encontro.

Observe que isso pode ser diferente da federação internacional que sancionou o encontro. Por exemplo, as reuniões da USPA são sancionadas pelo IPL, mas registramos as reuniões da USPA como USPA.
A lista completa de valores de Federação válidos é definida por modules/opltypes/src/federation.rs . Os comentários nesse arquivo ajudam a explicar o que cada valor de federação significa.

- Parental Federation:
 
Opcional. A federação mais alta que sancionou o encontro, geralmente o órgão internacional.
Por exemplo, o ParentFederationpara o USAPLe EPAé IPF.

- Date (Data):

Obrigatório. A data de início do encontro no formato ISO 8601 . ISO 8601 se parece com YYYY-MM-DD: por exemplo, 1996-12-04seria 4 de dezembro de 1996.
As reuniões que duram mais de um dia têm apenas a data de início registrada.

- MeetState (Estado):

Opcional. O estado, província ou região em que o encontro foi realizado.

- MeetName:

Obrigatório. O nome do encontro.
O nome é definido para nunca incluir o ano ou a federação. Por exemplo, o encontro chamado oficialmente 2019 USAPL Raw National Championshipsteria o MeetName Raw National Championshps.
