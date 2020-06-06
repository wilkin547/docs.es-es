---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736777"
---
# \<compositeDuplex>
Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|clientBaseAddress|Un URI que establece la dirección del canal secundario en modo de dúplex. El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.<br /><br /> Si no se establece este atributo, se genera una dirección predeterminada " `full qualified name+default port\TemporaryIndigoAddress\guid` ". De manera predeterminada, es `null`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP. TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.  
  
 El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión. El atributo `clientBaseAddress` proporciona esta dirección del cliente. Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
