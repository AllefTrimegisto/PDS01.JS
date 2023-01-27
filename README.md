# PDS01.JS

class Computer:
    def __init__(self, ram, hdd, cpu, type):
        self._ram = ram
        self._hdd = hdd
        self._cpu = cpu
        self._type = type

    def get_ram(self):
        return self._ram

    def get_hdd(self):
        return self._hdd

    def get_cpu(self):
        return self._cpu

    def get_type(self):
        return self._type

    def __str__(self):
        return f"Type: {self._type}, RAM: {self._ram}GB, HDD: {self._hdd}GB, CPU: {self._cpu}GHz"

class ComputerFactory:
    @staticmethod
    def create_computer(type, ram, hdd, cpu):
        if type == "pc":
            return PC(ram, hdd, cpu)
        elif type == "server":
            return Server(ram, hdd, cpu)
        else:
            return None

class PC(Computer):
    def __init__(self, ram, hdd, cpu):
        super().__init__(ram, hdd, cpu, "pc")

class Server(Computer):
    def __init__(self, ram, hdd, cpu):
        super().__init__(ram, hdd, cpu, "server")

# exemplo de uso
factory = ComputerFactory()
computer = factory.create_computer("pc", 8, 1000, 3.4)
print(computer) # imprimirá: Type: pc, RAM: 8GB, HDD: 1000GB, CPU: 3.4GHz
