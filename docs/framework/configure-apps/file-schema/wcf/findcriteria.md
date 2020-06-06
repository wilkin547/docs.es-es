---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855165"
---
# \<findCriteria>
Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección. Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y en criterios de finalización de búsqueda (cuánto tiempo debería durar la búsqueda).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|duration|Un valor Timespan que especifica el tiempo máximo para esperar respuestas de los servicios en la red. La duración predeterminada es de 20 segundos.|  
|maxResults|Entero que especifica el número máximo de respuestas que se deben esperar, de los servicios en una red o de Internet. Si se recibe el máximo de respuestas antes de que haya transcurrido el valor especificado en el atributo `duration`, finalizará la operación de búsqueda.|  
|scopeMatchBy|URI que especifica el algoritmo de coincidencia que se va a utilizar al establecer las coincidencias de los ámbitos del mensaje de sondeo con los del punto de conexión.<br /><br /> Hay cinco reglas de coincidencia de ámbito admitidas. Si no especifica ninguna regla de coincidencia de ámbito, se usa `ScopeMatchByPrefix`. Para obtener más información sobre este tema vea <xref:System.ServiceModel.Discovery.FindCriteria>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|Colección de elementos de configuración que contienen los nombres de los tipos de contrato de servicio de flujo de trabajo.|  
|\<extensions> de \<findCriteria>|Colección de objetos de elementos XML que proporcionan las extensiones.|  
|[\<scopes>](scopes.md)|Colección de objetos que contienen URI absolutos que se usan durante una operación de búsqueda para localizar un servicio o servicios concretos.<br /><br /> Si se encuentra el servicio concreto, se ha establecido una coincidencia correcta entre el URI del servicio y el URI del ámbito, en ocasiones con la ayuda de las reglas de ámbito que se ocupan de las complicaciones relativas a las coincidencias.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
