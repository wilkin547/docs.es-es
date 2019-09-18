---
title: <Event>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fb0245c50677da0397ba9c4918f171dcb217ba6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049844"
---
# <a name="event-element-net-native"></a><span data-ttu-id="c85b7-102">\<Elemento Event > (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="c85b7-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="c85b7-103">Aplica la directiva de reflexión en tiempo de ejecución a un evento.</span><span class="sxs-lookup"><span data-stu-id="c85b7-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c85b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c85b7-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c85b7-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c85b7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c85b7-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c85b7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c85b7-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c85b7-107">Attributes</span></span>  
  
|<span data-ttu-id="c85b7-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c85b7-108">Attribute</span></span>|<span data-ttu-id="c85b7-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="c85b7-109">Attribute type</span></span>|<span data-ttu-id="c85b7-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c85b7-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="c85b7-111">General</span><span class="sxs-lookup"><span data-stu-id="c85b7-111">General</span></span>|<span data-ttu-id="c85b7-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c85b7-112">Required attribute.</span></span> <span data-ttu-id="c85b7-113">Especifica el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="c85b7-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="c85b7-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="c85b7-114">Reflection</span></span>|<span data-ttu-id="c85b7-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c85b7-115">Optional attribute.</span></span> <span data-ttu-id="c85b7-116">Controla la consulta para obtener información acerca del evento o la enumeración del evento, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c85b7-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="c85b7-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="c85b7-117">Reflection</span></span>|<span data-ttu-id="c85b7-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c85b7-118">Optional attribute.</span></span> <span data-ttu-id="c85b7-119">Controla el acceso en tiempo de ejecución al evento para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="c85b7-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="c85b7-120">Esta directiva garantiza que un evento se puede controlar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c85b7-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="c85b7-121">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="c85b7-121">Name attribute</span></span>  
  
|<span data-ttu-id="c85b7-122">Valor</span><span class="sxs-lookup"><span data-stu-id="c85b7-122">Value</span></span>|<span data-ttu-id="c85b7-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c85b7-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c85b7-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="c85b7-124">*method_name*</span></span>|<span data-ttu-id="c85b7-125">Nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="c85b7-125">The event name.</span></span> <span data-ttu-id="c85b7-126">El tipo del evento se define mediante el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="c85b7-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="c85b7-127">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="c85b7-127">All other attributes</span></span>  
  
|<span data-ttu-id="c85b7-128">Valor</span><span class="sxs-lookup"><span data-stu-id="c85b7-128">Value</span></span>|<span data-ttu-id="c85b7-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c85b7-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c85b7-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="c85b7-130">*policy_setting*</span></span>|<span data-ttu-id="c85b7-131">Configuración que se va a aplicar a este tipo de directiva para el evento.</span><span class="sxs-lookup"><span data-stu-id="c85b7-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="c85b7-132">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="c85b7-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="c85b7-133">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="c85b7-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c85b7-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c85b7-134">Child Elements</span></span>  
 <span data-ttu-id="c85b7-135">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c85b7-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c85b7-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c85b7-136">Parent Elements</span></span>  
  
|<span data-ttu-id="c85b7-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="c85b7-137">Element</span></span>|<span data-ttu-id="c85b7-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c85b7-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c85b7-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="c85b7-139">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="c85b7-140">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c85b7-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="c85b7-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="c85b7-141">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="c85b7-142">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c85b7-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c85b7-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c85b7-143">Remarks</span></span>  
 <span data-ttu-id="c85b7-144">Si la directiva de un evento no se define explícitamente, heredará la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="c85b7-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85b7-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="c85b7-145">See also</span></span>

- [<span data-ttu-id="c85b7-146">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="c85b7-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c85b7-147">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="c85b7-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- <span data-ttu-id="c85b7-148">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="c85b7-148">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md)</span></span>
