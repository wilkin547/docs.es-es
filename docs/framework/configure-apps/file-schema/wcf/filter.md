---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278790"
---
# <a name="filter"></a>\<filter>

Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, como así los datos o los parámetros requeridos por el filtro de apoyo.

\<system.serviceModel> \<routing> \<filters> \<filter>
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

| Atributo  | Descripción |
| ---------- | ----------- |
| customType | Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro. Si `filterType` está establecido en `custom`, este atributo contiene el nombre de tipo completo de la clase para crear.  `filterData` También se puede contener valores que se usarán durante la evaluación del filtro de tipo personalizado. |
| filterData | Cadena que contiene los datos del filtro. Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Cadena que contiene el tipo de filtro. Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| name       | Cadena que contiene el nombre único de este elemento de filtro. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |
| ------- | ----------- |
| [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes. |

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
