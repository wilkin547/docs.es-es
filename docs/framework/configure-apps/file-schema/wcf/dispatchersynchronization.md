---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 537dee408f1af29a06042de439a2c1e7d7874222
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555393"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="a7bed-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="a7bed-102">&lt;dispatcherSynchronization&gt;</span></span>
  
<span data-ttu-id="a7bed-103">Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a7bed-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="a7bed-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a7bed-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a7bed-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a7bed-105">\<behaviors></span></span>  
<span data-ttu-id="a7bed-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a7bed-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a7bed-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a7bed-107">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7bed-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7bed-108">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="a7bed-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="a7bed-109">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7bed-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a7bed-110">Attributes and elements</span></span>  
  
<span data-ttu-id="a7bed-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a7bed-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7bed-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7bed-112">Attributes</span></span>

| <span data-ttu-id="a7bed-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a7bed-113">Attribute</span></span>               | <span data-ttu-id="a7bed-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7bed-114">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="a7bed-115">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="a7bed-115">asynchronousSendEnabled</span></span> | <span data-ttu-id="a7bed-116">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a7bed-116">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="a7bed-117">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="a7bed-117">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="a7bed-118">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="a7bed-118">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="a7bed-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7bed-119">Child elements</span></span>

<span data-ttu-id="a7bed-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a7bed-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a7bed-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a7bed-121">Parent elements</span></span>

| <span data-ttu-id="a7bed-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7bed-122">Element</span></span> | <span data-ttu-id="a7bed-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7bed-123">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="a7bed-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a7bed-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a7bed-125">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a7bed-125">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a7bed-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7bed-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
