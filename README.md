Deve-se criar em node red uma fuction com a base64 e inserir com base nela tag HTML e script JS

HTML(para cada imagem):

                    <img :src="'data:image/png;base64,' + msg.payload.pepsico_logo" alt="Logo" />  
       
JS(Para cada imagem):

   (function(scope) {
        scope.$watch('msg.payload.pepsico_logo', function(newVal) {
            if (newVal) {
                document.getElementById('pepsicoLogo').src = "data:image/png;base64," + newVal;
            }
        });
    })(scope);

Formato de conversão da imagem em base64 para imagens em tags HTML:

msg.payload= {pepsico_logo: '(INSERIR BASE 64 AQUI DENTRO'}
 
return msg;

