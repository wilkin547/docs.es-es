---
title: <Event> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: b1cf2239e58839c5026bc375ba04568227881bdd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288104"
---
# <a name="event-element-net-native"></a><span data-ttu-id="0ed88-102">\<Event> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="0ed88-102">\<Event> Element (.NET Native)</span></span>

<span data-ttu-id="0ed88-103">Aplica la directiva de reflexión en tiempo de ejecución a un evento.</span><span class="sxs-lookup"><span data-stu-id="0ed88-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ed88-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ed88-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ed88-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0ed88-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0ed88-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0ed88-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ed88-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="0ed88-107">Attributes</span></span>  
  
|<span data-ttu-id="0ed88-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="0ed88-108">Attribute</span></span>|<span data-ttu-id="0ed88-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="0ed88-109">Attribute type</span></span>|<span data-ttu-id="0ed88-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ed88-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0ed88-111">General</span><span class="sxs-lookup"><span data-stu-id="0ed88-111">General</span></span>|<span data-ttu-id="0ed88-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0ed88-112">Required attribute.</span></span> <span data-ttu-id="0ed88-113">Especifica el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="0ed88-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="0ed88-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0ed88-114">Reflection</span></span>|<span data-ttu-id="0ed88-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0ed88-115">Optional attribute.</span></span> <span data-ttu-id="0ed88-116">Controla la consulta para obtener información acerca del evento o la enumeración del evento, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0ed88-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="0ed88-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0ed88-117">Reflection</span></span>|<span data-ttu-id="0ed88-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0ed88-118">Optional attribute.</span></span> <span data-ttu-id="0ed88-119">Controla el acceso en tiempo de ejecución al evento para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="0ed88-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="0ed88-120">Esta directiva garantiza que un evento se puede controlar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0ed88-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0ed88-121">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="0ed88-121">Name attribute</span></span>  
  
|<span data-ttu-id="0ed88-122">Valor</span><span class="sxs-lookup"><span data-stu-id="0ed88-122">Value</span></span>|<span data-ttu-id="0ed88-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ed88-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0ed88-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="0ed88-124">*method_name*</span></span>|<span data-ttu-id="0ed88-125">Nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="0ed88-125">The event name.</span></span> <span data-ttu-id="0ed88-126">El tipo del evento se define mediante el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="0ed88-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0ed88-127">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="0ed88-127">All other attributes</span></span>  
  
|<span data-ttu-id="0ed88-128">Valor</span><span class="sxs-lookup"><span data-stu-id="0ed88-128">Value</span></span>|<span data-ttu-id="0ed88-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ed88-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0ed88-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0ed88-130">*policy_setting*</span></span>|<span data-ttu-id="0ed88-131">Configuración que se va a aplicar a este tipo de directiva para el evento.</span><span class="sxs-lookup"><span data-stu-id="0ed88-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="0ed88-132">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="0ed88-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="0ed88-133">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="0ed88-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ed88-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0ed88-134">Child Elements</span></span>  

 <span data-ttu-id="0ed88-135">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0ed88-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ed88-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0ed88-136">Parent Elements</span></span>  
  
|<span data-ttu-id="0ed88-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ed88-137">Element</span></span>|<span data-ttu-id="0ed88-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ed88-138">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="0ed88-139">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="0ed88-139">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="0ed88-140">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="0ed88-140">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ed88-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ed88-141">Remarks</span></span>  

 <span data-ttu-id="0ed88-142">Si la directiva de un evento no se define explícitamente, heredará la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="0ed88-142">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed88-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ed88-143">See also</span></span>

- [<span data-ttu-id="0ed88-144">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="0ed88-144">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0ed88-145">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0ed88-145">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="0ed88-146">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0ed88-146">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
