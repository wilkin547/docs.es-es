---
title: <filters> de <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855239"
---
# <a name="filters-of-routing"></a><span data-ttu-id="38824-102">\<filters> de \<routing></span><span class="sxs-lookup"><span data-stu-id="38824-102">\<filters> of \<routing></span></span>

<span data-ttu-id="38824-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="38824-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a><span data-ttu-id="38824-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38824-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38824-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38824-105">Attributes and elements</span></span>

<span data-ttu-id="38824-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38824-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="38824-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="38824-107">Attributes</span></span>

<span data-ttu-id="38824-108">None</span><span class="sxs-lookup"><span data-stu-id="38824-108">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="38824-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38824-109">Child elements</span></span>

|     | <span data-ttu-id="38824-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="38824-110">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="38824-111">Contiene un filtro de enrutamiento que determina el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="38824-111">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="38824-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38824-112">Parent elements</span></span>

|     | <span data-ttu-id="38824-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="38824-113">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="38824-114">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="38824-114">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="38824-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38824-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
