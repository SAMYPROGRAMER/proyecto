import random


def menu():
    menu = '''
    \t************************************************************************************************\n
    \t\t\t\t\t\t\t"Casa de fortuna game"
    \n\t\t\t\t\t\t"# Tente a sorte e faz a sua fortuna #"
    \t\t\t\t"# escolher um número de 0 a 20 de modo a ganhar um presente #"\n
    \t************************************************************************************************
    '''
    print(menu)


menu()
op = ['[um carro 0km]', '[uma moto BMW]', '[2 Tv]', '[uma casa]', '[1 milhão de reais R$]', '[uma viagem para EUA]']  # noqa

n_sorte = random.randint(1, 20)
premius = random.choice(op)

tentativas = 3
i = 0

for i in range(3):
    escolha = int(input('escolha um numero da sorte > '))
    if escolha <= 20:
        if escolha == n_sorte:
            print("\n********************************************************")
            print("\nParabens!!!, você escolheu o número da sorte\n")
            print('Ganhou ', premius, ' de premio!!\n')
            break
        else:
            tentativas -= 1
            if tentativas != 0:
                print("\nErrou o número!!!! restam ", tentativas, 'tentativas')
        if tentativas == 0:
            print("\n********************************************************")
            print("Quepena!! Você não conseguiu o premio\nFim do jogo!!")
            break
