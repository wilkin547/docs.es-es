---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: cc7c1a64f9481a7ab41cf35241ade04bd690dae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786391"
---
# <a name="routing"></a><span data-ttu-id="58e3f-101">\<routing></span><span class="sxs-lookup"><span data-stu-id="58e3f-101">\<routing></span></span>

<span data-ttu-id="58e3f-102">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="58e3f-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="58e3f-103">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="58e3f-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="58e3f-104">&nbsp;&nbsp;**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="58e3f-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="58e3f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58e3f-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58e3f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="58e3f-106">Attributes and elements</span></span>

<span data-ttu-id="58e3f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="58e3f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="58e3f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="58e3f-108">Attributes</span></span>

<span data-ttu-id="58e3f-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="58e3f-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="58e3f-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="58e3f-110">Child elements</span></span>

|     | <span data-ttu-id="58e3f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="58e3f-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="58e3f-112">**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="58e3f-112">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="58e3f-113">Contiene un conjunto de filtros de enrutamiento que determinan el tipo de MessageFilter de Windows Communication Foundation (WCF) que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="58e3f-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="58e3f-114">**\<filterTables>**</span><span class="sxs-lookup"><span data-stu-id="58e3f-114">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="58e3f-115">Contiene asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino para especificar qué punto de conexión usar cuando coincide el filtro.</span><span class="sxs-lookup"><span data-stu-id="58e3f-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="58e3f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="58e3f-116">Parent elements</span></span>

|     | <span data-ttu-id="58e3f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="58e3f-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="58e3f-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="58e3f-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="58e3f-119">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="58e3f-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="58e3f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="58e3f-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
