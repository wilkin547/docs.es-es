---
title: '&lt;baseAddressPrefixFilters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a1c2e5e887ceaadf3db6f51991d53c3db8fb6ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltbaseaddressprefixfiltersgt"></a>&lt;baseAddressPrefixFilters&gt;
Representa una colección de elementos de configuración que especifica filtros de paso a través, que proporcionan un mecanismo para seleccionar los enlaces adecuados de Internet Information Server (IIS) al hospedar una aplicación de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] en IIS.  
  
> [!WARNING]
>  \<baseAddressPrefixFilters > no reconoce el "localhost", use el nombre de equipo completo en su lugar.  
  
 \<sistema. ServiceModel >  
\<ServiceHostingEnvironment >  
  
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
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|Agrega un elemento de configuración que especifica un filtro de prefijo para las direcciones base usadas por el host de servicio.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.|  
  
## <a name="remarks"></a>Comentarios  
 Un filtro de prefijo proporciona un método para que los proveedores de host compartido especifiquen qué identificadores URI va a utiliza el servicio. Permite a los host compartidos hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.  
  
 Los sitios web de IIS son los contenedores para las aplicaciones virtuales que contienen los directorios virtuales. Se puede tener acceso a la aplicación en un sitio a través de uno o más enlaces de IIS. Los enlaces de IIS proporcionan dos partes de información: protocolo de enlace e información de enlace. El protocolo de enlace (por ejemplo, HTTP), define el esquema sobre el que la comunicación se produce y la información de enlace (por ejemplo, IPAddress, Puerto, Hostheader) contiene los datos utilizados para tener acceso al sitio.  
  
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
  
 En este ejemplo, `net.tcp://test1.fabrikam.com:8000` y `http://test2.fabrikam.com:9000` son las únicas direcciones base para sus respectivos esquemas, a través de los que se puede pasar.  
  
 De forma predeterminada, cuando no se especifica el prefijo, se pasan todas las direcciones. Especificar el prefijo permite que solo la dirección base coincidente para ese esquema se pase a través.  
  
> [!NOTE]
>  El filtro no admite ningún carácter comodín. Además, las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`. Estas direcciones no se filtran.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [Hospedar aplicaciones de WPF](../../../../../docs/framework/wcf/feature-details/hosting.md)
