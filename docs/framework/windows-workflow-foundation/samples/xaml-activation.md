---
title: Activación XAML
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-activation"></a>Activación XAML
En este ejemplo se muestra cómo hospedar un flujo de trabajo declarativo en IIS. El ejemplo es un flujo de trabajo básico llamado `EchoService` que incluye una operación.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a (página de descarga) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución XAMLActivation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando **F5**.  
  
3.  Ejecute WcfTestClient.exe. En un símbolo del sistema, escriba el comando siguiente:  
  
    1.  cd %SystemDrive%\Archivos de programa\Microsoft Visual Studio 10.0\Common7\IDE  
  
    2.  Ejecute WcfTestClient.exe.  
  
4.  Establece la dirección del servicio en WcfTestClient.exe presionando CTRL + MAYÚS + A y si se establece la dirección del servicio en http://localhost:56133/Service.xamlx.  
  
5.  Realice la operación de eco para probar el servicio.  
  
6.  Implemente el servicio en IIS usando DeployToIIS.Bat en un símbolo del sistema con privilegios de administrador.  
  
7.  Actualizar la dirección del servicio en el cliente para http://localhost/XAMLActivation/Service.xamlx y pruebe el servicio nuevo mediante WcfTestClient.exe.
