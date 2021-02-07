---
description: 'Más información acerca de: <persistenceProvider>'
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 60ddaf9f26f496bd7d79ccab84f84135e46963d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683559"
---
# \<persistenceProvider>

<span data-ttu-id="8040c-102">Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="8040c-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="8040c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8040c-103">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8040c-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8040c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8040c-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8040c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8040c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="8040c-106">Attributes</span></span>  
  
|<span data-ttu-id="8040c-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="8040c-107">Attribute</span></span>|<span data-ttu-id="8040c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8040c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8040c-109">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="8040c-109">persistenceOperationTimeout</span></span>|<span data-ttu-id="8040c-110">Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="8040c-110">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="8040c-111">El valor predeterminado es "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="8040c-111">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="8040c-112">type</span><span class="sxs-lookup"><span data-stu-id="8040c-112">type</span></span>|<span data-ttu-id="8040c-113">Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="8040c-113">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8040c-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8040c-114">Child Elements</span></span>  

 <span data-ttu-id="8040c-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8040c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8040c-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8040c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8040c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="8040c-117">Element</span></span>|<span data-ttu-id="8040c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8040c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8040c-119">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8040c-119">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8040c-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8040c-120">Remarks</span></span>  

 <span data-ttu-id="8040c-121">Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="8040c-121">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="8040c-122">Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="8040c-122">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8040c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8040c-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
