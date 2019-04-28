---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 6be9752e8102a5d4db4fed31aae8ff6d56fdd24e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673412"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="fd6a8-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="fd6a8-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="fd6a8-102">Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="fd6a8-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fd6a8-103">\<system.serviceModel></span></span>  
<span data-ttu-id="fd6a8-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="fd6a8-104">\<behaviors></span></span>  
<span data-ttu-id="fd6a8-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="fd6a8-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="fd6a8-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="fd6a8-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd6a8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd6a8-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="fd6a8-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="fd6a8-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd6a8-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fd6a8-109">Attributes and elements</span></span>  
  
<span data-ttu-id="fd6a8-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd6a8-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd6a8-111">Attributes</span></span>

| <span data-ttu-id="fd6a8-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="fd6a8-112">Attribute</span></span>               | <span data-ttu-id="fd6a8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd6a8-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="fd6a8-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="fd6a8-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="fd6a8-115">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="fd6a8-116">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="fd6a8-117">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="fd6a8-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fd6a8-118">Child elements</span></span>

<span data-ttu-id="fd6a8-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fd6a8-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fd6a8-120">Parent elements</span></span>

| <span data-ttu-id="fd6a8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd6a8-121">Element</span></span> | <span data-ttu-id="fd6a8-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd6a8-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="fd6a8-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fd6a8-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="fd6a8-124">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fd6a8-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="fd6a8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd6a8-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
