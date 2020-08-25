---
title: <add> de <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 2572a6ee6763ae26fe5c56669e10f8c9aef8a280
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811800"
---
# <a name="add-of-baseaddressprefixfilter"></a>\<add> de \<baseAddressPrefixFilter>
Representa un elemento de configuración que especifica un filtro de paso a través, que proporciona un mecanismo para seleccionar los enlaces de Internet Information Services (IIS) adecuados al hospedar una aplicación Windows Communication Foundation (WCF) en IIS.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
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
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|Colección de elementos de configuración que especifican filtros de paso a través, que proporcionan un mecanismo para seleccionar los enlaces de IIS adecuados al hospedar una aplicación Windows Communication Foundation (WCF) en IIS.|  
  
## <a name="remarks"></a>Comentarios  
 Un filtro de prefijo proporciona un método para que los proveedores de host compartido especifiquen qué identificadores URI va a utiliza el servicio. Permite a los host compartidos hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.  
  
 Los sitios web de IIS son los contenedores para las aplicaciones virtuales que contienen los directorios virtuales. Se puede tener acceso a la aplicación de un sitio a través de uno o varios enlaces de IIS. Los enlaces de IIS proporcionan dos partes de información: protocolo de enlace e información de enlace. El protocolo de enlace (por ejemplo, HTTP), define el esquema sobre el que la comunicación se produce y la información de enlace (por ejemplo, IPAddress, Puerto, Hostheader) contiene los datos utilizados para tener acceso al sitio.  
  
 IIS admite la especificación de varios enlaces IIS para cada sitio, lo que tiene como resultado varias direcciones base para cada esquema. Dado que un servicio WCF hospedado bajo un sitio permite el enlace solo a una dirección base para cada esquema, puede usar la característica de filtro de prefijo para seleccionar la dirección base necesaria del servicio hospedado. Las direcciones base de entrada, proporcionadas por IIS, se filtran dependiendo del filtro de la lista de prefijos opcional.  
  
 Por ejemplo, su sitio puede contener las siguientes direcciones base:
  
```http
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 Puede utilizar el archivo de configuración siguiente para especificar un filtro del prefijo en el nivel appdomain.  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 En este ejemplo, `net.tcp://test1.fabrikam.com:8000` y `http://test2.fabrikam.com:9000` son las únicas direcciones base para los respectivos esquemas a través de los que se puede pasar.  
  
 De forma predeterminada, cuando no se especifica el prefijo, se pasan todas las direcciones. Especificar el prefijo permite que solo la dirección base coincidente para ese esquema se pase a través.  
  
> [!NOTE]
> El filtro no admite ningún carácter comodín. Además, las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`. Estas direcciones no se filtran.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [Hospedar aplicaciones de WPF](../../../wcf/feature-details/hosting.md)
