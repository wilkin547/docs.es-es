---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 0728e22205d4ac2c7674f7690e142aed51d42440
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399539"
---
# <a name="soapprocessing"></a>\<> soapProcessing

Define el comportamiento del punto de conexión de cliente usado para serializar entre distintos tipos de enlaces y versiones de mensajes.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> soapProcessing**
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
  
En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|                   | DESCRIPCIÓN |
| ----------------- | ----------- |
| `processMessages` | Valor booleano que especifica si se deberían calcular las referencias a los mensajes entre las versiones del mensaje SOAP. |

### <a name="child-elements"></a>Elementos secundarios

None

### <a name="parent-elements"></a>Elementos primarios

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<comportamiento >** ](behavior-of-endpointbehaviors.md) | Especifica el comportamiento de un punto de conexión. |

## <a name="remarks"></a>Comentarios

El procesamiento SOAP es el proceso donde los mensajes se convierten entre las versiones del mensaje.

El servicio de enrutamiento de Windows Communication Foundation (WCF) puede convertir mensajes de un protocolo a otro. Si las versiones del mensaje de entrada y de salida son diferentes, se crea un nuevo mensaje de la versión correcta. El procesamiento de los mensajes de una <xref:System.ServiceModel.Channels.MessageVersion> a otra se logra construyendo un nuevo mensaje WCF que contiene la parte del cuerpo y los encabezados pertinentes del mensaje WCF de entrada. Los encabezados específicos del direccionamiento, o que se interpretan en el nivel del enrutador, no se usan durante la construcción del nuevo mensaje WCF porque estos encabezados son de una versión diferente (en el caso de los encabezados de direccionamiento) o se han procesado como parte de la comunicación entre el cliente y el enrutador.

La colocación de un encabezado en el mensaje de salida está determinada por si se marcó o no como comprendido al atravesar la capa del canal de entrada. Los encabezados que no se entienden (como los encabezados personalizados) no se quitan y pasan así por el servicio del enrutamiento copiándose en el mensaje de salida. El cuerpo del mensaje se copia en el mensaje de salida. A continuación, el mensaje se envía al canal de salida en el que se señalan todos los encabezados y se crearán y agregarán otros datos del sobre específicos de dicho protocolo/transporte de comunicaciones.

Dichos pasos de procesamiento tienen lugar cuando se especifica el comportamiento del procesamiento SOAP. Este comportamiento de soapProcessingExtension > es un comportamiento de extremo que se aplica a todos los extremos de cliente (salientes) cuando se inicia el servicio de enrutamiento. [ \<](soapprocessing.md) de forma predeterminada, el comportamiento del [ \<> de enrutamiento](routing-of-servicebehavior.md) crea y adjunta un nuevo `processMessages` `true` [ \<comportamiento de soapProcessingExtension >](soapprocessing.md) con establecido en para cada punto de conexión de cliente. Si tiene un protocolo que el servicio de enrutamiento no entiende, o desea invalidar el comportamiento del procesamiento predeterminado, puede deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo o solo para extremos determinados.  Para deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo en todos los extremos `soapProcessing` , establezca el atributo [ \<](routing-of-servicebehavior.md) del comportamiento `false`del > de enrutamiento en. Para desactivar el procesamiento SOAP para un extremo determinado, use este comportamiento y establezca el atributo `processMessages` en `false`; a continuación, adjunte este comportamiento al extremo en el que no desea que se ejecute el código de procesamiento predeterminado.  Cuando el comportamiento del [ \<> de enrutamiento](routing-of-servicebehavior.md) configura el servicio de enrutamiento, omitirá la reaplicación del comportamiento del punto de conexión, ya que ya existe uno.
