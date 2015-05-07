# BrCep

## O que é?

O BrCep é um gem que tem como objetivo buscar um endereço com base no seu CEP. Para isso ele utiliza um web service:

* RepublicaVirtual

## Como usar?

```ruby
BuscaEndereco.cep(22640100) 
BuscaEndereco.cep('22640100') 
BuscaEndereco.cep('22640-100') 
BuscaEndereco.cep('22.640-100') 
        
# => {:tipo_logradouro=>"Avenida", :logradouro=>"das Américas",
#     :bairro=>"Barra da Tijuca", :cidade=>"Rio de Janeiro",
#     :uf=>"RJ", :cep=>"22640100"} 
```

## O que acontece se o CEP informado tiver um formato inválido?

```ruby
BuscaEndereco.cep('12345678')   ==> RuntimeError: CEP 12345678 não encontrado.
```

P.S.: Nesse caso o endereço não foi encontrado porque não existe um endereço associado ao CEP 12345678. No entanto, pode haver situações em que CEPs que possuem endereços associados não tenham os seus endereços encontrados, no entanto, até o momento o web service utilizado cobrem todos os CEPs testados na prática.
