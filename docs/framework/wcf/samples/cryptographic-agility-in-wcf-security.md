---
title: Agilidad criptográfica en la seguridad de WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
ms.openlocfilehash: df40a87e2fe58b93a963d53fc79f88bbc7bdb805
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171626"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Agilidad criptográfica en la seguridad de WCF
En este ejemplo se muestra cómo especificar un algoritmo estándar o personalizado para proporcionar una implementación criptográfica agile en un cliente de Windows Communication Foundation (WCF) y el servicio. El ejemplo consta de los proyectos siguientes:  
  
 web de Office  
 Se trata de un servicio WCF autohospedado que implementa el `ICalculator` interfaz y protege el punto de conexión mediante el <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con la sesión segura y sesión confiable deshabilitadas. El servicio define una clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para la seguridad de los mensajes.  
  
 Cliente  
 Se trata de un WCFclient que accede al servicio tras una autenticación correcta. Invoca las operaciones expuestas por la interfaz `ICalculator` e implementadas por el servicio. El cliente también define la misma clase `SecurityAlgorithmSuite` personalizada para especificar los algoritmos criptográficos que se van a utilizar para el modo de seguridad.  
  
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
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a>Vea también  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)
