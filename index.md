<!DOCTYPE html>
<html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    </head>
    <body>
    <button onclick="gettronweb()">Can you get tronweb from tronlink?</button>
    <script>
        function gettronweb(){
            if(window.tronWeb && window.tronWeb.defaultAddress.base58){
                document.write("Yes, catch it: ",window.tronWeb.defaultAddress.base58)
            }else{
				document.write("failed")
			}
        }
	</script>
	<button onclick="sendtx()">Send TX</button>
	<script>
		function sendtx(){
			document.write("fase 0")
			if (window.tronWeb && window.tronWeb.defaultAddress.base58) {
                document.write("fase 1")
				var tronweb = window.tronWeb
				document.write("fase 2")
				var fromadd = window.tronWeb.defaultAddress.base58
                document.write("fase 3")
				var tx = tronweb.transactionBuilder.sendTrx('TRQyHhdcfRzjwqNS1t4mesaqLF5rEyRT4R', 10)
                document.write("fase 4")
 				var signedTx = await tronweb.trx.sign(tx)
                document.write("fase 5")
				var broastTx = await tronweb.trx.sendRawTransaction(signedTx)
                document.write("fatto")
            } else {
			document.write("fallimento")
			}
		}
    </script>
    </body>
</html>
