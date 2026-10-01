# prova1sistemasdistribuidos

Nome: Igor Soares Da Silva
RA: a6004915dc18d0e73dee

# Problema da empresa
Dar a tarifa de 3 Reais para uma entrega de 8KM

#Arquivos
from xmlrpc.server import SimpleXMLRPCServer;
def calcular_entrega(distancia, tarifa_por_quilometro):
    return distancia * tarifa_por_quilometro

servidor = SimpleXMLRPCServer(("localhost", 8003))

servidor.register_function(
    calcular_entrega,
    "calcular_entrega"
)

print("Servidor RPC aguardando solicitações...")

servidor.serve_forever()


from xmlrpc.client import ServerProxy

servidor = ServerProxy("http://localhost:8003/")

resultado = servidor.calcular_entrega(8, 3)

print("Valor da entrega:", resultado)

#Resultado do teste
PS C:\Users\aluno\Documents\prova> & "C:\Program Files\Python313\python.exe" c:/Users/aluno/Documents/prova/servidor.py
Servidor RPC aguardando solicitações...

No linha:1 caractere:41
+ ... Files\Python313\python.exe" c:/Users/aluno/Documents/prova/cliente.py
+                                 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Token 'c:/Users/aluno/Documents/prova/cliente.py' inesperado na expressão ou instrução.
    + CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : UnexpectedToken

