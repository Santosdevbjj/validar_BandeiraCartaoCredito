## Detalhes Técnicos do Projeto 


✅ **Detalhes técnicos importantes: Bandeiras de Cartão de Crédito**



**MasterCard:** Começa com 51-55 ou 2221-2720, 16 dígitos.

**Visa:** Começa com 4, 16 dígitos.

**American Express:** Começa com 34 ou 37, 15 dígitos.

**Diners Club:** Começa com 300-305, 36 ou 38, 14 dígitos.

**Discover:** Começa com 6011 ou 65, 16 dígitos.

**enRoute:** Começa com 2014 ou 2149, 15 dígitos.

**JCB:** Começa com 2131, 1800 ou 35, com 15 a 16 dígitos.

**Voyager:** Começa com 8699, 15 dígitos.

**HiperCard:** Começa com 38 (19 dígitos) ou 60 (16 dígitos).

**Aura:** Começa com 50, de 15 a 18 dígitos.



O código esta em Python com interface gráfica utilizando Tkinter, que identifica a bandeira de um cartão de crédito com base no número informado e valida o número utilizando o Algoritmo de Luhn. O código está amplamente comentado para facilitar o entendimento.



✅ **Explicação do Código:**

identificar_bandeira(numero_cartao): Utiliza expressões regulares para identificar a bandeira do cartão com base no número informado.

**validar_luhn(numero_cartao):** Implementa o Algoritmo de Luhn para verificar a validade do número do cartão. O algoritmo funciona da seguinte maneira:

1. Inverte o número do cartão.


2. Dobra cada segundo dígito (começando do segundo dígito da direita).


3. Se o resultado da multiplicação for maior que 9, subtrai 9.


4. Soma todos os dígitos.


5. Se o total for múltiplo de 10, o número é válido.



**validar_cartao():** Função chamada ao clicar no botão "Validar Cartão". Ela obtém o número do cartão, verifica se contém apenas dígitos, identifica a bandeira e valida o número utilizando o Algoritmo de Luhn. O resultado é exibido na interface gráfica.

**Interface Gráfica (Tkinter):**

Janela principal com título e tamanho fixo.

Campo de entrada para o número do cartão.

Botão "Validar Cartão" que chama a função de validação.

Rótulo para exibir o resultado da validação.



🧪 **Como Executar:**

1. Copie o código acima e cole em um arquivo chamado validador_cartao_gui.py.


2. **Execute o arquivo utilizando o Python:**

python validador_cartao_gui.py


3. **Na interface gráfica,** digite o número do cartão de crédito (somente números) e clique em "Validar Cartão".


4. **O resultado** será exibido abaixo do botão, indicando a bandeira identificada e se o cartão é válido ou inválido conforme o Algoritmo de Luhn.



**Caso deseje realizar testes,** você pode executar o programa e informar diferentes números de cartão (sem espaçamentos ou traços) para verificar qual das bandeiras é identificada. Por exemplo:

- **MasterCard:** `5123456789012345`  
- **Visa:** `4123456789012345`  
- **American Express:** `371234567890123`  
- **Diners Club:** `30512345678901`  
- **Discover:** `6011123456789012`  
- **enRoute:** `201412345678901`  
- **JCB:** `3528123456789012`  
- **Voyager:** `8699123456789012`  
- **HiperCard:** `38411234567890`  
- **Aura:** `5012345678901234`




 
