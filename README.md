
print("=== CALCULADORA DE PROBABILIDADE ===")

casos_favoraveis = int(input("Digite o número de casos favoráveis: "))

casos_possiveis = int(input("Digite o número de casos possíveis: "))
 probabilidade = (casos_favoraveis / casos_possiveis) * 100

print("A probabilidade é:", probabilidade, "%")
