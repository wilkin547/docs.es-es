---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399972"
---
# \<routing>

<span data-ttu-id="6f8c0-101">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-101">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**
  
## <a name="syntax"></a><span data-ttu-id="6f8c0-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f8c0-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f8c0-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6f8c0-103">Attributes and elements</span></span>

<span data-ttu-id="6f8c0-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f8c0-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f8c0-105">Attributes</span></span>

<span data-ttu-id="6f8c0-106">None</span><span class="sxs-lookup"><span data-stu-id="6f8c0-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="6f8c0-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f8c0-107">Child elements</span></span>

|     | <span data-ttu-id="6f8c0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f8c0-108">Description</span></span> |
| --- | ----------- |
| [**\<filters>**](filters-of-routing.md) | <span data-ttu-id="6f8c0-109">Contiene un conjunto de filtros de enrutamiento que determinan el tipo de Windows Communication Foundation (WCF) MessageFilter se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-109">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [**\<filterTables>**](filtertables.md) | <span data-ttu-id="6f8c0-110">Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-110">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="6f8c0-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6f8c0-111">Parent elements</span></span>

|     | <span data-ttu-id="6f8c0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f8c0-112">Description</span></span> |
| --- | ----------- |
| **\<system.ServiceModel>** | <span data-ttu-id="6f8c0-113">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-113">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6f8c0-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f8c0-114">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
