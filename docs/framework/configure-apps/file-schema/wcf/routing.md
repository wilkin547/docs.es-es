---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399972"
---
# <a name="routing"></a><span data-ttu-id="c25da-101">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="c25da-101">\<routing></span></span>

<span data-ttu-id="c25da-102">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) que se va a usar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino. enviar mensajes a cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="c25da-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="c25da-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c25da-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c25da-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c25da-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c25da-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enrutamiento**</span><span class="sxs-lookup"><span data-stu-id="c25da-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c25da-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c25da-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c25da-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c25da-107">Attributes and elements</span></span>

<span data-ttu-id="c25da-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c25da-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c25da-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c25da-109">Attributes</span></span>

<span data-ttu-id="c25da-110">None</span><span class="sxs-lookup"><span data-stu-id="c25da-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c25da-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c25da-111">Child elements</span></span>

|     | <span data-ttu-id="c25da-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c25da-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c25da-113"> **\<filters>** </span><span class="sxs-lookup"><span data-stu-id="c25da-113">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="c25da-114">Contiene un conjunto de filtros de enrutamiento que determinan el tipo de Windows Communication Foundation (WCF) MessageFilter se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c25da-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="c25da-115"> **\<filterTables>** </span><span class="sxs-lookup"><span data-stu-id="c25da-115">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="c25da-116">Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro.</span><span class="sxs-lookup"><span data-stu-id="c25da-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c25da-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c25da-117">Parent elements</span></span>

|     | <span data-ttu-id="c25da-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c25da-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="c25da-119">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="c25da-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="c25da-120">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="c25da-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c25da-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c25da-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
