# CADASTRO DOS CLIENTES DO DIA
clientes = []

qtd_clientes = int(input("Quantos clientes serão atendidos hoje? "))

for i in range(qtd_clientes):
    nome = input(f"Digite o nome do cliente {i+1}: ")
    clientes.append(nome)

precos = {
    1: ("Cabelo", 30),
    2: ("Barba", 20),
    3: ("Bigode", 10),
    4: ("Sobrancelha", 15)
}

clientes_atendidos = 0
quantidade_servicos = 0
faturamento = 0

print("\n" + "=" * 40)
print("      BARBEARIA DO SEU ZÉ")
print("=" * 40)

while clientes:

    cliente = clientes.pop(0)

    print("\n" + "-" * 40)
    print(f"Cliente da vez: {cliente}")
    print("-" * 40)

    print("1 - Cabelo      R$30")
    print("2 - Barba       R$20")
    print("3 - Bigode      R$10")
    print("4 - Sobrancelha R$15")

    escolha = input(
        "\nDigite os serviços desejados (ex: 1,2,4): "
    )

    servicos = escolha.split(",")

    total_cliente = 0

    print("\nServiços realizados:")

    for item in servicos:

        codigo = int(item)

        if codigo in precos:
            nome_servico, valor = precos[codigo]

            print(f"- {nome_servico}: R${valor}")

            total_cliente += valor
            faturamento += valor
            quantidade_servicos += 1

    print(f"Total do cliente: R${total_cliente}")

    clientes_atendidos += 1

print("\n" + "=" * 40)
print("      RELATÓRIO FINAL")
print("=" * 40)
print(f"Clientes atendidos : {clientes_atendidos}")
print(f"Serviços realizados: {quantidade_servicos}")
print(f"Faturamento total  : R${faturamento}")
print("=" * 40)
