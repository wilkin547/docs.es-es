---
title: '&lt;persistenceProvider&gt;'
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 3c7fd74a84184ddbf8cc8db90141174ed84e5774
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltpersistenceprovidergt"></a><span data-ttu-id="b5853-102">&lt;persistenceProvider&gt;</span><span class="sxs-lookup"><span data-stu-id="b5853-102">&lt;persistenceProvider&gt;</span></span>
<span data-ttu-id="b5853-103">Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="b5853-103">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="b5853-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b5853-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b5853-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="b5853-105">\<behaviors></span></span>  
<span data-ttu-id="b5853-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b5853-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b5853-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b5853-107">\<behavior></span></span>  
<span data-ttu-id="b5853-108">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="b5853-108">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5853-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5853-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5853-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b5853-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b5853-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b5853-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5853-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5853-112">Attributes</span></span>  
  
|<span data-ttu-id="b5853-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b5853-113">Attribute</span></span>|<span data-ttu-id="b5853-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5853-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5853-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="b5853-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="b5853-116">Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="b5853-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="b5853-117">El valor predeterminado es "00: 00:30".</span><span class="sxs-lookup"><span data-stu-id="b5853-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="b5853-118">type</span><span class="sxs-lookup"><span data-stu-id="b5853-118">type</span></span>|<span data-ttu-id="b5853-119">Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b5853-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5853-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b5853-120">Child Elements</span></span>  
 <span data-ttu-id="b5853-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b5853-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5853-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b5853-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b5853-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5853-123">Element</span></span>|<span data-ttu-id="b5853-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5853-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5853-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b5853-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b5853-126">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b5853-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5853-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5853-127">Remarks</span></span>  
 <span data-ttu-id="b5853-128">Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b5853-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="b5853-129">Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="b5853-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5853-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5853-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
