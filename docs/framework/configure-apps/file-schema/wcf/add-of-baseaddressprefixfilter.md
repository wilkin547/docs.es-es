---
title: '&lt;add&gt; de &lt;baseAddressPrefixFilter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad6ad6f71ef015ad97a2688a7334e8a0c6e5af44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a>&lt;add&gt; de &lt;baseAddressPrefixFilter&gt;
Representa un elemento de configuración que especifica un filtro del paso a través, que proporciona un mecanismo para seleccionar los enlaces adecuados del servicio de Internet Information Server (IIS) al hospedar una aplicación [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] en IIS.  
  
 \<sistema. ServiceModel >  
\<ServiceHostingEnvironment >  
\<baseAddressPrefixFilters >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|prefix|Un URI que se utiliza para coincidir con una parte de una dirección base.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|Una colección de elementos de configuración que especifican filtros del paso a través, que proporcionan un mecanismo para seleccionar los enlaces adecuados de IIS al hospedar una aplicación [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] en IIS.|  
  
## <a name="remarks"></a>Comentarios  
 Un filtro de prefijo proporciona un método para que los proveedores de host compartido especifiquen qué identificadores URI va a utiliza el servicio. Permite a los host compartidos hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.  
  
 Los sitios web de IIS son los contenedores para las aplicaciones virtuales que contienen los directorios virtuales. Se puede tener acceso a la aplicación de un sitio a través de uno o varios enlaces de IIS. Los enlaces de IIS proporcionan dos partes de información: protocolo de enlace e información de enlace. El protocolo de enlace (por ejemplo, HTTP), define el esquema sobre el que la comunicación se produce y la información de enlace (por ejemplo, IPAddress, Puerto, Hostheader) contiene los datos utilizados para tener acceso al sitio.  
  
 IIS admite la especificación de varios enlaces IIS para cada sitio, lo que tiene como resultado varias direcciones base para cada esquema. Puesto que un servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] hospedado bajo un sitio permite el enlace a solo una dirección base por cada esquema, se puede utilizar la característica de filtro de prefijo para escoger la dirección base necesaria del servicio hospedado. Las direcciones base de entrada, proporcionadas por IIS, se filtran dependiendo del filtro de la lista de prefijos opcional.  
  
 Por ejemplo, su sitio puede contener las direcciones base siguientes.  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 Puede utilizar el archivo de configuración siguiente para especificar un filtro del prefijo en el nivel appdomain.  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://test1.fabrikam.com:8000"/>  
        <add prefix="http://test2.fabrikam.com:9000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 En este ejemplo, `net.tcp://test1.fabrikam.com:8000` y `http://test2.fabrikam.com:9000` son las únicas direcciones base para los respectivos esquemas a través de los que se puede pasar.  
  
 De forma predeterminada, cuando no se especifica el prefijo, se pasan todas las direcciones. Especificar el prefijo permite que solo la dirección base coincidente para ese esquema se pase a través.  
  
> [!NOTE]
>  El filtro no admite ningún carácter comodín. Además, las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`. Estas direcciones no se filtran.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [Hospedar aplicaciones de WPF](../../../../../docs/framework/wcf/feature-details/hosting.md)
