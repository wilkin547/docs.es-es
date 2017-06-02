---
title: "Agilidad criptogr&#225;fica en la seguridad de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# Agilidad criptogr&#225;fica en la seguridad de WCF
Este ejemplo muestra cómo especificar un algoritmo estándar o personalizado para proporcionar una implementación criptográfica y ágil en un cliente y un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  El ejemplo consta de los proyectos siguientes:  
  
 Servicio  
 Es un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autohospedado que implementa la interfaz `ICalculator` y protege el extremo utilizando <xref:System.ServiceModel.WsHttpBinding> con la sesión segura y la sesión confiable deshabilitadas.  El servicio define una clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para la seguridad de los mensajes.  
  
 Cliente  
 Este es un cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que tiene acceso al servicio una vez que la autenticación es correcta.  Invoca las operaciones expuestas por la interfaz `ICalculator` e implementadas por el servicio.  El cliente también define la misma clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para el modo de seguridad.  
  
### Para utilizar este ejemplo  
  
1.  Abra la solución CryptoAgility.sln en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
3.  Abra [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]el Explorador de Windows, navegue al directorio \\WCF\\Basic\\Security\\CryptoAgility\\Service\\bin y ejecute el archivo service.exe con privilegios de administrador haciendo clic con el botón secundario en service.exe y seleccionando **Ejecutar como administrador**.  
  
4.  Navegue hasta el directorio \\WCF\\Basic\\Security\\CryptoAgility\\Client\\bin y ejecute el archivo client.exe normalmente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## Vea también  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)