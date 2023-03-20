from time import sleep


class Node:
    def __init__(self, data=None, next=None):
        self.data = data
        self.next = next


class LinkedList:
    def __init__(self):
        self.head = None


    def print(self):
        if self.head is None:
            print('Lista Vazia')
            return
        
        itr = self.head
        show = ''

        count = 1
        while itr:
            if itr.next:
                show += f'{str(count)}. {str(itr.data)} --> '
            else:
                show += f'{str(count)}. {str(itr.data)}'
            itr = itr.next
            count += 1

        print(show)

    
    def add_at_end(self, data):
        if self.head is None:
            self.head = Node(data, None)
            return
        
        itr = self.head
        while itr.next:
            itr = itr.next
        
        itr.next = Node(data, None)

    
    def is_there(self, item):
        itr = self.head
        
        while itr:
            if itr.data == item:
                return True
            else:
                itr = itr.next
    

def separate():
    print('=-' * 30)
            

print('--Iniciando o check-in no Hotel Beira Mar!--')
sleep(1)

count_rooms = 0
rooms = LinkedList()
price = 0 #full price: $400
ctn = ''
while True:
    separate()
    menu = int(input('''Insira a opção desejada:
[0] Adicionar Quarto
[1] Pesquisar Hóspede
[999] Finalizar
[?] '''))
    
    separate()
    
    if menu == 999:
        print('Finalizando...')
        sleep(0.5)
        break
    
    while True:
        if menu == 0:
            sleep(0.5)
            bedroom = int(input('''Insira o tipo de quarto:
[0] Quarto SOLTEIRO
[1] Quarto CASAL
[2] Quarto FAMÍLIA
[?] '''))
            if bedroom == 0:
                print('Cadastrando para o quarto SOLTEIRO(1 pessoa).')
                sleep(0.5)
                
                for c in range(1):
                    name = str(input(f'Insira o NOME do(a) hóspede: ')).strip().title()
                    age = int(input(f'Insira a IDADE do(a) hóspede: '))
                    rooms.add_at_end(name)
                    if age > 18:
                        price += 400
                    else:
                        price += 200
                
                count_rooms += 1

            if bedroom == 1:
                print('Cadastrando para o quarto CASAL(2 pessoas).')
                sleep(0.5)
                
                for c in range(2):
                    name = str(input(f'Insira o NOME do(a) {c+1}º hóspede: ')).strip().title()
                    age = int(input(f'Insira a IDADE do(a) {c+1}º hóspede: '))
                    rooms.add_at_end(name)
                    if age > 18:
                        price += 400
                    else:
                        price += 200
                
                count_rooms += 1
            
            if bedroom == 2:
                print('Cadastrando para o quarto FAMÍLIA(5 pessoas).')
                sleep(0.5)

                for c in range(5):
                    name = str(input(f'Insira o NOME do(a) {c+1}º hóspede: ')).strip().title()
                    age = int(input(f'Insira a IDADE do(a) {c+1}º hóspede: '))
                    rooms.add_at_end(name)
                    if age > 18:
                        price += 400
                    else:
                        price += 200

                count_rooms += 1
            

            ctn = str(input('Continuar? [S/N] ')).upper().strip()
            while True:
                if ctn not in 'SN':
                    ctn = str(input('Continuar? [S/N] ')).upper().strip()
                else:
                    break
            if ctn == 'N':
                print(f'Preço atual: R${price}.')
                sleep(1)
                break

        elif menu == 1:
            search = str(input('Qual hóspede deseja procurar?\n--> ')).strip().title()
            if rooms.is_there(search) == None:
                print(f'{search} não está hospedado(a) no hotel.')
                sleep(0.5)
                break
            elif rooms.is_there(search) == True:
                print(f'{search} está hospedado(a) no hotel.')
                separate()
                sleep(0.5)
                break


print(f'{count_rooms} quarto(s) adicionados com sucesso!')
sleep(0.5)
print('Carregando lista de hóspedes:')
sleep(0.5)
rooms.print()
sleep(0.5)
print(f'Preço final: R${price}.')
