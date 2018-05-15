---
title: '&lt;Enrutamiento&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt"></a><span data-ttu-id="d398a-102">&lt;Enrutamiento&gt;</span><span class="sxs-lookup"><span data-stu-id="d398a-102">&lt;routing&gt;</span></span>

<span data-ttu-id="d398a-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="d398a-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="d398a-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="d398a-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="d398a-105">&nbsp;&nbsp;**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="d398a-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d398a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d398a-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d398a-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d398a-107">Attributes and elements</span></span>

<span data-ttu-id="d398a-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d398a-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d398a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d398a-109">Attributes</span></span>

<span data-ttu-id="d398a-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d398a-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d398a-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d398a-111">Child elements</span></span>

|     | <span data-ttu-id="d398a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d398a-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d398a-113">**\<filtros >**</span><span class="sxs-lookup"><span data-stu-id="d398a-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="d398a-114">Contiene un conjunto de filtros de enrutamiento que determinan el tipo de MessageFilter de Windows Communication Foundation (WCF) que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="d398a-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="d398a-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="d398a-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="d398a-116">Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro.</span><span class="sxs-lookup"><span data-stu-id="d398a-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="d398a-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d398a-117">Parent elements</span></span>

|     | <span data-ttu-id="d398a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d398a-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="d398a-119">**\<sistema. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="d398a-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="d398a-120">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="d398a-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d398a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d398a-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
