# Libreria Soap para FActuracion electronica Colombia [![NPM version]

> Un cliente y servidor SOAP para node.js.

Este módulo le permite conectarse a servicios web utilizando SOAP. También proporciona un servidor que le permite ejecutar sus propios servicios SOAP.


- Se implementa con la ayuda de la libreria SOAP  de vpulim  https://github.com/vpulim .
``` javascript
var fecolombia = require('fecolombia');
var url = 'https://www.dian.gov.co/Service.svc?wsdl';
var args = {
   "tem:EstadoDocumento": {
      "tem:tokenEmpresa": "CCCCXXXBBB",
      "tem:tokenPassword": "99W55W5W5WD825EE2",
      "tem:documento": "FACT01"
   }
};
fecolombia.createClient(url, function (err, client) {
   client.EstadoDocumento(args, function (err, result) {
     console.log(result.EstadoDocumentoResult.cufe);
   });

});


RESPUESTA : 

{ EstadoDocumentoResult:
   { acuseEstatus: '0',
     acuseRespuesta: '0',
     codigo: '200',
     cufe: 'WWRSSSSSRR',
     estatusDocumento: '200',
     fechaDocumento: '2018-11-12 10:12:00',
     mensaje: 'Se retornan datos de la Factura.',
     mensajeDocumento: 'El documento se envió correctamente.',
     resultado: 'Procesado' 
    }
}
