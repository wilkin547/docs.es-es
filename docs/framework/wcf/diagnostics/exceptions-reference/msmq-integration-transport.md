---
description: 'Más información sobre: el transporte de integración de MSMQ'
title: Transporte de integración de MSMQ
ms.date: 03/30/2017
ms.assetid: 2bf9893a-fbd1-41fc-b6de-a41a44279936
ms.openlocfilehash: a9d47a3a15778bdeb52d2a9ab38610803448de4f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686406"
---
# <a name="msmq-integration-transport"></a>Transporte de integración de MSMQ

En este tema se hace una lista de todas las excepciones generadas por el transporte de integración de MSMQ.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|MessageSizeMustBeInIntegerRange|Este generador almacena en búfer los mensajes, por lo que los tamaños de los mensajes deben estar en el rango de un valor entero.|  
|MsmqByteArrayBodyExpected|Se produjo una desigualdad entre el formato de serialización especificado y el cuerpo del mensaje de MSMQ. El mensaje no puede enviarse o recibirse. El formato de serialización ByteArray requiere que el cuerpo del mensaje de MSMQ sea de tipo byte[].|  
|MsmqCannotDeserializeActiveXMessage|Se ha producido un error de serialización de ActiveX. El mensaje no puede enviarse o recibirse. El tipo de variante especificado para el cuerpo no coincide con el cuerpo del mensaje de MSMQ real.|  
|MsmqCannotUseBodyTypeWithActiveXSerialization|Las propiedades del mensaje no coinciden. El mensaje no puede enviarse o recibirse. No se puede especificar la propiedad de mensaje BodyType si se utiliza el formato de serialización de ActiveX.|  
|MsmqInvalidServiceOperationForMsmqIntegrationBinding|Error en la validación de MsmqIntegrationBinding. No se puede iniciar el extremo de servicio. El enlace especificado no admite la firma del método para la operación de servicio especificada en el contrato especificado. Corrija la operación del servicio para utilizar MsmqIntegrationBinding.|  
|MsmqInvalidTypeDeserialization|Se produjo un error en la serialización de ActiveX porque no se puede reconocer el formato de serialización. El mensaje no puede enviarse o recibirse.|  
|MsmqInvalidTypeSerialization|No se reconoce el tipo de variante. Error en la serialización de ActiveX. El mensaje no puede enviarse o recibirse. No se admite el tipo de variante especificado.|  
|MsmqStreamBodyExpected|El formato de serialización y el contenido del cuerpo no coinciden. El mensaje no se puede enviar ni recibir. Solo un cuerpo de tipo secuencia se puede enviar o recibir utilizando el modo de serialización de secuencias.|
