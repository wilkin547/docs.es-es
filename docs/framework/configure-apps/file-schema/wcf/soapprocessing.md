---
title: '&lt;soapProcessing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e53225399e3acba275d2d95533c4baad20386a4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltsoapprocessinggt"></a>&lt;soapProcessing&gt;

Define el comportamiento del punto de conexión de cliente usado para serializar entre distintos tipos de enlaces y versiones de mensajes.

**\<sistema. ServiceModel >**   
&nbsp;&nbsp;**\<comportamientos >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comportamiento >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing >**

## <a name="syntax"></a>Sintaxis

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|                   | Descripción |
| ----------------- | ----------- |
| `processMessages` | Valor booleano que especifica si se deberían calcular las referencias a los mensajes entre las versiones del mensaje SOAP. |

### <a name="child-elements"></a>Elementos secundarios

Ninguna

### <a name="parent-elements"></a>Elementos primarios

|     | Descripción |
| --- | ----------- |
| [**\<comportamiento >**](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | Especifica el comportamiento de un punto de conexión. |

## <a name="remarks"></a>Comentarios

El procesamiento SOAP es el proceso donde los mensajes se convierten entre las versiones del mensaje.

El servicio de enrutamiento [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] puede convertir los mensajes de un protocolo en otro. Si las versiones del mensaje de entrada y de salida son diferentes, se crea un nuevo mensaje de la versión correcta. Procesamiento de mensajes de una <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion` a otra se logra construyendo un nuevo [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] mensaje que contiene la parte del cuerpo y los encabezados pertinentes de la entrada [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] mensaje. Los encabezados específicos del direccionamiento, o que se interpretan en el nivel del enrutador, no se usan durante la construcción del nuevo mensaje WCF porque estos encabezados son de una versión diferente (en el caso de los encabezados de direccionamiento) o se han procesado como parte de la comunicación entre el cliente y el enrutador.

La colocación de un encabezado en el mensaje de salida está determinada por si se marcó o no como comprendido al atravesar la capa del canal de entrada. Los encabezados que no se entienden (como los encabezados personalizados) no se quitan y pasan así por el servicio del enrutamiento copiándose en el mensaje de salida. El cuerpo del mensaje se copia en el mensaje de salida. A continuación, el mensaje se envía al canal de salida en el que se señalan todos los encabezados y se crearán y agregarán otros datos del sobre específicos de dicho protocolo/transporte de comunicaciones.

Dichos pasos de procesamiento tienen lugar cuando se especifica el comportamiento del procesamiento SOAP. Esto [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) comportamiento es un comportamiento del punto de conexión que se aplica a todos los extremos de cliente (saliente) cuando se inicia el servicio de enrutamiento. de manera predeterminada, el [ \<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportamiento crea y asocia una nueva [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) comportamiento con `processMessages` establecido en `true` para cada uno punto de conexión de cliente. Si tiene un protocolo que el servicio de enrutamiento no entiende, o desea invalidar el comportamiento del procesamiento predeterminado, puede deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo o solo para puntos de conexión determinados.  Para deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo en todos los puntos de conexión, establezca el `soapProcessing` atributo de la [ \<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportamiento `false`. Para desactivar el procesamiento SOAP para un extremo determinado, use este comportamiento y establezca el atributo `processMessages` en `false`; a continuación, adjunte este comportamiento al extremo en el que no desea que se ejecute el código de procesamiento predeterminado.  Cuando el [ \<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportamiento configura el servicio de enrutamiento, se omitirán volver a aplicar el comportamiento de punto de conexión porque ya existe uno.
