---
title: Datos del marco de servicio
ms.date: 03/30/2017
ms.assetid: 2a2c8ddc-4e82-4e7f-a79f-97085c469517
ms.openlocfilehash: 8bb6e9df6a77eda5875981a0bf7783f50671a589
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255785"
---
# <a name="service-framework-data"></a>Datos del marco de servicio

En este tema se enumeran las excepciones generadas por Service Framework Data.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|AddressingExtensionInBadNS|El elemento especificado en el espacio de nombres especificado no es válido. Esto significa que el elemento especificado es un elemento duplicado o que no es una extensión legal porque los elementos de extensión no pueden estar en el espacio de nombres de direccionamiento.|  
|BinaryEncoderSessionInvalid|La sesión del codificador binario no es válida porque se produjo un error al descodificar un mensaje anterior.|  
|CannotDetectAddressingVersion|No puede detectar la versión de WS-Addressing. EndpointAddress no se inicia con un elemento.|  
|CouldNotFindNamespaceForPrefix|El prefijo especificado no tiene ningún espacio de nombres que enlace en el ámbito.|  
|EncoderBadContentType|No puede procesar a contentType.|  
|EncoderEnvelopeVersionMismatch|La versión de envoltura del mensaje entrante especificado no coincide con el codificador especificado. Asegúrese de que el enlace se configura con la misma versión que los mensajes esperados.|  
|EncoderMessageVersionMismatch|La versión del mensaje del mensaje entrante especificado no coincide con el codificador especificado. Asegúrese de que el enlace se configura con la misma versión que el mensaje.|  
|ExtraContentIsPresentInFaultDetail|El contenido del lenguaje de marcado extensible adicional se encuentra en el elemento de detalle del error. Solo se permite un elemento.|  
|FilterBadTableType|La IMessageFilterTable creada para un filtro no puede ser MessageFilterTable o derivar de MessageFilterTable.|  
|FilterTableInvalidForLookup|El estado de MessageFilterTable está dañado. No se puede realizar la búsqueda solicitada.|  
|MandatoryHeaderNotUnderstood|No se entendieron uno o más bloques requeridos de encabezado de protocolo de acceso de objeto simple.|  
|MessageBodyIsStream|El cuerpo del mensaje es una secuencia.|  
|MessageBodyIsUnknown|El formato del cuerpo del mensaje es desconocido.|  
|MessageBodyReaderInvalidReadState|No se puede utilizar el ReadState especificado del lector del cuerpo del mensaje.|  
|MessageTextEncodingNotSupported|No se admite la codificación de texto especificada que se utiliza en el formato del mensaje de texto.|  
|MissingMessageID|Al mensaje de solicitud le falta un encabezado MessageID. Se requiere que un MessageID guarde correlación con una respuesta.|  
|MultipleMessageHeaders|Se encontró más de un encabezado con el espacio de nombres y nombre especificado.|  
|MultipleMessageHeadersWithActor|Se encontró más de un encabezado con la función, espacio de nombres y nombre especificado.|  
|MultipleRelatesToHeaders|Se encontró más de un encabezado RelatesTo con la relación especificada. Solo se permite uno por relación.|  
|QueryFunctionTypeNotSupported|No se admite el tipo de valor devuelto especificado para la IXsltContextFunction.|  
|QueryIteratorOutOfScope|Se ha invalidado XPathNodeIterator. Los XPathNodeIterators que se pasan como argumentos a IXsltContextFunctions solo son válidos dentro de la función. No se pueden almacenar en memoria caché para su uso posterior ni la función puede devolverlos.|  
|QueryVariableNull|Los métodos IXsltContextVariable no pueden devolver null.|  
|QueryVariableTypeNotSupported|El tipo derivado IXsltContextVariable especificado no se admite.|  
|ReceiveShutdownReturnedMessage|El canal recibió un mensaje de entrada inesperado con la Acción especificada mientras se cerraba. Cierre el canal si no está esperando más mensajes de entrada.|  
|XmlBufferInInvalidState|Se ha producido un error interno. No se puede realizar la operación debido al estado del búfer de XML.|  
|XmlBufferQuotaExceeded|El tamaño necesario para almacenar en búfer el contenido del lenguaje de marcado extensible superó la cuota del búfer.|
