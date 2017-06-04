---
title: "Ejemplo de detecci&#243;n de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Ejemplo de detecci&#243;n de flujo de trabajo
En este ejemplo se muestra cómo hacer que un servicio de flujo de trabajo se pueda detectar y cómo crear una actividad de código personalizada que busque un servicio determinado.  
  
## Demostraciones  
 Actividad de búsqueda de detección y uso del flujo de trabajo  
  
## Análisis  
 En la primera parte del ejemplo, se hace que un servicio de flujo de trabajo se pueda detectar mediante la configuración.La configuración también se puede utilizar para aplicar el servicio de forma apropiada con los metadatos personalizados \(como los ámbitos\).En el cliente, el ejemplo utiliza una actividad de código personalizada, que utiliza Detección para buscar un servicio que coincide con un contrato determinado.La actividad de código genera un URI, que se utiliza después en una actividad de envío.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Este ejemplo utiliza los extremos HTTP, que debe tener las ACL de dirección URL apropiadas, para ejecutarse \(vea [Configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener detalles\).Al ejecutar el siguiente comando en un símbolo del sistema con permisos elevados, se deberían agregar las ACL adecuadas.Sustituya su dominio y nombre de usuario para los siguientes argumentos si su shell no entiende el formato de variable.  
  
     **netsh http add urlacl url\=http:\/\/\+:8000\/ user\=%DOMAIN%\\%UserName%**  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`