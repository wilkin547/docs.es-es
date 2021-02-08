---
description: 'Más información acerca de: lista de actividades'
title: Lista de actividades
ms.date: 03/30/2017
ms.assetid: 5540e185-ce8e-4db3-83b0-2b9f5bf71829
ms.openlocfilehash: 656c605e81872405aa8637b647b40278b06913cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770877"
---
# <a name="activity-list"></a>Lista de actividades

En este tema se enumeran todas las actividades definidas por Windows Communication Foundation (WCF).  
  
> [!NOTE]
> También puede definir las actividades mediante programación para agrupar los seguimientos del usuario. Para obtener más información, consulte [emitir seguimientos de User-Code](emitting-user-code-traces.md).  
  
## <a name="servicemodel-activities"></a>Actividades ServiceModel  

 La siguiente tabla muestra una lista de todas las actividades para los escenarios de uso principales.  
  
|Etiqueta|Nombre de actividad|Tipo de actividad|Descripción|  
|-----------|-------------------|-------------------|-----------------|  
|A, M|Actividad de ambiente|N/A (ServiceModel no lo controla)|La actividad cuyo id. se establece en TLS antes de que se realice ninguna llamada al código de ServiceModel (del lado de cliente o servidor).<br /><br /> Ejemplo: una actividad en la que se llama a Open en el cliente WCF o se llama a serviceHost. Open.|  
|B|Construcción<br /><br /> ChannelFactory. ContractType : ‘[Type]’.|Construcción||  
|C|Abrir<br /><br /> [ClientBase&#124;ChannelFactory]. ContractType : ‘[Type]’.|Abrir||  
|I|Cierre [ClientBase&#124;ChannelFactory]. ContractType : ‘[Type]’.|Cerrar||  
|M|Construir ServiceHost. ServiceType: ‘[Type]’.|Construcción||  
|No|Abrir ServiceHost. ServiceType: ‘[Type]’.|Abrir||  
|Z|Cerrar ServiceHost. ServiceType: ‘[Type]’.|Cerrar||  
|O|Escuchar en ‘[address]’.|ListenAt|Esta actividad y la siguiente son específicas del transporte. La actividad ListenAt representa el contenido que asigna a la dirección donde el agente de escucha realiza escuchas. En el caso de MSMQ, es la propia cola puesto que la cola asigna a una dirección. Esta actividad realiza escuchas para las conexiones entrantes en el caso de transportes orientados a conexiones, para los mensajes de MSMQ en el caso de MSMQ. Esta actividad se crea durante ServiceHost.Open () y contiene las trazas relacionadas con la creación y disposición del agente de escucha, así como la transferencia de salida a todas las actividades ReceiveBytes.|  
|P|Recibir los bytes en la conexión ‘[address]’. Recibir mensaje MSMQ.|ReceiveBytes|En esta actividad, se procesan los datos que finalmente recibirán un mensaje de WCF. Los bytes de entrada se esperan en el caso de http o transporte orientado a conexiones. Para TCP/canalización con nombre, la duración de esta actividad es igual a la vida la conexión, puesto que se crea al mismo tiempo que la conexión. Para http, es de la duración de una solicitud de mensaje y se crea cuando se envía el mensaje. Esta actividad contiene las trazas relacionadas con la creación y disposición de la conexión si fuese pertinente, así como las transferencias hacia fuera a todas las actividades de procesamiento de mensajes (objetos).<br /><br /> En el caso de MSMQ, es la actividad donde se recupera el mensaje MSMQ.|  
|Q|Procese el mensaje [number]. (Tenga en cuenta que [number] es un valor que aumenta de manera monótona que comienza en 1.)|ProcessMessage|Procese un mensaje entrante. Esta actividad se inicia cuando se reciben todos los datos (bytes, mensajes de MSMQ) para formar un objeto de mensaje de WCF. Los seguimientos dentro de esta actividad tratan con el procesamiento de encabezados.<br /><br /> Una vez formado un mensaje que se puede enviar, se cambia a la actividad ServiceHost ProcessAction después de buscar el identificador de actividad correspondiente.|  
|D, S|Procese la acción ‘[action]’.|ProcessAction|Procese el mensaje a través de la pila Transporte/Seguridad/RM para enviar el mensaje al código de usuario en la recepción y en el orden inverso en el envío.<br /><br /> En el servidor, esta actividad utiliza el ID. de actividad propagado si se envía en el encabezado del mensaje a través de la "propagación de actividad". de lo contrario, se crea un nuevo GUID.<br /><br /> El mensaje de respuesta para contratos de solicitud/respuesta también se procesa en esa actividad.|  
|T|Ejecute ‘[IContract.Operation]’.|ExecuteUserCode|Ejecute el código de usuario tras el envío en el lado de servicio. Esta actividad proporciona un límite para delinear el código de ServiceHost del código proporcionado por el usuario.|  
  
## <a name="security-activities"></a>Actividades de seguridad  

 La tabla siguiente muestra todas las actividades relacionadas con la seguridad.  
  
|Nombre de actividad|Tipo de actividad|Descripción|  
|-------------------|-------------------|-----------------|  
|Configure la sesión segura|SetupSecurity|Existe solo en el lado de cliente. Contiene todos los intercambios de RST*/SCT para la autenticación y configuración del contexto de seguridad. Si `propagateActivity` = `true` es, esta actividad se combina con las actividades RST/SCT de la acción de proceso correspondiente del servicio \* .|  
|Cerrar sesión segura|SetupSecurity|Existe en el lado de cliente. Contiene el intercambio de mensajes de cancelación para cerrar la sesión segura. Si `propagateActivity` = `true` es, esta actividad se combina con la acción de proceso "Cancelar" desde el servicio.|  
  
 En la tabla siguiente se muestra una lista de todas las actividades relacionadas con COM+.  
  
|Nombre de actividad|Tipo de actividad|Descripción|  
|-------------------|-------------------|-----------------|  
|Cree una instancia COM+.|TransferToCOMPlus|1 instancia de actividad para cada llamada COM+ desde código WCF|  
|Ejecutar COM+ \<operation>|TransferToCOMPlus|1 instancia de actividad para cada llamada COM+ desde código WCF|  
  
## <a name="wmi-activities"></a>Actividades WMI  

 La tabla siguiente muestra una lista de todas las actividades relacionadas con WMI.  
  
|Nombre de actividad|Tipo de actividad|Descripción|  
|-------------------|-------------------|-----------------|  
|Obtención de WMI|WMIGetObject|El usuario está recuperando datos desde WMI.|  
|Colocación en WMI|WmiPutInstance|El usuario está actualizando los datos mediante WMI.|
