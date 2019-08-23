---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925854"
---
# <a name="dispatchersynchronization"></a>\<dispatcherSynchronization>
  
Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.  
  
\<system.serviceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a>Type  
  
`Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
  
En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos

| Atributo               | DESCRIPCIÓN       |
| ----------------------- | ----------------- |
| asynchronousSendEnabled | Booleano que especifica si el comportamiento de envío asincrónico está habilitado. |
| `maxPendingReceives`    | Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.<br /><br /> Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | DESCRIPCIÓN |  
| ------- | ----------- |  
| [\<comportamiento >](behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un punto de conexión. |

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
