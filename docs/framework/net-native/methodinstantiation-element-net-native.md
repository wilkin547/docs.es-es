---
description: 'Más información sobre: <MethodInstantiation> elemento (.net Native)'
title: <MethodInstantiation> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: 985d522a559dbbce936a2f29a9983c89ebd18a48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747496"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="1b310-103">\<MethodInstantiation> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="1b310-103">\<MethodInstantiation> Element (.NET Native)</span></span>

<span data-ttu-id="1b310-104">Aplica la directiva de reflexión en tiempo de ejecución a un método genérico construido.</span><span class="sxs-lookup"><span data-stu-id="1b310-104">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b310-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b310-105">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b310-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1b310-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1b310-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1b310-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b310-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1b310-108">Attributes</span></span>  
  
|<span data-ttu-id="1b310-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="1b310-109">Attribute</span></span>|<span data-ttu-id="1b310-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="1b310-110">Attribute type</span></span>|<span data-ttu-id="1b310-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b310-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="1b310-112">General</span><span class="sxs-lookup"><span data-stu-id="1b310-112">General</span></span>|<span data-ttu-id="1b310-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="1b310-113">Required attribute.</span></span> <span data-ttu-id="1b310-114">Especifica el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="1b310-114">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="1b310-115">General</span><span class="sxs-lookup"><span data-stu-id="1b310-115">General</span></span>|<span data-ttu-id="1b310-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1b310-116">Optional attribute.</span></span> <span data-ttu-id="1b310-117">Especifica los parámetros con nombre del método.</span><span class="sxs-lookup"><span data-stu-id="1b310-117">Specifies named parameters of the method.</span></span> <span data-ttu-id="1b310-118">Cuando hay varios parámetros con nombre, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="1b310-118">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="1b310-119">El atributo `Signature` se usa para diferenciar los métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="1b310-119">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="1b310-120">General</span><span class="sxs-lookup"><span data-stu-id="1b310-120">General</span></span>|<span data-ttu-id="1b310-121">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="1b310-121">Required attribute.</span></span> <span data-ttu-id="1b310-122">Especifica los argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="1b310-122">Specifies the generic type arguments.</span></span> <span data-ttu-id="1b310-123">Si hay varios argumentos, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="1b310-123">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="1b310-124">Reflexión</span><span class="sxs-lookup"><span data-stu-id="1b310-124">Reflection</span></span>|<span data-ttu-id="1b310-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1b310-125">Optional attribute.</span></span> <span data-ttu-id="1b310-126">Controla la consulta para obtener información acerca de un método o la enumeración de un método, pero no permite la invocación dinámica en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1b310-126">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="1b310-127">Reflexión</span><span class="sxs-lookup"><span data-stu-id="1b310-127">Reflection</span></span>|<span data-ttu-id="1b310-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1b310-128">Optional attribute.</span></span> <span data-ttu-id="1b310-129">Controla el acceso en tiempo de ejecución a un constructor o un método para habilitar la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="1b310-129">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="1b310-130">Esta directiva garantiza que un miembro se puede invocar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1b310-130">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="1b310-131">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="1b310-131">Name attribute</span></span>  
  
|<span data-ttu-id="1b310-132">Value</span><span class="sxs-lookup"><span data-stu-id="1b310-132">Value</span></span>|<span data-ttu-id="1b310-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b310-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b310-134">*method_name*</span><span class="sxs-lookup"><span data-stu-id="1b310-134">*method_name*</span></span>|<span data-ttu-id="1b310-135">El nombre del método.</span><span class="sxs-lookup"><span data-stu-id="1b310-135">The method name.</span></span> <span data-ttu-id="1b310-136">El tipo del método se define mediante el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="1b310-136">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="1b310-137">Signature (atributo)</span><span class="sxs-lookup"><span data-stu-id="1b310-137">Signature attribute</span></span>  
  
|<span data-ttu-id="1b310-138">Value</span><span class="sxs-lookup"><span data-stu-id="1b310-138">Value</span></span>|<span data-ttu-id="1b310-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b310-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b310-140">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="1b310-140">*method_signature*</span></span>|<span data-ttu-id="1b310-141">Especifica los parámetros con nombre del método.</span><span class="sxs-lookup"><span data-stu-id="1b310-141">Specifies the named parameters of the method.</span></span> <span data-ttu-id="1b310-142">Si hay varios parámetros, se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="1b310-142">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="1b310-143">Arguments (atributo)</span><span class="sxs-lookup"><span data-stu-id="1b310-143">Arguments attribute</span></span>  
  
|<span data-ttu-id="1b310-144">Value</span><span class="sxs-lookup"><span data-stu-id="1b310-144">Value</span></span>|<span data-ttu-id="1b310-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b310-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b310-146">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="1b310-146">*method_arguments*</span></span>|<span data-ttu-id="1b310-147">Especifica los argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="1b310-147">Specifies the generic type arguments.</span></span> <span data-ttu-id="1b310-148">Si hay varios argumentos, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="1b310-148">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="1b310-149">Cada argumento debe contener el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="1b310-149">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="1b310-150">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="1b310-150">All other attributes</span></span>  
  
|<span data-ttu-id="1b310-151">Value</span><span class="sxs-lookup"><span data-stu-id="1b310-151">Value</span></span>|<span data-ttu-id="1b310-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b310-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b310-153">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="1b310-153">*policy_setting*</span></span>|<span data-ttu-id="1b310-154">Configuración que se aplica a este tipo de directiva para el método.</span><span class="sxs-lookup"><span data-stu-id="1b310-154">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="1b310-155">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="1b310-155">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="1b310-156">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="1b310-156">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b310-157">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1b310-157">Child Elements</span></span>  

 <span data-ttu-id="1b310-158">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1b310-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b310-159">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1b310-159">Parent Elements</span></span>  
  
|<span data-ttu-id="1b310-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b310-160">Element</span></span>|<span data-ttu-id="1b310-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b310-161">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="1b310-162">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="1b310-162">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="1b310-163">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="1b310-163">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b310-164">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1b310-164">Remarks</span></span>  

 <span data-ttu-id="1b310-165">El elemento `<MethodInstantiation>` invalida la directiva de reflexión en tiempo de ejecución de su correspondiente método genérico abierto.</span><span class="sxs-lookup"><span data-stu-id="1b310-165">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b310-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b310-166">See also</span></span>

- [<span data-ttu-id="1b310-167">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="1b310-167">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="1b310-168">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1b310-168">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="1b310-169">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1b310-169">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="1b310-170">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="1b310-170">\<Method> Element</span></span>](method-element-net-native.md)
