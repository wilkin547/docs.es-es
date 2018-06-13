---
title: '&lt;system.serviceModel&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: ef3af4663462ff2bb93622e128e58a3ac039dcf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353216"
---
# <a name="ltsystemservicemodelgt"></a>&lt;system.serviceModel&gt;
Esta sección de configuración contiene todos los elementos de configuración de ServiceModel de Windows Communication Foundation (WCF).  
  
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
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguna  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<comportamientos >](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|Esta sección define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios. Su atributo de `name` único identifica cada elemento de comportamiento.|  
|[\<enlaces >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Esta sección contiene una colección de enlaces estándar y personalizados. Su `name` único identifica cada entrada. Los servicios usan los enlaces vinculándose a ellos mediante `name`.|  
|[\<cliente >](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|Esta sección contiene una lista de puntos de conexión que usa un cliente para conectarse a un servicio.|  
|[\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|Esta sección define contratos COM habilitados para WCF e interoperabilidad COM.|  
|[\<commonBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|Esta sección solo se puede definir en el archivo machine.config. Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define elementos de comportamiento utilizados respectivamente por todos los extremos WCF y servicios en el equipo.  Si se define un comportamiento en las `<commonBehaviors>` y `<behaviors>` secciones, el comportamiento en el \<comportamientos > sección tendrá preferencia.|  
|[\<las extensiones >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|Esta sección contiene una colección de extensiones, que permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.|  
|[\<diagnóstico >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Esta sección contiene la configuración para las características de diagnóstico de WCF. El usuario puede habilitar/deshabilitar el seguimiento, contadores de rendimiento y el proveedor de WMI, y puede agregar filtros de mensajes personalizados.|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Esta sección define un conjunto de asignación de protocolo predeterminado entre los esquemas de protocolos de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y enlaces de WCF.|  
|[\<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Esta sección define un conjunto de filtros de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los puntos de conexión de destino para enviar mensajes cuando un coincide con el filtro.|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Esta sección define para qué tipo el entorno de host de servicio crea instancias de un transporte determinado. Si esta sección está vacía, se usa el tipo predeterminado.|  
|[\<Servicios >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Esta sección contiene una colección de servicios. Para cada servicio definido en el ensamblado, este elemento contiene un elemento `service` que especifica la configuración del servicio.|  
|[\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Esta sección define una colección de puntos de conexión estándar, que son los puntos de conexión preconfigurados reutilizables. Un extremo estándar tendrá uno o más atributos de la dirección, el enlace y el contrato establecidos en un valor fijo. Por ejemplo, en el extremo de la detección el contrato es fijo. También puede usar los puntos de conexión estándar para extender el punto de conexión de servicio con nuevas propiedades similares a la definición de enlaces personalizados.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\<configuration>|El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.|  
  
## <a name="remarks"></a>Comentarios  
 WCF no agrega elementos a las secciones de configuración de otros productos.  
  
 Servicios WCF se definen en la `services` sección del archivo de configuración. Un ensamblado puede contener cualquier número de servicios. Cada servicio tiene su propia sección de configuración de `service`. La sección y su contenido definen el contrato de servicios, comportamiento y extremos del servicio determinado.  
  
 Sólo se requiere el atributo de `name` del servicio.  De forma predeterminada, el nombre de un servicio describe el tipo CLR subyacente usado para implementar un servicio; sin embargo, puede cambiar la propiedad ConfigurationName en <xref:System.ServiceModel.ServiceContractAttribute> para invalidar el requisito de tipo de CLR.  
  
 El atributo `behaviorConfiguration` es opcional. Identifica el comportamiento del servicio usado por un servicio. El comportamiento especificado por este atributo debe vincularse a un comportamiento del servicio definido en el ámbito del mismo archivo de configuración (es decir, el mismo archivo o un archivo primario).  
  
 Cada servicio expone uno o más extremos definidos en un elemento `endpoint`. Cada extremo tiene su propia dirección y enlace. Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.  
  
 Los enlaces se vinculan a los extremos a través de la combinación de los atributos `name` y `bindingConfiguration`. El atributo de `binding` define la sección en que está definido el enlace. El atributo `bindingConfiguration` define el enlace configurado que se usa en la sección de enlaces. Una sección de enlaces puede definir varios enlaces configurados.  
  
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
        <diagnostics wmiProviderEnabled="false" performanceCountersEnabled="false" tracingEnabled="false">  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
