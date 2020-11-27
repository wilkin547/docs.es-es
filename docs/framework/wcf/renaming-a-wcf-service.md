---
title: Cambiar el nombre de un servicio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 25f9201253f02f368ccf95ddf1f7a7d78d2e1b2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249727"
---
# <a name="renaming-a-wcf-service"></a>Cambiar el nombre de un servicio WCF

En este tema se describe cómo se puede cambiar el nombre de un servicio de Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Cambiar el nombre de un servicio WCF  

 Realice los pasos siguientes para cambiar el nombre de un servicio en una plantilla Windows Communication Foundation (WCF).  
  
- Cambie el nombre de la clase que implementa el servicio.  
  
- En el archivo de configuración del servicio, cambie el nombre del servicio al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo. El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Si el servicio es webhosted, usa un archivo *\* . SVC* . Abra el archivo svc y modifique el nombre de su servicio tal y como se indica en el siguiente ejemplo. Este paso no es necesario para aplicaciones autohospedadas, puesto que no hay ningún archivo svc.  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Cambio del nombre de un contrato de servicios de WCF  
  
- Realice los siguientes pasos para cambiar el nombre del contrato de servicios:  
  
- Cambie el nombre del contrato de servicios.  
  
- En el archivo de configuración del servicio, cambie el nombre del contrato de servicios al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo. El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
