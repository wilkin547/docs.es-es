---
title: <filters> de <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: ba60958ad33b46b40285f3f70001273bb3af3a63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925614"
---
# <a name="filters-of-routing"></a><span data-ttu-id="42d2c-102">\<> filtros de \<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="42d2c-102">\<filters> of \<routing></span></span>

<span data-ttu-id="42d2c-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="42d2c-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="42d2c-104">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="42d2c-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="42d2c-105">&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="42d2c-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="42d2c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**</span><span class="sxs-lookup"><span data-stu-id="42d2c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="42d2c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42d2c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42d2c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42d2c-108">Attributes and elements</span></span>

<span data-ttu-id="42d2c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42d2c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="42d2c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="42d2c-110">Attributes</span></span>

<span data-ttu-id="42d2c-111">None</span><span class="sxs-lookup"><span data-stu-id="42d2c-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="42d2c-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42d2c-112">Child elements</span></span>

|     | <span data-ttu-id="42d2c-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="42d2c-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="42d2c-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="42d2c-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="42d2c-115">Contiene un filtro de enrutamiento que determina el tipo de Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="42d2c-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="42d2c-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42d2c-116">Parent elements</span></span>

|     | <span data-ttu-id="42d2c-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="42d2c-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="42d2c-118"> **\<> de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="42d2c-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="42d2c-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino. enviar mensajes a cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="42d2c-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="42d2c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="42d2c-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
