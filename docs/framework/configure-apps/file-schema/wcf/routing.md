---
description: 'Más información acerca de: <routing>'
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 62222b527a14310b66015d4fdc4503e6cff25c8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683351"
---
# \<routing>

<span data-ttu-id="e62f9-102">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="e62f9-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**
  
## <a name="syntax"></a><span data-ttu-id="e62f9-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e62f9-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e62f9-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e62f9-104">Attributes and elements</span></span>

<span data-ttu-id="e62f9-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e62f9-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e62f9-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="e62f9-106">Attributes</span></span>

<span data-ttu-id="e62f9-107">None</span><span class="sxs-lookup"><span data-stu-id="e62f9-107">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="e62f9-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e62f9-108">Child elements</span></span>

|     | <span data-ttu-id="e62f9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e62f9-109">Description</span></span> |
| --- | ----------- |
| [**\<filters>**](filters-of-routing.md) | <span data-ttu-id="e62f9-110">Contiene un conjunto de filtros de enrutamiento que determinan el tipo de Windows Communication Foundation (WCF) MessageFilter se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e62f9-110">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [**\<filterTables>**](filtertables.md) | <span data-ttu-id="e62f9-111">Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro.</span><span class="sxs-lookup"><span data-stu-id="e62f9-111">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="e62f9-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e62f9-112">Parent elements</span></span>

|     | <span data-ttu-id="e62f9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e62f9-113">Description</span></span> |
| --- | ----------- |
| **\<system.ServiceModel>** | <span data-ttu-id="e62f9-114">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="e62f9-114">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e62f9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e62f9-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
