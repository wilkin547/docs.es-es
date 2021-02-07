---
description: 'Más información acerca de: transporte de MSMQ'
title: Transporte MSMQ
ms.date: 03/30/2017
ms.assetid: 3f29a2fe-24df-4614-b64c-b0c084fb7003
ms.openlocfilehash: af371a6481e7137321f1c32d0183f68e529d13d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686354"
---
# <a name="msmq-transport"></a>Transporte MSMQ

En este tema se hace una lista de todas las excepciones generadas por el transporte MSMQ.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|MsmqActiveDirectoryRequiresNativeTransfer|Error de la validación del enlace para el mensaje. El cliente no puede enviar mensajes. Un conflicto en las propiedades del enlace produjo este error. UseActiveDirectory está establecido en true y QueueTransferProtocol se establece en Native. Para resolver el conflicto, corrija una de las propiedades.|  
|MsmqAuthNoneRequiresProtectionNone|Error en la validación del enlace para el servicio. No se puede iniciar el punto de conexión de servicio o el cliente. Un conflicto en las propiedades del enlace produjo este error. MsmqAuthenticationMode se establece en None y MsmqProtectionLevel no se establece en None. Para resolver el conflicto, corrija una de las propiedades.|  
|MsmqCustomRequiresPerAddDLQ|Error de la validación del enlace para el mensaje. El cliente no puede enviar los mensajes. DeadLetterQueue está establecido en Custom, pero no se especifica CustomDeadLetterQueue. Especifique el URI de la cola de mensajes no enviados de cada aplicación en la propiedad CustomDeadLetterQueue.|  
|MsmqDeserializationError|Se encontró un error al deserializar el mensaje XML. El mensaje no se puede recibir y se quita.|  
|MsmqDLQNotWriteable|Error en la validación del enlace para el cliente. El cliente no puede enviar un mensaje. La cola de mensajes no enviados especificada no existe o no se puede escribir en ella. Asegúrese de que la cola existe con la autorización apropiada para escribir en ella.|  
|MsmqGetPrivateComputerInformationError|Error en la comprobación de la versión con el error especificado. No se puede detectar la versión de MSMQ. Se producirá un error en todas las operaciones que estén en el canal en cola. Asegúrese de que MSMQ está instalado y disponible.|  
|MsmqNoAssurancesForVolatile|Error en la validación del enlace para el servicio. No se puede iniciar el punto de conexión de servicio o el cliente. La propiedad ExactlyOnce está establecida en true y la propiedad Durable está establecida en false. Esto no se admite. Para resolver el conflicto, corrija una de estas propiedades.|  
|MsmqNonTransactionalQueueNeeded|Se detectó una desigualdad entre el enlace y la configuración de cola de MSMQ. No se puede iniciar el extremo de servicio. La propiedad ExactlyOnce está establecida en false y la cola de la que leer los mensajes es una cola transaccional. Corrija el error estableciendo la propiedad ExactlyOnce en true o cree un enlace no transaccional.|  
|MsmqOpenError|Se produjo un error al abrir la cola especificada. El mensaje no se puede enviar o recibir desde la cola. Asegúrese de que MSMQ está instalado y ejecutándose. También asegúrese de que la cola está disponible para abrir con la autorización y el modo de acceso necesario.|  
|MsmqPathLookupError|Se produjo un error al convertir el nombre de ruta de la cola especificado en el nombre de formato. Error en todas las operaciones del canal en cola. Asegúrese de que la dirección de la cola es válida. MSMQ debe estar instalado con la integración de Active Directory habilitada y se ha de poder obtener acceso a él.|  
|MsmqPerAppDLQRequiresCustom|Error en la validación del enlace en el cliente. El cliente no puede enviar mensajes. La propiedad CustomDeadLetterQueue se establece, pero la propiedad DeadLetterQueue no se establece en Custom. Establezca la propiedad DeadLetterQueue en Custom.|  
|MsmqPerAppDLQRequiresExactlyOnce|Error en la validación del enlace para el cliente. El cliente no puede enviar mensajes. Un conflicto en las propiedades del enlace está causando este error. Para utilizar la cola de mensajes no enviados personalizada, ExactlyOnce debe establecerse en true para resolver el conflicto.|  
|MsmqPerAppDLQRequiresMsmq4|Se detectó una desigualdad entre el enlace y la configuración de MSMQ. El cliente no puede enviar mensajes. Para utilizar la cola de mensajes no enviados personalizada, debe tener la versión 4.0 o posterior de MSMQ. Si no tiene la versión 4.0 de MSMQ o posterior, establezca la propiedad DeadLetterQueue en System o None.|  
|MsmqReceiveError|Se produjo un error mientras se recibía un mensaje de la cola. Asegúrese de que MSMQ está instalado y ejecutándose. Asegúrese de que la cola puede recibir.|  
|MsmqSameTransactionExpected|Se produjo un error de transacción para esta sesión. Error en el canal de la sesión. No se pueden enviar ni recibir mensajes en la sesión. Una sesión en cola no puede asociarse a más de una transacción. Asegúrese de que todos los mensajes en la sesión se envían o se reciben utilizando una única transacción.|  
|MsmqSendError|Se produjo un error al enviar a la cola especificada. Asegúrese de que MSMQ está instalado y ejecutándose. Si está enviando a una cola local, asegúrese de que la cola existe con el modo de acceso y autorización requeridos.|  
|MsmqTimeSpanTooLarge|El período de vida del mensaje es demasiado grande. No se puede enviar el mensaje. El mensaje Time To Live (TTL) no puede superar el valor máximo de Int32.|  
|MsmqTokenProviderNeededForCertificates|No se puede encontrar un X509SecurityTokenProvider. No se puede enviar el mensaje. El modo de autenticación del certificado requiere un proveedor de tokens de X.509. Asegúrese de que un proveedor de tokens de seguridad está disponible para el certificado instalado.|  
|MsmqTransactedDLQExpected|Se produjo una desigualdad entre el enlace y la configuración de MSMQ. No se pueden enviar mensajes. La cola de mensajes no enviados personalizada especificada en el enlace debe ser una cola de transacción. Asegúrese de que la dirección de la cola de mensajes no enviados personalizada es correcta y de que la cola es transaccional.|  
|MsmqTransactionalQueueNeeded|Se produjo una desigualdad entre el enlace y la configuración de cola de MSMQ. No se puede iniciar el extremo de servicio. La propiedad ExactlyOnce se establece en true y la cola de la que leer los mensajes no es una cola transaccional. Para corregir el error, establezca la propiedad ExactlyOnce en false o cree una cola transaccional para este enlace.|  
|MsmqTransactionCurrentRequired|Ninguna transacción está disponible para enviar mensajes en la sesión. Enviar un mensaje en una sesión en cola requiere una transacción. Asegúrese de que un ámbito de la transacción se especifica para enviar el mensaje en la sesión.|  
|MsmqTransactionRequired|Se requiere una transacción pero no está disponible. No se puede enviar ni recibir mensajes. Asegúrese de que el ámbito de la transacción se especifica para enviar o recibir mensajes.|  
|MsmqUnsupportedSerializationFormat|Se produjo un error de deserialización. El mensaje no se puede recibir y se quita. No se admite el formato de serialización especificado.|  
|MsmqWrongPrivateQueueSyntax|La dirección URL no es válida. La dirección URL para la cola no puede contener el carácter '$'. Utilice la sintaxis en net.msmq://machine/private/queueName para direccionar una cola privada.|
