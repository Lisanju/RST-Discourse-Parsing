# Analisador Discursivo pelo método RST
A proposta deste repositório é estudar a produção de um analisador discursivo de um sistema de Processamento de Linguagem Natural (NLP) simbólico, isso através do método RST - Teoria de Estrutura Retórica, de Mann e Thompson (1987), uma das principais teorias discursivas. Trata-se de um projeto feito para a disciplina 'Laboratório 5 - PLN' no curso de Linguística - UFSCar.

## Sobre os sistemas de PLN
De um modo geral, o PLN busca a automação de tarefas linguísticas específicas que envolvem a interpretação e a geração de uma língua natural. Como exemplo de sistemas ou aplicações do PLN, temos:

- Síntese de voz;
- Reconhecimento de fala;
- Sistemas de diálogo;
- Tradutores automáticos;
- Revisores (ortográficos, gramaticais e estilísticos);
- Ferramentas de auxílio à escrita;
- Sumarizadores automáticos;
- Simplificadores textuais;
- Sistemas de perguntas e respostas.

Para isso, utilizamos dois recursos: Léxico, uma espécie de dicionário, que pode contar as palavras de uma língua e suas diversas características; Gramática, um conjunto de regras descritas segundo um modelo gramatical, que (i) estabelecem as estruturas das sentenças de uma língua e (ii) permitem, juntamente com o léxico, reconhecer e gerar sentenças dessa língua. Além disso, o PLN possui ferramentas que auxiliam em suas tarefas:

- Segmentadores textuais: palavras (tokenizador), sentenças (sentenciador), parágrafos, tópicos;
- Stemmers (“radicalizador”), lematizadores, nominalizadores;
- Etiquetadores morfossintáticos (taggers);
- Analisadores sintáticos;
- Analisadores semânticos;
- Analisadores discursivos;
- Alinhadores textuais: lexicais, sentenciais, etc;
- Concordanceadores, “contadores de palavras” (word counting) etc.

## Discurso vs Discursos

“Um discurso é uma sequência extensa de sentenças produzida por uma ou mais pessoas com o objetivo de convencer ou trocar informação”. – Mitkov, R. (2004). The Oxford Handbook of Computational Linguistics.

“Um discurso é qualquer cadeia/segmento de língua – usualmente maior que uma sentença. Livros-texto, romances, relatórios meteorológicos e conversações (diálogos) são tipos de discursos” – Russel, S. & Norvig, P. (2003). Artificial Intelligence: A Modern Approach.

Para a linha americana, a concepção de discurso encara um texto como algo a maisdo que uma simples sequência de sentenças justapostas. Isso porque possui uma estrutura altamente elaborada, com diversas propriedades em níveis variados:

- Coesão;
- Coerência;
- Progressão temática;
- Tópicos;
- Intenções;
- Estilo.

Então, é possível dizer que há uma “sintaxe textual”.

## Coesão vs Coerência
A coesão é o uso de mecanismos linguísticos para conectar unidades textuais, como uma “cola textual”:

- Palavras (mesma palavra, sinônimos, hiperônimos, etc.);
- Expressões referenciais;
- Marcadores discursivos, frases e palavras indicativas;
- Pontuação;
- Paralelismo sintático;
- Etc.

Por outro lado, a coerência é a relação de significado entre unidades textuais, como o significado do discurso pode ser inferido a partir das partes textuais: conteúdo textual.

O discurso está entre os níveis de análise da língua mais abstratos. Para Koch & Travaglia (2002), ele envolve a situação de comunicação entre escritor/falante e leitor/ouvinte.

## RST - Teoria de Estrutura Retórica
A RST é uma das principais teorias discursivas usadas no PLN, contendo 23 relações.

A ideia é que a RST descreve relações entre o conteúdo de segmentos discursivos em termos funcionais, como através de proposições. A premissa é que todo texto tem uma estrutura retórica subjacente que permite recuperar o objetivo comunicativo que o escritor do texto pretendia atingir ao escrevê-lo.

Os principais elementos da RST são as estruturas retóricas, compostas por segmentos discursivos inter-relacionados por meio de relações retóricas. Os segmentos discursivos: unidades mínimas de significado que compõem um texto.

Cada segmento discursivo representa um núcleo (N) ou um satélite (S).

- Núcleo ou unidade nuclear: expressa a informação principal sendo, portanto, mais relevante do que o satélite;
- Satélite: apresenta informação adicional, a qual exerce influência na interpretação do leitor sobre a informação apresentada em N.

Por exemplo, tomemos o texto abaixo:

```
Ele queria jantar com Suzana, mas também queria jogar tênis com Janete. Essa indecisão o deixou louco.
```

- a - `Ele queria jantar com Suzana,`;
- b - `mas também queria jogar tênis com Janete.`;
- c - `Essa indecisão o deixou louco.`.

Dividimos o texto em três segmentos discursivos a, b e c. Cada segmento se conecta através de uma relação retórica.

O segmento b expressa uma relação retórica de contraste com o segmento a, em que ambos carregam informações relevantes apesar de constratantes. Dizemos, então que estão conectados através da relação CONTRAST, que é multinuclear, isto é, conecta um N (segmento a) a outro N (segmento b).

Agora, a conexão entre a e b se conectam com o segmento c através dedasdasda uma relação retórica de causa. Isto é, a informação expressa no segmento c é a informação principal em relação aos outros segmentos. A causa da informação do segmento c são os segmentos conectados a e b. Por isso, dizemos que estão conectados através de uma relação CAUSE, que é mononuclear, isto é, conecta um N (segmento c) com um S (segmento a conectado com b).

![image](https://github.com/Lisanju/RST-Discourse-Parsing/assets/106002045/32439992-0c1d-4e37-86eb-ffb64c798614)

