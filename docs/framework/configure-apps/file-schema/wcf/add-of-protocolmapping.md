---
title: '&lt;add&gt; de &lt;protocolMapping&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a254b8a4de8f66cb0d051d246be2d07e905615a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a>&lt;add&gt; de &lt;protocolMapping&gt;
Representa una asignación de protocolo predeterminado entre un esquema de protocolo de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y un [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] enlace. Al crear extremos predeterminados en tiempo de ejecución, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] observa las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.  
  
 \<system.serviceModel >  
\<protocolMapping >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
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
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Representa una sección de configuración para definir las asignaciones de protocolos predeterminados entre esquemas de protocolos de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] enlaces.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config. Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config. O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
