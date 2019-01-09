---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 86660620113b162a9a5260b7026a64455284d184
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151467"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="2368b-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="2368b-102">&lt;dispatcherSynchronization&gt;</span></span>
  
<span data-ttu-id="2368b-103">Especifica un comportamiento del punto de conexión que permite que un servicio envíe respuestas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2368b-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="2368b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2368b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2368b-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2368b-105">\<behaviors></span></span>  
<span data-ttu-id="2368b-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2368b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="2368b-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2368b-107">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2368b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2368b-108">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="2368b-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="2368b-109">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2368b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2368b-110">Attributes and elements</span></span>  
  
<span data-ttu-id="2368b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2368b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2368b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="2368b-112">Attributes</span></span>

| <span data-ttu-id="2368b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="2368b-113">Attribute</span></span>               | <span data-ttu-id="2368b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2368b-114">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="2368b-115">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="2368b-115">asynchronousSendEnabled</span></span> | <span data-ttu-id="2368b-116">Booleano que especifica si el comportamiento de envío asincrónico está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2368b-116">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="2368b-117">Entero que especifica el número de recepciones simultáneas que se pueden emitir en el canal.</span><span class="sxs-lookup"><span data-stu-id="2368b-117">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="2368b-118">Este valor solo debería configurarse después de haber configurado correctamente el comportamiento de limitación de peticiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="2368b-118">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="2368b-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2368b-119">Child elements</span></span>

<span data-ttu-id="2368b-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2368b-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2368b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2368b-121">Parent elements</span></span>

| <span data-ttu-id="2368b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2368b-122">Element</span></span> | <span data-ttu-id="2368b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="2368b-123">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="2368b-124">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2368b-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2368b-125">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2368b-125">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2368b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2368b-126">See also</span></span>

 <span data-ttu-id="2368b-127"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="2368b-127"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
