---
title: "Activaci&#243;n XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Activaci&#243;n XAML
En este ejemplo se muestra cómo hospedar un flujo de trabajo declarativo en IIS.El ejemplo es un flujo de trabajo básico llamado `EchoService` que incluye una operación.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a \(página de descarga\) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución XAMLActivation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Presione **F5** para compilar la solución.  
  
3.  Ejecute WcfTestClient.exe.En un símbolo del sistema, escriba el comando siguiente:  
  
    1.  cd %SystemDrive%\\Archivos de programa\\Microsoft Visual Studio 10.0\\Common7\\IDE  
  
    2.  Ejecute WcfTestClient.exe.  
  
4.  Establezca la dirección del servicio en WcfTestClient.exe presionando CTRL\+SHIFT\+A y estableciendo la dirección de servicio en http:\/\/localhost:56133\/Service.xamlx.  
  
5.  Realice la operación de eco para probar el servicio.  
  
6.  Implemente el servicio en IIS usando DeployToIIS.Bat en un símbolo del sistema con privilegios de administrador.  
  
7.  Actualice la dirección de servicio en el cliente a http:\/\/localhost\/XAMLActivation\/Service.xamlx y pruebe el servicio de nuevo mediante WcfTestClient.exe.