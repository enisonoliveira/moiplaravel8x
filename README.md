# moiplaravel8.x
-> pacote moip para rodar no php 7.2.4 ao 8.2 
-> Laravel 8.x


configuração em app.php adicione as confings do moip

 [providers]
 Moip\Providers\MoipServiceProvider::class

[aliases]

 'MoipApp'    => Moip\Facades\Moip::class,
 
 configuraça composer.json
 
 na tag autolad adicion a linha do pacote moip em psr-4
 
 "autoload": {
        "psr-4": 
            "Moip\\": "moipapp/src"
        }
    },
    
 instanciando do serviço moip
 
 if(env("MOIP")=="production"){
     $this->moip = new Moip(new BasicAuth($token, $key),Moip::ENDPOINT_PRODUCTION);
 }else{
     $this->moip = new Moip(new BasicAuth($token, $key),Moip::ENDPOINT_SANDBOX);
 }
 
 
 configurar  .env
 
 MOIP=dev || production
