#Animal (Herança Múltipla)
import random

class Animal:
    def __init__(self,nome):
        self.nome = nome
    
    def Exibir_Descrição(self):
        print('nome do animal: ',self.nome)
    
class Carnivoro(Animal):
    def __init__(self,nome):
        super().__init__(nome)

    def caçar(self):
        print(self.nome,'está caçando')
    
    def Exibir_Descrição(self):
        super().Exibir_Descrição()
        print('animal carnívoro')

class Herbivoro(Animal):
    def __init__(self, nome):
        super().__init__(nome)
    
    def pastar(self):
        print(self.nome,'está pastando')
    
    def Exibir_Descrição(self):
        super().Exibir_Descrição()
        print('animal herbívoro')
    
class Onivoro(Carnivoro,Herbivoro):
    def __init__(self, nome):
        super().__init__(nome)
    
    def comer(self):
        num = random.randint(0,1)
        if num == 0:
            self.caçar()
        else:
            self.pastar()
    
    def Exibir_Descrição(self):
        super().Exibir_Descrição()
        print('animal onívoro')

leão = Carnivoro('Simba')
leão.Exibir_Descrição()
leão.caçar()

vaca = Herbivoro('Otis')
vaca.Exibir_Descrição()
vaca.pastar()

cobra = Onivoro('Naja')
cobra.Exibir_Descrição()
cobra.comer()
