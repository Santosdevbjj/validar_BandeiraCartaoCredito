
import re
import tkinter as tk
from tkinter import messagebox

def identificar_bandeira(numero_cartao):
    """
    Identifica a bandeira do cartão de crédito com base no número.
    """
    bandeiras = {
        'MasterCard': r'^(5[1-5][0-9]{14}|2[2-7][0-9]{14})$',
        'Visa 16 Dígitos': r'^4[0-9]{15}$',
        'American Express': r'^3[47][0-9]{13}$',
        'Diners Club': r'^3(?:0[0-5]|[68][0-9])[0-9]{11}$',
        'Discover': r'^6(?:011|5[0-9]{2})[0-9]{12}$',
        'enRoute': r'^(2014|2149)[0-9]{11}$',
        'JCB': r'^(?:2131|1800|35\d{3})\d{11}$',
        'Voyager': r'^8699[0-9]{11}$',
        'HiperCard': r'^(38[0-9]{17}|60[0-9]{14})$',
        'Aura': r'^50[0-9]{14,17}$'
    }

    for bandeira, padrao in bandeiras.items():
        if re.match(padrao, numero_cartao):
            return bandeira

    return "Bandeira desconhecida"

def validar_luhn(numero_cartao):
    """
    Valida o número do cartão de crédito utilizando o Algoritmo de Luhn.
    """
    # Inverte o número do cartão e converte para lista de inteiros
    digitos = [int(d) for d in str(numero_cartao)][::-1]
    soma = 0

    for i, d in enumerate(digitos):
        if i % 2 == 1:
            d *= 2
            if d > 9:
                d -= 9
        soma += d

    return soma % 10 == 0

def validar_cartao():
    """
    Função chamada ao clicar no botão 'Validar Cartão'.
    """
    numero = entrada_numero.get().strip()

    if not numero.isdigit():
        messagebox.showwarning("Entrada inválida", "Por favor, insira apenas números.")
        return

    bandeira = identificar_bandeira(numero)
    valido = validar_luhn(numero)

    if bandeira == "Bandeira desconhecida":
        resultado_var.set("Bandeira: Desconhecida")
    else:
        resultado_var.set(f"Bandeira: {bandeira}")

    if valido:
        resultado_var.set(resultado_var.get() + "\nCartão Válido (Algoritmo de Luhn)")
    else:
        resultado_var.set(resultado_var.get() + "\nCartão Inválido (Algoritmo de Luhn)")

# Criando a janela principal
janela = tk.Tk()
janela.title("Validador de Cartão de Crédito")
janela.geometry("400x250")
janela.resizable(False, False)

# Rótulo de instrução
rotulo_instrucao = tk.Label(janela, text="Digite o número do cartão de crédito:")
rotulo_instrucao.pack(pady=10)

# Campo de entrada
entrada_numero = tk.Entry(janela, width=30, font=("Arial", 12))
entrada_numero.pack()

# Botão para validar
botao_validar = tk.Button(janela, text="Validar Cartão", command=validar_cartao, bg="#4CAF50", fg="white", font=("Arial", 12))
botao_validar.pack(pady=10)

# Rótulo para exibir o resultado
resultado_var = tk.StringVar()
rotulo_resultado = tk.Label(janela, textvariable=resultado_var, font=("Arial", 12, "bold"))
rotulo_resultado.pack(pady=10)

# Iniciando o loop da interface
janela.mainloop()  





