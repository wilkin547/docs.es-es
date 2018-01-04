---
title: "Agilidad criptográfica en la seguridad de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7d99ada67255d0ced8bbabc2ab6fc645e6ba9e35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cryptographic-agility-in-wcf-security"></a>Agilidad criptográfica en la seguridad de WCF
Este ejemplo muestra cómo especificar un algoritmo estándar o personalizado para proporcionar una implementación criptográfica y ágil en un cliente y un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. El ejemplo consta de los proyectos siguientes:  
  
 Servicio  
 Se trata de un hospedado por sí mismo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio que implementa el `ICalculator` de interfaz y protege el extremo utilizando el <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con la sesión segura y la sesión confiable deshabilitadas. El servicio define una clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para la seguridad de los mensajes.  
  
 Cliente  
 Este es un cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que tiene acceso al servicio una vez que la autenticación es correcta. Invoca las operaciones expuestas por la interfaz `ICalculator` e implementadas por el servicio. El cliente también define la misma clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para el modo de seguridad.  
  
### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra la solución CryptoAgility.sln en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Abra [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] y desplácese al directorio \WCF\Basic\Security\CryptoAgility\Service\bin y ejecute el archivo service.exe con privilegios de administrador haciendo clic en service.exe y seleccionando **ejecutar como administrador**.  
  
4.  Navegue hasta el directorio \WCF\Basic\Security\CryptoAgility\Client\bin y ejecute el archivo client.exe normalmente.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a>Vea también  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)
