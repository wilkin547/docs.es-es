---
title: "Servicio de enrutador de detecci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Servicio de enrutador de detecci&#243;n
En este ejemplo se muestra cómo reenviar los mensajes de detección a otro extremo.  
  
## Demostraciones  
 Enrutamiento de la detección  
  
## Análisis  
 El enrutamiento de la detección es útil en un escenario en el que un cliente busca un servicio mediante un proxy y el proxy no conoce dicho servicio, pero conoce otro proxy.Este proxy puede reenviar el paquete de detección desde este cliente al segundo proxy.El segundo proxy puede buscar el servicio y devolver las respuestas al cliente original.  
  
 En este ejemplo, un cliente envía un mensaje a un componente de enrutamiento de la detección.Este mensaje se envía a un extremo concreto en el enrutador de detección.A continuación, el enrutador reenvía el mensaje a un extremo de multidifusión UDP.El mensaje de sondeo sale al extremo de multidifusión y un servicio que realiza escuchas en una dirección de multidifusión UDP responde a ese enrutador de detección.El enrutador de detección recopila las respuestas y las envía de nuevo al cliente.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Compile el ejemplo.  
  
2.  Ejecute la aplicación ejecutable DiscoveryRouter.  
  
3.  Ejecute el ejecutable de servicio desde el directorio de compilación.  
  
4.  Ejecute la aplicación cliente.Observe que el cliente busca el servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`