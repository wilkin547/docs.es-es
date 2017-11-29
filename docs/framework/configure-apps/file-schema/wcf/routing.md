---
title: '&lt;enrutamiento&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed2dd4e68584d6e79e18fc9b61fcc8f078615dac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltroutinggt"></a>&lt;enrutamiento&gt;

Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;**\<enrutamiento >**

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

Ninguna

### <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<filtros >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Contiene un conjunto de filtros de enrutamiento que determinan el tipo de MessageFilter de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se usará al evaluar los mensajes entrantes. |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro. |

### <a name="parent-elements"></a>Elementos primarios

|     | Descripción |
| --- | ----------- |
| **\<sistema. ServiceModel >** | Elemento raíz de todos los elementos de configuración de WCF. |

## <a name="see-also"></a>Vea también

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
