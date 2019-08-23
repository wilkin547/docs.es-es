---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 3c7e9cb1284ab55c8dd199d9fb47a223698814f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934127"
---
# <a name="routing"></a>\<> de enrutamiento

Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino. enviar mensajes a cuando coincida un filtro.

[ **\<system.serviceModel>** ](system-servicemodel.md)   
&nbsp;&nbsp; **\<> de enrutamiento**
  
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
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
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
| [ **\<filters>** ](filters-of-routing.md) | Contiene un conjunto de filtros de enrutamiento que determinan el tipo de Windows Communication Foundation (WCF) MessageFilter se usará al evaluar los mensajes entrantes. |
| [ **\<filterTables>** ](filtertables.md) | Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro. |

### <a name="parent-elements"></a>Elementos primarios

|     | DESCRIPCIÓN |
| --- | ----------- |
| **\<system.ServiceModel>** | Elemento raíz de todos los elementos de configuración de WCF. |

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
