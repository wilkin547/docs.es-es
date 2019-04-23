---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: 1e5ecc2b937aa0cdb159a6cbd1222fe6d4af79fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159853"
---
# <a name="compositeduplex"></a>\<compositeDuplex>
Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<compositeDuplex>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|clientBaseAddress|Un URI que establece la dirección del canal secundario en modo de dúplex. El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.<br /><br /> Si este atributo no se establece, una dirección predeterminada "`full qualified name+default port\TemporaryIndigoAddress\guid`" se genera. De manera predeterminada, es `null`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP. TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.  
  
 El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión. El atributo `clientBaseAddress` proporciona esta dirección del cliente. Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
