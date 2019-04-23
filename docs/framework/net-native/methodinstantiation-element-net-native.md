---
title: <MethodInstantiation> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae15e6d61267feb0388170ee27dcd939035329b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121698"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="c82c7-102">\<MethodInstantiation > elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="c82c7-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="c82c7-103">Aplica la directiva de reflexión en tiempo de ejecución a un método genérico construido.</span><span class="sxs-lookup"><span data-stu-id="c82c7-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c82c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c82c7-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c82c7-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c82c7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c82c7-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c82c7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c82c7-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c82c7-107">Attributes</span></span>  
  
|<span data-ttu-id="c82c7-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c82c7-108">Attribute</span></span>|<span data-ttu-id="c82c7-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="c82c7-109">Attribute type</span></span>|<span data-ttu-id="c82c7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c82c7-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="c82c7-111">General</span><span class="sxs-lookup"><span data-stu-id="c82c7-111">General</span></span>|<span data-ttu-id="c82c7-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c82c7-112">Required attribute.</span></span> <span data-ttu-id="c82c7-113">Especifica el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="c82c7-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="c82c7-114">General</span><span class="sxs-lookup"><span data-stu-id="c82c7-114">General</span></span>|<span data-ttu-id="c82c7-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c82c7-115">Optional attribute.</span></span> <span data-ttu-id="c82c7-116">Especifica los parámetros con nombre del método.</span><span class="sxs-lookup"><span data-stu-id="c82c7-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="c82c7-117">Cuando hay varios parámetros con nombre, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="c82c7-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="c82c7-118">El atributo `Signature` se usa para diferenciar los métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="c82c7-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="c82c7-119">General</span><span class="sxs-lookup"><span data-stu-id="c82c7-119">General</span></span>|<span data-ttu-id="c82c7-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c82c7-120">Required attribute.</span></span> <span data-ttu-id="c82c7-121">Especifica los argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="c82c7-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="c82c7-122">Si hay varios argumentos, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="c82c7-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="c82c7-123">Reflexión</span><span class="sxs-lookup"><span data-stu-id="c82c7-123">Reflection</span></span>|<span data-ttu-id="c82c7-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c82c7-124">Optional attribute.</span></span> <span data-ttu-id="c82c7-125">Controla la consulta para obtener información acerca de un método o la enumeración de un método, pero no permite la invocación dinámica en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c82c7-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="c82c7-126">Reflexión</span><span class="sxs-lookup"><span data-stu-id="c82c7-126">Reflection</span></span>|<span data-ttu-id="c82c7-127">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="c82c7-127">Optional attribute.</span></span> <span data-ttu-id="c82c7-128">Controla el acceso en tiempo de ejecución a un constructor o un método para habilitar la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="c82c7-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="c82c7-129">Esta directiva garantiza que un miembro se puede invocar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c82c7-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="c82c7-130">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="c82c7-130">Name attribute</span></span>  
  
|<span data-ttu-id="c82c7-131">Valor</span><span class="sxs-lookup"><span data-stu-id="c82c7-131">Value</span></span>|<span data-ttu-id="c82c7-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="c82c7-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c82c7-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="c82c7-133">*method_name*</span></span>|<span data-ttu-id="c82c7-134">El nombre del método.</span><span class="sxs-lookup"><span data-stu-id="c82c7-134">The method name.</span></span> <span data-ttu-id="c82c7-135">El tipo del método se define mediante el elemento primario [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="c82c7-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="c82c7-136">Signature (atributo)</span><span class="sxs-lookup"><span data-stu-id="c82c7-136">Signature attribute</span></span>  
  
|<span data-ttu-id="c82c7-137">Valor</span><span class="sxs-lookup"><span data-stu-id="c82c7-137">Value</span></span>|<span data-ttu-id="c82c7-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="c82c7-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c82c7-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="c82c7-139">*method_signature*</span></span>|<span data-ttu-id="c82c7-140">Especifica los parámetros con nombre del método.</span><span class="sxs-lookup"><span data-stu-id="c82c7-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="c82c7-141">Si hay varios parámetros, se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="c82c7-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="c82c7-142">Arguments (atributo)</span><span class="sxs-lookup"><span data-stu-id="c82c7-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="c82c7-143">Valor</span><span class="sxs-lookup"><span data-stu-id="c82c7-143">Value</span></span>|<span data-ttu-id="c82c7-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="c82c7-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c82c7-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="c82c7-145">*method_arguments*</span></span>|<span data-ttu-id="c82c7-146">Especifica los argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="c82c7-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="c82c7-147">Si hay varios argumentos, se separan mediante coma.</span><span class="sxs-lookup"><span data-stu-id="c82c7-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="c82c7-148">Cada argumento debe contener el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="c82c7-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="c82c7-149">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="c82c7-149">All other attributes</span></span>  
  
|<span data-ttu-id="c82c7-150">Valor</span><span class="sxs-lookup"><span data-stu-id="c82c7-150">Value</span></span>|<span data-ttu-id="c82c7-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="c82c7-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c82c7-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="c82c7-152">*policy_setting*</span></span>|<span data-ttu-id="c82c7-153">Configuración que se aplica a este tipo de directiva para el método.</span><span class="sxs-lookup"><span data-stu-id="c82c7-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="c82c7-154">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="c82c7-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="c82c7-155">Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="c82c7-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c82c7-156">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c82c7-156">Child Elements</span></span>  
 <span data-ttu-id="c82c7-157">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c82c7-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c82c7-158">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c82c7-158">Parent Elements</span></span>  
  
|<span data-ttu-id="c82c7-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="c82c7-159">Element</span></span>|<span data-ttu-id="c82c7-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="c82c7-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c82c7-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="c82c7-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="c82c7-162">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c82c7-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="c82c7-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="c82c7-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="c82c7-164">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c82c7-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c82c7-165">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c82c7-165">Remarks</span></span>  
 <span data-ttu-id="c82c7-166">El elemento `<MethodInstantiation>` invalida la directiva de reflexión en tiempo de ejecución de su correspondiente método genérico abierto.</span><span class="sxs-lookup"><span data-stu-id="c82c7-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c82c7-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="c82c7-167">See also</span></span>

- [<span data-ttu-id="c82c7-168">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="c82c7-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c82c7-169">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="c82c7-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- <span data-ttu-id="c82c7-170">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="c82c7-170">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>
- [<span data-ttu-id="c82c7-171">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="c82c7-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
