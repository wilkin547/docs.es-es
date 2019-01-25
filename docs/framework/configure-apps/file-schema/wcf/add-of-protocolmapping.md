---
title: '&lt;add&gt; de &lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: ce970b9ef71e2a28de680926f96f83500948619b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632821"
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a>&lt;add&gt; de &lt;protocolMapping&gt;
Representa una asignación de protocolo predeterminado entre un esquema de protocolo de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y un enlace de Windows Communication Foundation (WCF). Al crear puntos de conexión predeterminados en tiempo de ejecución, WCF examina las asignaciones configuradas y decide qué enlace usar para una determinada dirección base.  
  
 \<system.serviceModel>  
\<protocolMapping>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|enlace|Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.|  
|bindingConfiguration|Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.|  
|scheme|Esquema de protocolos de transporte que se va a utilizar para el punto de conexión predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<protocolMapping>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Representa una sección de configuración para definir las asignaciones de protocolos predeterminados entre esquemas de protocolos de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y enlaces de Windows Communication Foundation (WCF).|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config. Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config. O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
