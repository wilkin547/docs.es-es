---
title: '&lt;filters&gt; de &lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 9f0fa9bf51d264346738172f57a8efca7950fdb7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltersgt-of-ltroutinggt"></a>&lt;filters&gt; de &lt;routing&gt;

Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;[**\<enrutamiento >**](routing.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<filtros >**

## <a name="syntax"></a>Sintaxis

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

Ninguna

### <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<Filtro >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Contiene un filtro de enrutamiento que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> se usará al evaluar los mensajes entrantes. |

### <a name="parent-elements"></a>Elementos primarios

|     | Descripción |
| --- | ----------- |
| [**\<enrutamiento >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro. |

## <a name="see-also"></a>Vea también

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
