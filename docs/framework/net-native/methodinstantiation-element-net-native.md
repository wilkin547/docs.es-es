---
title: <MethodInstantiation>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: f19bd3c20088431bcbbafac298398b82a664bee9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128326"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="8fd99-102">\<MethodInstantiation>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="8fd99-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="8fd99-103">Aplica la directiva de reflexión en tiempo de ejecución a un método genérico construido.</span><span class="sxs-lookup"><span data-stu-id="8fd99-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fd99-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fd99-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8fd99-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8fd99-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8fd99-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fd99-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8fd99-107">Attributes</span></span>  
  
|<span data-ttu-id="8fd99-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8fd99-108">Attribute</span></span>|<span data-ttu-id="8fd99-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="8fd99-109">Attribute type</span></span>|<span data-ttu-id="8fd99-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd99-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="8fd99-111">General</span><span class="sxs-lookup"><span data-stu-id="8fd99-111">General</span></span>|<span data-ttu-id="8fd99-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8fd99-112">Required attribute.</span></span> <span data-ttu-id="8fd99-113">Especifica el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="8fd99-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="8fd99-114">General</span><span class="sxs-lookup"><span data-stu-id="8fd99-114">General</span></span>|<span data-ttu-id="8fd99-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8fd99-115">Optional attribute.</span></span> <span data-ttu-id="8fd99-116">Especifica los parámetros con nombre del método.</span><span class="sxs-lookup"><span data-stu-id="8fd99-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="8fd99-117">Cuando hay varios parámetros con nombre, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="8fd99-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="8fd99-118">El atributo `Signature` se usa para diferenciar los métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="8fd99-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="8fd99-119">General</span><span class="sxs-lookup"><span data-stu-id="8fd99-119">General</span></span>|<span data-ttu-id="8fd99-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8fd99-120">Required attribute.</span></span> <span data-ttu-id="8fd99-121">Especifica los argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="8fd99-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="8fd99-122">Si hay varios argumentos, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="8fd99-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="8fd99-123">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8fd99-123">Reflection</span></span>|<span data-ttu-id="8fd99-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8fd99-124">Optional attribute.</span></span> <span data-ttu-id="8fd99-125">Controla la consulta para obtener información acerca de un método o la enumeración de un método, pero no permite la invocación dinámica en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8fd99-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="8fd99-126">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8fd99-126">Reflection</span></span>|<span data-ttu-id="8fd99-127">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8fd99-127">Optional attribute.</span></span> <span data-ttu-id="8fd99-128">Controla el acceso en tiempo de ejecución a un constructor o un método para habilitar la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="8fd99-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="8fd99-129">Esta directiva garantiza que un miembro se puede invocar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8fd99-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="8fd99-130">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="8fd99-130">Name attribute</span></span>  
  
|<span data-ttu-id="8fd99-131">Value</span><span class="sxs-lookup"><span data-stu-id="8fd99-131">Value</span></span>|<span data-ttu-id="8fd99-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd99-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8fd99-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="8fd99-133">*method_name*</span></span>|<span data-ttu-id="8fd99-134">El nombre del método.</span><span class="sxs-lookup"><span data-stu-id="8fd99-134">The method name.</span></span> <span data-ttu-id="8fd99-135">El tipo del método se define mediante el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="8fd99-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="8fd99-136">Signature (atributo)</span><span class="sxs-lookup"><span data-stu-id="8fd99-136">Signature attribute</span></span>  
  
|<span data-ttu-id="8fd99-137">Value</span><span class="sxs-lookup"><span data-stu-id="8fd99-137">Value</span></span>|<span data-ttu-id="8fd99-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd99-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8fd99-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="8fd99-139">*method_signature*</span></span>|<span data-ttu-id="8fd99-140">Especifica los parámetros con nombre del método.</span><span class="sxs-lookup"><span data-stu-id="8fd99-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="8fd99-141">Si hay varios parámetros, se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="8fd99-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="8fd99-142">Arguments (atributo)</span><span class="sxs-lookup"><span data-stu-id="8fd99-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="8fd99-143">Value</span><span class="sxs-lookup"><span data-stu-id="8fd99-143">Value</span></span>|<span data-ttu-id="8fd99-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd99-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8fd99-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="8fd99-145">*method_arguments*</span></span>|<span data-ttu-id="8fd99-146">Especifica los argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="8fd99-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="8fd99-147">Si hay varios argumentos, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="8fd99-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="8fd99-148">Cada argumento debe contener el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="8fd99-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="8fd99-149">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="8fd99-149">All other attributes</span></span>  
  
|<span data-ttu-id="8fd99-150">Value</span><span class="sxs-lookup"><span data-stu-id="8fd99-150">Value</span></span>|<span data-ttu-id="8fd99-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd99-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8fd99-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="8fd99-152">*policy_setting*</span></span>|<span data-ttu-id="8fd99-153">Configuración que se aplica a este tipo de directiva para el método.</span><span class="sxs-lookup"><span data-stu-id="8fd99-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="8fd99-154">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="8fd99-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="8fd99-155">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="8fd99-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fd99-156">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8fd99-156">Child Elements</span></span>  
 <span data-ttu-id="8fd99-157">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8fd99-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fd99-158">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8fd99-158">Parent Elements</span></span>  
  
|<span data-ttu-id="8fd99-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="8fd99-159">Element</span></span>|<span data-ttu-id="8fd99-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd99-160">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="8fd99-161">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="8fd99-161">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="8fd99-162">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="8fd99-162">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fd99-163">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fd99-163">Remarks</span></span>  
 <span data-ttu-id="8fd99-164">El elemento `<MethodInstantiation>` invalida la directiva de reflexión en tiempo de ejecución de su correspondiente método genérico abierto.</span><span class="sxs-lookup"><span data-stu-id="8fd99-164">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd99-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8fd99-165">See also</span></span>

- [<span data-ttu-id="8fd99-166">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="8fd99-166">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="8fd99-167">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8fd99-167">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="8fd99-168">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8fd99-168">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="8fd99-169">\<Method>Element</span><span class="sxs-lookup"><span data-stu-id="8fd99-169">\<Method> Element</span></span>](method-element-net-native.md)
