---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 34c12a05ee363df6b6cfc9ff3809bab50ee8d522
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747582"
---
# <a name="ltdispatchersynchronizationgt"></a>&lt;dispatcherSynchronization&gt;

Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.

\<system.serviceModel > \<comportamientos > \<endpointBehaviors > \<comportamiento >

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
| [\<comportamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un punto de conexión. |

## <a name="see-also"></a>Vea también

 <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
