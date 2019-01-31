---
title: <filters> de <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 8b2c735a19c4cece16dcb77e3ec548eb2d39ec18
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272693"
---
# <a name="filters-of-routing"></a><span data-ttu-id="9f7bd-102">\<filtros > de \<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="9f7bd-102">\<filters> of \<routing></span></span>

<span data-ttu-id="9f7bd-103">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="9f7bd-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="9f7bd-104">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="9f7bd-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="9f7bd-105">&nbsp;&nbsp;[**\<enrutamiento >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="9f7bd-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="9f7bd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="9f7bd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9f7bd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f7bd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f7bd-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9f7bd-108">Attributes and elements</span></span>

<span data-ttu-id="9f7bd-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9f7bd-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f7bd-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9f7bd-110">Attributes</span></span>

<span data-ttu-id="9f7bd-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9f7bd-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f7bd-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9f7bd-112">Child elements</span></span>

|     | <span data-ttu-id="9f7bd-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f7bd-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9f7bd-114">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="9f7bd-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="9f7bd-115">Contiene un filtro de enrutamiento que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="9f7bd-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="9f7bd-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9f7bd-116">Parent elements</span></span>

|     | <span data-ttu-id="9f7bd-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f7bd-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9f7bd-118">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="9f7bd-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="9f7bd-119">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="9f7bd-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9f7bd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f7bd-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
