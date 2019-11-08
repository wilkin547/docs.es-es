---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738779"
---
# <a name="pnrppeerresolver"></a>\<pnrpPeerResolver >
Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución. Este elemento es opcional porque PNRP es la resolución predeterminada.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<pnrpResolver >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|resolverType|Una cadena que especifica la resolución que se va a utilizar. Este atributo es opcional. Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<> de enlace](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
- [Resoluciones del mismo nivel](../../../wcf/feature-details/peer-resolvers.md)
