---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 537dee408f1af29a06042de439a2c1e7d7874222
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555393"
---
# <a name="ltdispatchersynchronizationgt"></a>&lt;dispatcherSynchronization&gt;
  
Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.  
  
\<system.serviceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a>Tipo  
  
`Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
  
En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos

| Atributo               | Descripción       |
| ----------------------- | ----------------- |
| asynchronousSendEnabled | Booleano que especifica si el comportamiento de envío asincrónico está habilitado. |
| `maxPendingReceives`    | Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.<br /><br /> Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |  
| ------- | ----------- |  
| [\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un punto de conexión. |

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
