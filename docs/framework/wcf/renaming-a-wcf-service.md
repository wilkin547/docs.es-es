---
title: Cambiar el nombre de un servicio WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2ab3d780f85131fc7adf24c5f420bd5fe643d9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="renaming-a-wcf-service"></a>Cambiar el nombre de un servicio WCF
En este tema se describe cómo cambiar el nombre de un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="renaming-a-wcf-service"></a>Cambiar el nombre de un servicio WCF  
 Realice los pasos siguientes para cambiar el nombre de un servicio en una plantilla de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
-   Cambie el nombre de la clase que implementa el servicio.  
  
-   En el archivo de configuración del servicio, cambie el nombre del servicio al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo. El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   Si su servicio es hospedado mediante web, utiliza un * archivo .svc. Abra el archivo svc y modifique el nombre de su servicio tal y como se indica en el siguiente ejemplo. Este paso no es necesario para aplicaciones autohospedadas, puesto que no hay ningún archivo svc.  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Cambio del nombre de un contrato de servicios de WCF  
  
-   Realice los siguientes pasos para cambiar el nombre del contrato de servicios:  
  
-   Cambie el nombre del contrato de servicios.  
  
-   En el archivo de configuración del servicio, cambie el nombre del contrato de servicios al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo. El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
