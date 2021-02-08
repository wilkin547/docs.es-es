---
description: Más información acerca de cómo cambiar el nombre de un servicio WCF
title: Cambiar el nombre de un servicio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8d75e43f4bda97e8ee6de34b039eb1236d6c4a6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779171"
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
