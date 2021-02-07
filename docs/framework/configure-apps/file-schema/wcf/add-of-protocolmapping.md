---
description: 'Más información sobre: <add> de <protocolMapping>'
title: <add> de <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 530ef6b2893eb55a979aba2ef7ec21efffc3070a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750252"
---
# <a name="add-of-protocolmapping"></a>\<add> de \<protocolMapping>

Representa una asignación de protocolo predeterminada entre un esquema de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y un enlace Windows Communication Foundation (WCF). Al crear puntos de conexión predeterminados en tiempo de ejecución, WCF examina las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
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
|binding|Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.|  
|bindingConfiguration|Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.|  
|scheme|Esquema de protocolos de transporte que se va a utilizar para el extremo predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|Representa una sección de configuración para definir las asignaciones de protocolo predeterminadas entre los esquemas de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y los enlaces de Windows Communication Foundation (WCF).|  
  
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
