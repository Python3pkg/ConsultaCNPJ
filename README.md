# ConsultaCNPJ
Consulta de dados por CNPJ

# Como utilizar
Veja alguns exemplos de uso para este módulo

## Retornando um CNPJ com mascara
Este código retorna o CNPJ com a mascara padrão de para exibição
```python
import CNPJ

cod       = '33592510000154'
CGC       = CNPJ.ConsultaCNPJ()
MaskedCGC = CGC.maskedCNPJ(cod)

print(MaskedCGC)
```

## Validando um CNPJ
Faz o checksum do CNPJ e retorna ```True``` se for válido ou ```False```
```python
import CNPJ

cod       = '33592510000154'
CGC       = CNPJ.ConsultaCNPJ()
Valid     = CGC.Checksum(cod)

print(Valid)
```

## Consultando dados pelo CNPJ
Busca os dados em uma consulta via CNPJ no banco de dados da Receita Federal
```python
import CNPJ

CGC   = CNPJ.ConsultaCNPJ()
data  = CGC.newQuery('33592510000154', '02916265000160')

for cnpj, dados in data.items():
    print('\n\n\n>>> Consultando %s' % query.maskedCNPJ(cnpj))
        for atributos, valores in dados.items():
            if isinstance(valores, list):    
            print('%s' % atributos)
            for item in valores:
                for Codigo, Texto in item.items():
                    print('    %s: %s' % (Codigo, Texto))
        else:
            print('%s: %s' % (atributos, valores))
```
