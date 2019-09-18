---
title: Elementos de directivas en tiempo de ejecución
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 062f13ad92f37bb7ae29ed34dcf88f99f98e7612
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049264"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="7876a-102">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7876a-102">Runtime Directive Elements</span></span>
<span data-ttu-id="7876a-103">El formato del archivo de directivas de tiempo de ejecución (rd.xml) es compatible con los siguientes elementos de directiva de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7876a-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="7876a-104">Vea [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)) para obtener una representación jerárquica.</span><span class="sxs-lookup"><span data-stu-id="7876a-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="7876a-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="7876a-105">\<Application></span></span>](application-element-net-native.md)  
 <span data-ttu-id="7876a-106">Aplica la directiva de reflexión en tiempo de ejecución a todos los tipos utilizados por la aplicación y sirve como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7876a-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="7876a-107">Se trata de un elemento secundario del elemento [\<Directives>](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="7876a-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="7876a-108">\<Assembly></span></span>](assembly-element-net-native.md)  
 <span data-ttu-id="7876a-109">Aplica la directiva de tiempo de ejecución a todos los tipos de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7876a-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="7876a-110">Se trata de un elemento secundario de los elementos [\<Application>](application-element-net-native.md) y [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-110">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="7876a-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="7876a-111">\<AttributeImplies></span></span>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="7876a-112">Si la directiva [\<Type>](type-element-net-native.md) que contiene es un atributo, aplica la directiva en tiempo de ejecución a los elementos de código a los que se les aplica dicho atributo.</span><span class="sxs-lookup"><span data-stu-id="7876a-112">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="7876a-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="7876a-113">\<Directives></span></span>](directives-element-net-native.md)  
 <span data-ttu-id="7876a-114">Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7876a-114">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="7876a-115">Sus elementos secundarios son [\<Application>](application-element-net-native.md) y [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-115">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="7876a-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="7876a-116">\<Event></span></span>](event-element-net-native.md)  
 <span data-ttu-id="7876a-117">Aplica la directiva de tiempo de ejecución a un evento.</span><span class="sxs-lookup"><span data-stu-id="7876a-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="7876a-118">Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-118">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="7876a-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="7876a-119">\<Field></span></span>](field-element-net-native.md)  
 <span data-ttu-id="7876a-120">Aplica la directiva de tiempo de ejecución a un campo.</span><span class="sxs-lookup"><span data-stu-id="7876a-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="7876a-121">Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="7876a-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="7876a-122">\<GenericParameter></span></span>](genericparameter-element-net-native.md)  
 <span data-ttu-id="7876a-123">Aplica la directiva de tiempo de ejecución al tipo de parámetro de un método o tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="7876a-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="7876a-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="7876a-124">\<ImpliesType></span></span>](impliestype-element-net-native.md)  
 <span data-ttu-id="7876a-125">Aplica la directiva de tiempo de ejecución a un tipo, si dicha directiva se ha aplicado al tipo contenedor o al método.</span><span class="sxs-lookup"><span data-stu-id="7876a-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="7876a-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="7876a-126">\<Library></span></span>](library-element-net-native.md)  
 <span data-ttu-id="7876a-127">Aplica la directiva de tiempo de ejecución a todos los tipos de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7876a-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="7876a-128">Se trata de un elemento secundario de los elementos [\<Application>](application-element-net-native.md) y [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-128">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="7876a-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="7876a-129">\<Method></span></span>](method-element-net-native.md)  
 <span data-ttu-id="7876a-130">Aplica la directiva de tiempo de ejecución a un método.</span><span class="sxs-lookup"><span data-stu-id="7876a-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="7876a-131">Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-131">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="7876a-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="7876a-132">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="7876a-133">Aplica la directiva de tiempo de ejecución a un método genérico construido.</span><span class="sxs-lookup"><span data-stu-id="7876a-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="7876a-134">Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-134">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="7876a-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="7876a-135">\<Namespace></span></span>](namespace-element-net-native.md)  
 <span data-ttu-id="7876a-136">Aplica la directiva de tiempo de ejecución a todos los tipos de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7876a-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="7876a-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="7876a-137">\<Parameter></span></span>](parameter-element-net-native.md)  
 <span data-ttu-id="7876a-138">Aplica la directiva de tiempo de ejecución al tipo del argumento que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="7876a-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="7876a-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="7876a-139">\<Property></span></span>](property-element-net-native.md)  
 <span data-ttu-id="7876a-140">Aplica la directiva de tiempo de ejecución a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="7876a-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="7876a-141">Se trata de un elemento secundario de los elementos [\<Type>](type-element-net-native.md) y [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7876a-141">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="7876a-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="7876a-142">\<Subtypes></span></span>](subtypes-element-net-native.md)  
 <span data-ttu-id="7876a-143">Aplica la directiva en tiempo de ejecución a todas las clases heredadas del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="7876a-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="7876a-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="7876a-144">\<Type></span></span>](type-element-net-native.md)  
 <span data-ttu-id="7876a-145">Aplica la directiva de tiempo de ejecución a un tipo.</span><span class="sxs-lookup"><span data-stu-id="7876a-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="7876a-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="7876a-146">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="7876a-147">Aplica la directiva de tiempo de ejecución a un tipo genérico construido.</span><span class="sxs-lookup"><span data-stu-id="7876a-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="7876a-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="7876a-148">\<TypeParameter></span></span>](typeparameter-element-net-native.md)  
 <span data-ttu-id="7876a-149">Aplica la directiva de tiempo de ejecución al tipo representado por un argumento <xref:System.Type> que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="7876a-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7876a-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="7876a-150">See also</span></span>

- [<span data-ttu-id="7876a-151">Referencia del archivo de configuración rd.xml</span><span class="sxs-lookup"><span data-stu-id="7876a-151">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
