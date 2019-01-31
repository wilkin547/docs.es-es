---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 6be9752e8102a5d4db4fed31aae8ff6d56fdd24e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273337"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="d4b96-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="d4b96-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="d4b96-102">Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="d4b96-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="d4b96-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d4b96-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d4b96-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d4b96-104">\<behaviors></span></span>  
<span data-ttu-id="d4b96-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d4b96-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="d4b96-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d4b96-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b96-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4b96-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="d4b96-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="d4b96-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4b96-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d4b96-109">Attributes and elements</span></span>  
  
<span data-ttu-id="d4b96-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d4b96-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4b96-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d4b96-111">Attributes</span></span>

| <span data-ttu-id="d4b96-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="d4b96-112">Attribute</span></span>               | <span data-ttu-id="d4b96-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4b96-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="d4b96-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="d4b96-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="d4b96-115">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="d4b96-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="d4b96-116">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="d4b96-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="d4b96-117">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="d4b96-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="d4b96-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d4b96-118">Child elements</span></span>

<span data-ttu-id="d4b96-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d4b96-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d4b96-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d4b96-120">Parent elements</span></span>

| <span data-ttu-id="d4b96-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4b96-121">Element</span></span> | <span data-ttu-id="d4b96-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4b96-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="d4b96-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d4b96-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d4b96-124">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d4b96-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d4b96-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4b96-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
