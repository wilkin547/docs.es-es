---
title: Servicio de enrutador de detección
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 149dd69cdd1972465f4b7cb48ab657492d3f21d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183728"
---
# <a name="discovery-router-service"></a>Servicio de enrutador de detección
En este ejemplo se muestra cómo reenviar los mensajes de detección a otro punto de conexión.  
  
## <a name="demonstrates"></a>Muestra  
 Enrutamiento de la detección  
  
## <a name="discussion"></a>Discusión  
 El enrutamiento de la detección es útil en un escenario en el que un cliente busca un servicio mediante un proxy y el proxy no conoce dicho servicio, pero conoce otro proxy. Este proxy puede reenviar el paquete de detección desde este cliente al segundo proxy. El segundo proxy puede buscar el servicio y devolver las respuestas al cliente original.  
  
 En este ejemplo, un cliente envía un mensaje a un componente de enrutamiento de la detección. Este mensaje se envía a un extremo concreto en el enrutador de detección. A continuación, el enrutador reenvía el mensaje a un extremo de multidifusión UDP. El mensaje de sondeo sale al extremo de multidifusión y un servicio que realiza escuchas en una dirección de multidifusión UDP responde a ese enrutador de detección. El enrutador de detección recopila las respuestas y las envía de nuevo al cliente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Compile el ejemplo.  
  
2. Ejecute la aplicación ejecutable DiscoveryRouter.  
  
3. Ejecute el ejecutable de servicio desde el directorio de compilación.  
  
4. Ejecute la aplicación cliente. Observe que el cliente busca el servicio.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
