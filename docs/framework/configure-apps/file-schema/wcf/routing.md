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
# <a name="routing"></a><span data-ttu-id="930b5-101">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="930b5-101">\<routing></span></span>

<span data-ttu-id="930b5-102">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino. enviar mensajes a cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="930b5-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="930b5-103">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="930b5-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="930b5-104">&nbsp;&nbsp; **\<> de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="930b5-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="930b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="930b5-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="930b5-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="930b5-106">Attributes and elements</span></span>

<span data-ttu-id="930b5-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="930b5-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="930b5-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="930b5-108">Attributes</span></span>

<span data-ttu-id="930b5-109">None</span><span class="sxs-lookup"><span data-stu-id="930b5-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="930b5-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="930b5-110">Child elements</span></span>

|     | <span data-ttu-id="930b5-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="930b5-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="930b5-112"> **\<filters>** </span><span class="sxs-lookup"><span data-stu-id="930b5-112">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="930b5-113">Contiene un conjunto de filtros de enrutamiento que determinan el tipo de Windows Communication Foundation (WCF) MessageFilter se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="930b5-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="930b5-114"> **\<filterTables>** </span><span class="sxs-lookup"><span data-stu-id="930b5-114">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="930b5-115">Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro.</span><span class="sxs-lookup"><span data-stu-id="930b5-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="930b5-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="930b5-116">Parent elements</span></span>

|     | <span data-ttu-id="930b5-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="930b5-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="930b5-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="930b5-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="930b5-119">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="930b5-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="930b5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="930b5-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
