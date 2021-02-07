---
description: 'Más información sobre: <Event> elemento (.net Native)'
title: <Event> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 16ef4376e5953da514598bd7cdcbe0c196ee4da5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747886"
---
# <a name="event-element-net-native"></a><span data-ttu-id="b7a51-103">\<Event> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="b7a51-103">\<Event> Element (.NET Native)</span></span>

<span data-ttu-id="b7a51-104">Aplica la directiva de reflexión en tiempo de ejecución a un evento.</span><span class="sxs-lookup"><span data-stu-id="b7a51-104">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7a51-105">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7a51-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b7a51-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b7a51-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b7a51-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7a51-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7a51-108">Attributes</span></span>  
  
|<span data-ttu-id="b7a51-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="b7a51-109">Attribute</span></span>|<span data-ttu-id="b7a51-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="b7a51-110">Attribute type</span></span>|<span data-ttu-id="b7a51-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7a51-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b7a51-112">General</span><span class="sxs-lookup"><span data-stu-id="b7a51-112">General</span></span>|<span data-ttu-id="b7a51-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b7a51-113">Required attribute.</span></span> <span data-ttu-id="b7a51-114">Especifica el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="b7a51-114">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="b7a51-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="b7a51-115">Reflection</span></span>|<span data-ttu-id="b7a51-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="b7a51-116">Optional attribute.</span></span> <span data-ttu-id="b7a51-117">Controla la consulta para obtener información acerca del evento o la enumeración del evento, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7a51-117">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="b7a51-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="b7a51-118">Reflection</span></span>|<span data-ttu-id="b7a51-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="b7a51-119">Optional attribute.</span></span> <span data-ttu-id="b7a51-120">Controla el acceso en tiempo de ejecución al evento para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="b7a51-120">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="b7a51-121">Esta directiva garantiza que un evento se puede controlar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7a51-121">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b7a51-122">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="b7a51-122">Name attribute</span></span>  
  
|<span data-ttu-id="b7a51-123">Value</span><span class="sxs-lookup"><span data-stu-id="b7a51-123">Value</span></span>|<span data-ttu-id="b7a51-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7a51-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7a51-125">*method_name*</span><span class="sxs-lookup"><span data-stu-id="b7a51-125">*method_name*</span></span>|<span data-ttu-id="b7a51-126">Nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="b7a51-126">The event name.</span></span> <span data-ttu-id="b7a51-127">El tipo del evento se define mediante el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="b7a51-127">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b7a51-128">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="b7a51-128">All other attributes</span></span>  
  
|<span data-ttu-id="b7a51-129">Value</span><span class="sxs-lookup"><span data-stu-id="b7a51-129">Value</span></span>|<span data-ttu-id="b7a51-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7a51-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7a51-131">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b7a51-131">*policy_setting*</span></span>|<span data-ttu-id="b7a51-132">Configuración que se va a aplicar a este tipo de directiva para el evento.</span><span class="sxs-lookup"><span data-stu-id="b7a51-132">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="b7a51-133">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="b7a51-133">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="b7a51-134">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="b7a51-134">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7a51-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7a51-135">Child Elements</span></span>  

 <span data-ttu-id="b7a51-136">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b7a51-136">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7a51-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7a51-137">Parent Elements</span></span>  
  
|<span data-ttu-id="b7a51-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7a51-138">Element</span></span>|<span data-ttu-id="b7a51-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7a51-139">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="b7a51-140">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="b7a51-140">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="b7a51-141">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="b7a51-141">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a51-142">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7a51-142">Remarks</span></span>  

 <span data-ttu-id="b7a51-143">Si la directiva de un evento no se define explícitamente, heredará la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="b7a51-143">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a51-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7a51-144">See also</span></span>

- [<span data-ttu-id="b7a51-145">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="b7a51-145">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b7a51-146">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b7a51-146">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="b7a51-147">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b7a51-147">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
