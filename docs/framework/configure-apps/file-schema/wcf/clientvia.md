---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673633"
---
# <a name="clientvia"></a><span data-ttu-id="14979-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="14979-101">\<clientVia></span></span>
<span data-ttu-id="14979-102">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="14979-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="14979-103">Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="14979-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="14979-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="14979-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="14979-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="14979-105">\<behaviors></span></span>  
<span data-ttu-id="14979-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="14979-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="14979-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="14979-107">\<behavior></span></span>  
<span data-ttu-id="14979-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="14979-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14979-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14979-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14979-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="14979-110">Attributes and Elements</span></span>  
 <span data-ttu-id="14979-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="14979-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14979-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="14979-112">Attributes</span></span>  
  
|<span data-ttu-id="14979-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="14979-113">Attribute</span></span>|<span data-ttu-id="14979-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="14979-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="14979-115">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="14979-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14979-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="14979-116">Child Elements</span></span>  
 <span data-ttu-id="14979-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="14979-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14979-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14979-118">Parent Elements</span></span>  
  
|<span data-ttu-id="14979-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="14979-119">Element</span></span>|<span data-ttu-id="14979-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="14979-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14979-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="14979-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="14979-122">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="14979-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14979-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="14979-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
