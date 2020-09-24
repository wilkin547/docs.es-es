---
title: <system.serviceModel>
description: Obtenga información sobre los elementos de configuración de ServiceModel de WCF, que le permiten configurar el servicio WCF y las aplicaciones cliente.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 44966ed9ee3abb3d1babdf09dd44f087376ada55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158687"
---
# \<system.serviceModel>

Esta sección de configuración contiene todos los elementos de configuración de ServiceModel Windows Communication Foundation (WCF).  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  

 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behaviors>](behaviors.md)|Esta sección define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios. Su atributo de `name` único identifica cada elemento de comportamiento.|  
|[\<bindings>](bindings.md)|Esta sección contiene una colección de enlaces estándar y personalizados. Su `name` único identifica cada entrada. Los servicios usan los enlaces vinculándose a ellos mediante `name`.|  
|[\<client>](client.md)|Esta sección contiene una lista de extremos que usa un cliente para conectarse a un servicio.|  
|[\<comContracts>](comcontracts.md)|Esta sección define contratos COM habilitados para WCF e interoperabilidad COM.|  
|[\<commonBehaviors>](commonbehaviors.md)|Esta sección solo se puede definir en el archivo machine.config. Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define los elementos de comportamiento utilizados por todos los puntos de conexión y servicios de WCF en el equipo, respectivamente.  Si un comportamiento se define en las secciones `<commonBehaviors>` y `<behaviors>`, el comportamiento en la sección \<behaviors> tendrá preferencia.|  
|[\<diagnostics>](diagnostics.md)|Esta sección contiene la configuración para las características de diagnóstico de WCF. El usuario puede habilitar/deshabilitar el seguimiento, contadores de rendimiento y el proveedor de WMI, y puede agregar filtros de mensajes personalizados.|  
|[\<extensions>](extensions-section.md)|Esta sección contiene una colección de extensiones, que permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.|  
|[\<protocolMapping>](protocolmapping.md)|En esta sección se define un conjunto de asignación de protocolos predeterminados entre los esquemas de protocolos de transporte (ej., http, net.tcp, net.pipe, etc.) y enlaces WCF.|  
|[\<routing>](routing.md)|En esta sección se define un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|Esta sección define para qué tipo el entorno de host de servicio crea instancias de un transporte determinado. Si esta sección está vacía, se usa el tipo predeterminado.|  
|[\<services>](services.md)|Esta sección contiene una colección de servicios. Para cada servicio definido en el ensamblado, este elemento contiene un elemento `service` que especifica la configuración del servicio.|  
|[\<standardEndpoints>](standardendpoints.md)|Esta sección define una colección de extremos estándar, que son los extremos preconfigurados reutilizables. Un punto de conexión estándar tendrá uno o más atributos de la dirección, el enlace y el contrato establecidos en un valor fijo. Por ejemplo, en el punto de conexión de la detección el contrato es fijo. También puede usar los puntos de conexión estándar para extender el punto de conexión de servicio con nuevas propiedades similares a la definición de enlaces personalizados.|
|[\<tracking>](tracking-of-wcf.md)|En esta sección se define la configuración de seguimiento de un servicio de flujo de trabajo.|

### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\<configuration>|El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.|  
  
## <a name="remarks"></a>Observaciones  

 WCF no agrega elementos a las secciones de configuración de otros productos.  
  
 Los servicios WCF se definen en la `services` sección del archivo de configuración. Un ensamblado puede contener cualquier número de servicios. Cada servicio tiene su propia sección de configuración de `service`. La sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.  
  
 Sólo se requiere el atributo de `name` del servicio.  De forma predeterminada, el nombre de un servicio describe el tipo CLR subyacente usado para implementar un servicio; sin embargo, puede cambiar la propiedad ConfigurationName en <xref:System.ServiceModel.ServiceContractAttribute> para invalidar el requisito de tipo de CLR.  
  
 El atributo `behaviorConfiguration` es opcional. Identifica el comportamiento del servicio usado por un servicio. El comportamiento especificado por este atributo debe vincularse a un comportamiento del servicio definido en el ámbito del mismo archivo de configuración (es decir, el mismo archivo o un archivo primario).  
  
 Cada servicio expone uno o más puntos de conexión definidos en un elemento `endpoint`. Cada extremo tiene su propia dirección y enlace. Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.  
  
 Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`. El atributo de `binding` define la sección en que está definido el enlace. El atributo `bindingConfiguration` define el enlace configurado que se usa en la sección de enlaces. Una sección de enlaces puede definir varios enlaces configurados.  
  
## <a name="example"></a>Ejemplo  

 Esto es un ejemplo de un archivo de configuración de WCF.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
