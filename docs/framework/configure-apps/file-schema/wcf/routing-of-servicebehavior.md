---
description: 'Más información sobre: <routing> de <serviceBehavior>'
title: <routing> de <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 1d8a056d708b3c42aeccf3e46a0703b3fc78a17d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786894"
---
# <a name="routing-of-servicebehavior"></a>\<routing> de \<serviceBehavior>

Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|filterTable|Cadena que especifica el nombre de la tabla de enrutamiento que contiene filtros que va a evaluar el servicio del enrutamiento. Este valor debe coincidir con el `name` atributo de un [\<filterTable>](filtertable.md) elemento de la [\<filterTables>](filtertables.md) sección.|  
|routeOnHeaderOnly|Valor booleano que especifica si el filtro examinará el cuerpo del mensaje y el encabezado, o solo el encabezado. De manera predeterminada, es `true`.|  
|soapProcessingEnabled|Valor booleano que especifica si se debe producir el procesamiento SOAP.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Observaciones  

 Cuando se agrega a la configuración del comportamiento del servicio, este elemento de configuración habilita el enrutamiento para el servicio. Puede especificar la tabla de enrutamiento real que va a usar el servicio en este elemento.  
  
 Mediante esta sección de configuración, puede cambiar la configuración de enrutamiento sobre la marcha cuando cambie el patrón de implementación. En tiempo de ejecución, puede registrar su propia extensión de enrutamiento con una nueva configuración de enrutamiento y el servicio del enrutamiento empezará a usar la información de configuración actualizada para los mensajes y sesiones nuevos, mientras deja que los mensajes o las sesiones en curso usen las reglas que estaban en vigor cuando se iniciaron.  Esto le permite realizar la reconfiguración del servicio de enrutamiento con menos reciclaje y segura para la sesión durante el tiempo de ejecución.  
