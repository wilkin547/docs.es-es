---
title: <filters> de <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855239"
---
# <a name="filters-of-routing"></a>\<> filtros de \<> de enrutamiento

Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes.

[ **\<system.serviceModel>** ](system-servicemodel.md)\
&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**  
  
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

None

### <a name="child-elements"></a>Elementos secundarios

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<filter>** ](filter.md) | Contiene un filtro de enrutamiento que determina el tipo de Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) se usará al evaluar los mensajes entrantes. |

### <a name="parent-elements"></a>Elementos primarios

|     | DESCRIPCIÓN |
| --- | ----------- |
| [ **\<> de enrutamiento**](routing.md) | Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino. enviar mensajes a cuando coincida un filtro. |

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
