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
# <a name="filters-of-routing"></a><span data-ttu-id="fca77-102">\<> filtros de \<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="fca77-102">\<filters> of \<routing></span></span>

<span data-ttu-id="fca77-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="fca77-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="fca77-104">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fca77-104">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fca77-105">&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="fca77-105">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="fca77-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**</span><span class="sxs-lookup"><span data-stu-id="fca77-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca77-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fca77-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fca77-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fca77-108">Attributes and elements</span></span>

<span data-ttu-id="fca77-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fca77-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fca77-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="fca77-110">Attributes</span></span>

<span data-ttu-id="fca77-111">None</span><span class="sxs-lookup"><span data-stu-id="fca77-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="fca77-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fca77-112">Child elements</span></span>

|     | <span data-ttu-id="fca77-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fca77-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fca77-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="fca77-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="fca77-115">Contiene un filtro de enrutamiento que determina el tipo de Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="fca77-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="fca77-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fca77-116">Parent elements</span></span>

|     | <span data-ttu-id="fca77-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fca77-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fca77-118"> **\<> de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="fca77-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="fca77-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino. enviar mensajes a cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="fca77-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="fca77-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fca77-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
