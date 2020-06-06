---
title: Elementos de directivas en tiempo de ejecución
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128168"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="26da7-102">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="26da7-102">Runtime Directive Elements</span></span>
<span data-ttu-id="26da7-103">El formato del archivo de directivas de tiempo de ejecución (rd.xml) es compatible con los siguientes elementos de directiva de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="26da7-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="26da7-104">Vea [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)) para obtener una representación jerárquica.</span><span class="sxs-lookup"><span data-stu-id="26da7-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [\<Application>](application-element-net-native.md)  
 <span data-ttu-id="26da7-105">Aplica la directiva de reflexión en tiempo de ejecución a todos los tipos utilizados por la aplicación y sirve como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="26da7-105">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="26da7-106">Es un elemento secundario del [\<Directives>](directives-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="26da7-106">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [\<Assembly>](assembly-element-net-native.md)  
 <span data-ttu-id="26da7-107">Aplica la directiva de tiempo de ejecución a todos los tipos de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="26da7-107">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="26da7-108">Se trata de un elemento secundario de los [\<Application>](application-element-net-native.md) [\<Library>](library-element-net-native.md) elementos y.</span><span class="sxs-lookup"><span data-stu-id="26da7-108">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="26da7-109">Si su Directiva contenedora [\<Type>](type-element-net-native.md) es un atributo, aplica la Directiva en tiempo de ejecución a los elementos de código a los que se aplica ese atributo.</span><span class="sxs-lookup"><span data-stu-id="26da7-109">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [\<Directives>](directives-element-net-native.md)  
 <span data-ttu-id="26da7-110">Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.</span><span class="sxs-lookup"><span data-stu-id="26da7-110">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="26da7-111">Sus elementos secundarios son [\<Application>](application-element-net-native.md) y [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="26da7-111">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [\<Event>](event-element-net-native.md)  
 <span data-ttu-id="26da7-112">Aplica la directiva de tiempo de ejecución a un evento.</span><span class="sxs-lookup"><span data-stu-id="26da7-112">Applies runtime policy to an event.</span></span> <span data-ttu-id="26da7-113">Se trata de un elemento secundario de los [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementos y.</span><span class="sxs-lookup"><span data-stu-id="26da7-113">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Field>](field-element-net-native.md)  
 <span data-ttu-id="26da7-114">Aplica la directiva de tiempo de ejecución a un campo.</span><span class="sxs-lookup"><span data-stu-id="26da7-114">Applies runtime policy to a field.</span></span> <span data-ttu-id="26da7-115">Se trata de un elemento secundario de los [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementos y.</span><span class="sxs-lookup"><span data-stu-id="26da7-115">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 <span data-ttu-id="26da7-116">Aplica la directiva de tiempo de ejecución al tipo de parámetro de un método o tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="26da7-116">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 <span data-ttu-id="26da7-117">Aplica la directiva de tiempo de ejecución a un tipo, si dicha directiva se ha aplicado al tipo contenedor o al método.</span><span class="sxs-lookup"><span data-stu-id="26da7-117">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [\<Library>](library-element-net-native.md)  
 <span data-ttu-id="26da7-118">Aplica la directiva de tiempo de ejecución a todos los tipos de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="26da7-118">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="26da7-119">Se trata de un elemento secundario de los [\<Application>](application-element-net-native.md) [\<Library>](library-element-net-native.md) elementos y.</span><span class="sxs-lookup"><span data-stu-id="26da7-119">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<Method>](method-element-net-native.md)  
 <span data-ttu-id="26da7-120">Aplica la directiva de tiempo de ejecución a un método.</span><span class="sxs-lookup"><span data-stu-id="26da7-120">Applies runtime policy to a method.</span></span> <span data-ttu-id="26da7-121">Se trata de un elemento secundario de los [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementos y.</span><span class="sxs-lookup"><span data-stu-id="26da7-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="26da7-122">Aplica la directiva de tiempo de ejecución a un método genérico construido.</span><span class="sxs-lookup"><span data-stu-id="26da7-122">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="26da7-123">Se trata de un elemento secundario de los [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementos y.</span><span class="sxs-lookup"><span data-stu-id="26da7-123">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Namespace>](namespace-element-net-native.md)  
 <span data-ttu-id="26da7-124">Aplica la directiva de tiempo de ejecución a todos los tipos de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="26da7-124">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [\<Parameter>](parameter-element-net-native.md)  
 <span data-ttu-id="26da7-125">Aplica la directiva de tiempo de ejecución al tipo del argumento que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="26da7-125">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [\<Property>](property-element-net-native.md)  
 <span data-ttu-id="26da7-126">Aplica la directiva de tiempo de ejecución a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="26da7-126">Applies runtime policy to a property.</span></span> <span data-ttu-id="26da7-127">Se trata de un elemento secundario de los [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementos y.</span><span class="sxs-lookup"><span data-stu-id="26da7-127">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 <span data-ttu-id="26da7-128">Aplica la directiva en tiempo de ejecución a todas las clases heredadas del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="26da7-128">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [\<Type>](type-element-net-native.md)  
 <span data-ttu-id="26da7-129">Aplica la directiva de tiempo de ejecución a un tipo.</span><span class="sxs-lookup"><span data-stu-id="26da7-129">Applies runtime policy to a type.</span></span>  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="26da7-130">Aplica la directiva de tiempo de ejecución a un tipo genérico construido.</span><span class="sxs-lookup"><span data-stu-id="26da7-130">Applies runtime policy to a constructed generic type.</span></span>  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 <span data-ttu-id="26da7-131">Aplica la directiva de tiempo de ejecución al tipo representado por un argumento <xref:System.Type> que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="26da7-131">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26da7-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26da7-132">See also</span></span>

- [<span data-ttu-id="26da7-133">Referencia del archivo de configuración rd.xml</span><span class="sxs-lookup"><span data-stu-id="26da7-133">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
