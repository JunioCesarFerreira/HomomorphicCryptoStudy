### Fundamentos de Criptografia

Nesta nota são apresentados alguns fundamentos necessários quando discutimos criptografia.


#### 1. Introdução à Criptografia

**História e Evolução:**
- **Antiguidade:**
  - *Cifra de César*: Um dos métodos mais antigos, onde cada letra do texto é substituída por outra letra um número fixo de posições à frente no alfabeto. Por exemplo, com uma chave de +3, A se torna D, B se torna E, e assim por diante.
  - *Cifra de Vigenère*: Uma técnica de substituição polialfabética que usa uma palavra-chave repetida para determinar a substituição de cada letra do texto. É mais segura que a Cifra de César devido à variação na substituição das letras.
- **Idade Média:**
  - *Cifras de substituição e transposição*: Uso de técnicas mais complexas para cifrar mensagens, como a troca de posições de letras no texto (transposição) ou substituição de letras por outras (substituição).
- **Era Moderna:**
  - *Máquinas criptográficas*: Desenvolvimento de dispositivos como a Enigma, usada pela Alemanha na Segunda Guerra Mundial. A complexidade mecânica da Enigma permitia um grande número de combinações possíveis, aumentando a segurança das mensagens cifradas.
  - *Teoria da Informação de Shannon*: Claude Shannon introduziu conceitos fundamentais como a entropia e a teoria da informação, que formam a base para a criptografia moderna. Ele mostrou que sistemas de criptografia devem ser analisados em termos de probabilidade e informação.

**Conceitos Básicos:**
- **Chave Pública e Privada:**
  - Na criptografia assimétrica, um par de chaves é usado: uma chave pública para cifrar dados e uma chave privada para decifrar. A chave pública pode ser distribuída livremente, enquanto a chave privada deve ser mantida em segredo.
- **Ciframento e Decifragem:**
  - *Ciframento (Encryption)*: Processo de transformar texto plano (plaintext) em texto cifrado (ciphertext) usando uma chave. Por exemplo, usar uma chave para aplicar uma função matemática que embaralha os dados.
  - *Decifragem (Decryption)*: Processo de transformar texto cifrado de volta em texto plano usando uma chave. Isso envolve aplicar uma função inversa àquela usada no ciframento.


#### 2. Tipos de Criptografia

**Criptografia Simétrica:**
- Usa a mesma chave para ciframento e decifragem. É eficiente, mas a segurança depende do segredo da chave. Exemplos incluem:
  - **AES (Advanced Encryption Standard)**: Um padrão de criptografia adotado pelo governo dos EUA, conhecido por sua eficiência e segurança. Ele opera em blocos de 128 bits usando chaves de 128, 192 ou 256 bits.
  - **DES (Data Encryption Standard)**: Um algoritmo de bloco mais antigo que opera em blocos de 64 bits usando uma chave de 56 bits. Considerado inseguro para muitas aplicações modernas devido ao pequeno tamanho da chave.

**Criptografia Assimétrica:**
- Usa um par de chaves: uma chave pública para ciframento e uma chave privada para decifragem. Embora seja mais lenta que a criptografia simétrica, facilita a troca segura de chaves e a assinatura digital. Exemplos incluem:
  - **RSA (Rivest-Shamir-Adleman)**: Baseado na dificuldade de fatoração de grandes números inteiros. É amplamente usado para segurança na internet.
  - **ECC (Elliptic Curve Cryptography)**: Baseado em propriedades das curvas elípticas. Oferece segurança comparável ao RSA com chaves menores, o que resulta em maior eficiência.

**Exemplos e Usos Comuns:**
- **AES:** Utilizado em uma variedade de aplicações, incluindo criptografia de dados em trânsito (como HTTPS) e em repouso (como discos criptografados).
- **RSA:** Utilizado em protocolos de segurança como SSL/TLS para a troca segura de chaves e em assinaturas digitais.
- **ECC:** Devido à sua eficiência, é usado em dispositivos móveis e sistemas com recursos limitados, bem como em certificação digital e autenticação.


#### 3. Matemática Básica para Criptografia

**Aritmética Modular:**
- *Definição:* Aritmética de restos. Dados dois inteiros $a$ e $n$, $a \mod n$ é o resto da divisão de $a$ por $n$.
- *Propriedades:* 
  - **Adição Modular:** $(a + b) \mod n = ((a \mod n) + (b \mod n)) \mod n$
  - **Multiplicação Modular:** $(a \cdot b) \mod n = ((a \mod n) \cdot (b \mod n)) \mod n$
  - **Exponenciação Modular:** $(a^b) \mod n = ((a \mod n)^b) \mod n$

**Exemplo de Aritmética Modular:**
- Suponha que $a = 17$ e $n = 5$. Então, $17 \mod 5 = 2$.
- Se $a = 4$, $b = 3$, e $n = 5$:
  - Adição Modular: $(4 + 3) \mod 5 = 7 \mod 5 = 2$
  - Multiplicação Modular: $(4 \cdot 3) \mod 5 = 12 \mod 5 = 2$
  - Exponenciação Modular: $4^3 \mod 5 = 64 \mod 5 = 4$

**Conceitos de Álgebra Linear:**
- *Vetores e Matrizes:* 
  - Vetores são listas de números que podem representar dados. Por exemplo, um vetor $\mathbf{v} = (v_1, v_2, \ldots, v_n)$.
  - Matrizes são arranjos bidimensionais de números que podem ser usadas para transformar vetores. Uma matriz $A$ de dimensões $m \times n$ pode transformar um vetor de dimensão $n$ em um vetor de dimensão $m$.
- *Multiplicação de Matrizes:*
  - Dados dois vetores $\mathbf{u} = (u_1, u_2, \ldots, u_n)$ e $\mathbf{v} = (v_1, v_2, \ldots, v_n)$, o produto escalar é $\mathbf{u} \cdot \mathbf{v} = \sum_{i=1}^n u_i v_i$.
  - A multiplicação de uma matriz $A$ por um vetor $\mathbf{x}$ resulta em um novo vetor, com cada componente sendo uma combinação linear dos componentes de $\mathbf{x}$ ponderados pelos elementos de $A$. Por exemplo, se $A$ é uma matriz $2 \times 2$ e $\mathbf{x}$ é um vetor $2 \times 1$, o produto $A\mathbf{x}$ resulta em um vetor $2 \times 1$.
