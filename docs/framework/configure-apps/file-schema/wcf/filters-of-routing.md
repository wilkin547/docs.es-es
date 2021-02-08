---
description: 'Más información sobre: <filters> de <routing>'
title: <filters> de <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 41b51453f53fca042f53ca1ee8372413b8478ecd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782057"
---
# <a name="filters-of-routing"></a><span data-ttu-id="82baf-103">\<filters> de \<routing></span><span class="sxs-lookup"><span data-stu-id="82baf-103">\<filters> of \<routing></span></span>

<span data-ttu-id="82baf-104">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="82baf-104">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a><span data-ttu-id="82baf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82baf-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82baf-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="82baf-106">Attributes and elements</span></span>

<span data-ttu-id="82baf-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="82baf-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="82baf-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="82baf-108">Attributes</span></span>

<span data-ttu-id="82baf-109">None</span><span class="sxs-lookup"><span data-stu-id="82baf-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="82baf-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="82baf-110">Child elements</span></span>

|     | <span data-ttu-id="82baf-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="82baf-111">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="82baf-112">Contiene un filtro de enrutamiento que determina el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="82baf-112">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="82baf-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="82baf-113">Parent elements</span></span>

|     | <span data-ttu-id="82baf-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="82baf-114">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="82baf-115">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="82baf-115">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="82baf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="82baf-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
