---
title: Elemento &lt;Event&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11cc51eb12edc36331bd7a2d3bb1ecfdc267985e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536755"
---
# <a name="lteventgt-element-net-native"></a><span data-ttu-id="8677e-102">Elemento &lt;Event&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="8677e-102">&lt;Event&gt; Element (.NET Native)</span></span>
<span data-ttu-id="8677e-103">Aplica la directiva de reflexión en tiempo de ejecución a un evento.</span><span class="sxs-lookup"><span data-stu-id="8677e-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8677e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8677e-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8677e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8677e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8677e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8677e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8677e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8677e-107">Attributes</span></span>  
  
|<span data-ttu-id="8677e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8677e-108">Attribute</span></span>|<span data-ttu-id="8677e-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="8677e-109">Attribute type</span></span>|<span data-ttu-id="8677e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8677e-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="8677e-111">General</span><span class="sxs-lookup"><span data-stu-id="8677e-111">General</span></span>|<span data-ttu-id="8677e-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8677e-112">Required attribute.</span></span> <span data-ttu-id="8677e-113">Especifica el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="8677e-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="8677e-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8677e-114">Reflection</span></span>|<span data-ttu-id="8677e-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8677e-115">Optional attribute.</span></span> <span data-ttu-id="8677e-116">Controla la consulta para obtener información acerca del evento o la enumeración del evento, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8677e-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="8677e-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8677e-117">Reflection</span></span>|<span data-ttu-id="8677e-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8677e-118">Optional attribute.</span></span> <span data-ttu-id="8677e-119">Controla el acceso en tiempo de ejecución al evento para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="8677e-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="8677e-120">Esta directiva garantiza que un evento se puede controlar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8677e-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="8677e-121">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="8677e-121">Name attribute</span></span>  
  
|<span data-ttu-id="8677e-122">Valor</span><span class="sxs-lookup"><span data-stu-id="8677e-122">Value</span></span>|<span data-ttu-id="8677e-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="8677e-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8677e-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="8677e-124">*method_name*</span></span>|<span data-ttu-id="8677e-125">Nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="8677e-125">The event name.</span></span> <span data-ttu-id="8677e-126">El tipo del evento se define mediante el elemento primario [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="8677e-126">The type of the event is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="8677e-127">Todos los demás atributos</span><span class="sxs-lookup"><span data-stu-id="8677e-127">All other attributes</span></span>  
  
|<span data-ttu-id="8677e-128">Valor</span><span class="sxs-lookup"><span data-stu-id="8677e-128">Value</span></span>|<span data-ttu-id="8677e-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="8677e-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8677e-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="8677e-130">*policy_setting*</span></span>|<span data-ttu-id="8677e-131">Configuración que se va a aplicar a este tipo de directiva para el evento.</span><span class="sxs-lookup"><span data-stu-id="8677e-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="8677e-132">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="8677e-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="8677e-133">Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="8677e-133">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8677e-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8677e-134">Child Elements</span></span>  
 <span data-ttu-id="8677e-135">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8677e-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8677e-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8677e-136">Parent Elements</span></span>  
  
|<span data-ttu-id="8677e-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="8677e-137">Element</span></span>|<span data-ttu-id="8677e-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="8677e-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8677e-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="8677e-139">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="8677e-140">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="8677e-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="8677e-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="8677e-141">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="8677e-142">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="8677e-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8677e-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8677e-143">Remarks</span></span>  
 <span data-ttu-id="8677e-144">Si la directiva de un evento no se define explícitamente, heredará la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="8677e-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8677e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="8677e-145">See also</span></span>
- [<span data-ttu-id="8677e-146">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="8677e-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="8677e-147">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="8677e-147">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- <span data-ttu-id="8677e-148">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="8677e-148">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>
