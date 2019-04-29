---
title: Servicio de enrutador de detección
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 166f6b9d1055e36f987e6b9a81fe69dc8bd548b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773040"
---
# <a name="discovery-router-service"></a>Servicio de enrutador de detección
En este ejemplo se muestra cómo reenviar los mensajes de detección a otro punto de conexión.  
  
## <a name="demonstrates"></a>Demostraciones  
 Enrutamiento de la detección  
  
## <a name="discussion"></a>Discusión  
 El enrutamiento de la detección es útil en un escenario en el que un cliente busca un servicio mediante un proxy y el proxy no conoce dicho servicio, pero conoce otro proxy. Este proxy puede reenviar el paquete de detección desde este cliente al segundo proxy. El segundo proxy puede buscar el servicio y devolver las respuestas al cliente original.  
  
 En este ejemplo, un cliente envía un mensaje a un componente de enrutamiento de la detección. Este mensaje se envía a un extremo concreto en el enrutador de detección. A continuación, el enrutador reenvía el mensaje a un extremo de multidifusión UDP. El mensaje de sondeo sale al extremo de multidifusión y un servicio que realiza escuchas en una dirección de multidifusión UDP responde a ese enrutador de detección. El enrutador de detección recopila las respuestas y las envía de nuevo al cliente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Compilar el ejemplo.  
  
2. Ejecute la aplicación ejecutable DiscoveryRouter.  
  
3. Ejecute el ejecutable de servicio desde el directorio de compilación.  
  
4. Ejecute la aplicación cliente. Observe que el cliente busca el servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
