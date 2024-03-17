conjuntos = []

with open('conjuntos.txt', 'r') as arquivo:
    for linha in arquivo:
        linha = linha.strip()
        conjuntos.append(linha.split(","))

op = input("Digite a operação desejada (U = União, I = Interseção, D = Diferença, C = Produto Cartesiano): ")

if op == 'U':
    for i in range(len(conjuntos)):
        if conjuntos[i] == ['U']:
            aux1 = set(conjuntos[i+1])
            aux2 = set(conjuntos[i+2])
            print(f"União: conjunto1 {aux1}, conjunto2 {aux2}. Resultado = {aux1 | aux2}")
elif op == 'I':
    for i in range(len(conjuntos)):
        if conjuntos[i] == ['I']:
            aux1 = set(conjuntos[i + 1])
            aux2 = set(conjuntos[i + 2])
            print(f"Intersecção: conjunto1 {aux1}, conjunto2 {aux2}. Resultado = {aux1 & aux2}")
elif op == 'D':
    for i in range(len(conjuntos)):
        if conjuntos[i] == ['D']:
            aux1 = set(conjuntos[i + 1])
            aux2 = set(conjuntos[i + 2])
            print(f"Diferença: conjunto1 {aux1}, conjunto2 {aux2}. Resultado = {aux1 - aux2}")
elif op == 'C':
    for i in range(len(conjuntos)):
        if conjuntos[i] == ['C']:
            compl = {0}
            compl.clear()
            sm = []
            aux1 = set(conjuntos[i + 1])
            aux2 = set(conjuntos[i + 2])
            print(f"")
            for j in range(len(conjuntos[i+1])):
                for k in range(len(conjuntos[i+2])):
                    sm.append(f"{conjuntos[i+1][j]} X {conjuntos[i+2][k]}")
                    compl = set(sm)
            print(f"Cartesiano: conjunto1 {aux1}, conjunto2 {aux2}. Resultado = {compl}")
else:
    print("não existe essa opção.")
