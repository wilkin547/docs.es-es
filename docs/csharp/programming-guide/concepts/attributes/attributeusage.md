---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61668723"
---
# <a name="attributeusage-c"></a><span data-ttu-id="d5202-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="d5202-102">AttributeUsage (C#)</span></span>

<span data-ttu-id="d5202-103">Determina cómo se puede usar una clase de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5202-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="d5202-104"><xref:System.AttributeUsageAttribute> es un atributo que se aplica a las definiciones de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5202-104"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="d5202-105">El atributo `AttributeUsage` permite controlar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5202-105">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="d5202-106">Los atributos de elementos de programa que se pueden aplicar.</span><span class="sxs-lookup"><span data-stu-id="d5202-106">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="d5202-107">A menos que el uso esté restringido, un atributo se puede aplicar a cualquiera de los siguientes elementos de programa:</span><span class="sxs-lookup"><span data-stu-id="d5202-107">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="d5202-108">ensamblado</span><span class="sxs-lookup"><span data-stu-id="d5202-108">assembly</span></span>
  - <span data-ttu-id="d5202-109">module</span><span class="sxs-lookup"><span data-stu-id="d5202-109">module</span></span>
  - <span data-ttu-id="d5202-110">campo</span><span class="sxs-lookup"><span data-stu-id="d5202-110">field</span></span>
  - <span data-ttu-id="d5202-111">evento</span><span class="sxs-lookup"><span data-stu-id="d5202-111">event</span></span>
  - <span data-ttu-id="d5202-112">método</span><span class="sxs-lookup"><span data-stu-id="d5202-112">method</span></span>
  - <span data-ttu-id="d5202-113">param</span><span class="sxs-lookup"><span data-stu-id="d5202-113">param</span></span>
  - <span data-ttu-id="d5202-114">Propiedad</span><span class="sxs-lookup"><span data-stu-id="d5202-114">property</span></span>
  - <span data-ttu-id="d5202-115">return</span><span class="sxs-lookup"><span data-stu-id="d5202-115">return</span></span>
  - <span data-ttu-id="d5202-116">tipo</span><span class="sxs-lookup"><span data-stu-id="d5202-116">type</span></span>
- <span data-ttu-id="d5202-117">Si un atributo se puede aplicar a un mismo elemento de programa varias veces.</span><span class="sxs-lookup"><span data-stu-id="d5202-117">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="d5202-118">Si las clases derivadas heredan atributos.</span><span class="sxs-lookup"><span data-stu-id="d5202-118">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="d5202-119">La configuración predeterminada se parece al siguiente ejemplo cuando se aplica explícitamente:</span><span class="sxs-lookup"><span data-stu-id="d5202-119">The default settings look like the following example when applied explicitly:</span></span>

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

<span data-ttu-id="d5202-120">En este ejemplo, la clase `NewAttribute` se puede aplicar a cualquier elemento de programación compatible,</span><span class="sxs-lookup"><span data-stu-id="d5202-120">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="d5202-121">pero solamente se puede aplicar una vez a cada entidad.</span><span class="sxs-lookup"><span data-stu-id="d5202-121">But it can be applied only once to each entity.</span></span> <span data-ttu-id="d5202-122">Las clases derivadas heredan el atributo cuando se aplica a una clase base.</span><span class="sxs-lookup"><span data-stu-id="d5202-122">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="d5202-123">Los argumentos <xref:System.AttributeUsageAttribute.AllowMultiple> y <xref:System.AttributeUsageAttribute.Inherited> son opcionales, por lo que el siguiente código tiene el mismo efecto:</span><span class="sxs-lookup"><span data-stu-id="d5202-123">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

<span data-ttu-id="d5202-124">El primer argumento <xref:System.AttributeUsageAttribute> debe ser uno o varios elementos de la enumeración <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="d5202-124">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="d5202-125">Se pueden vincular diversos tipos de destino con el operador OR, como se refleja en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5202-125">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

<span data-ttu-id="d5202-126">A partir de C# 7.3, los atributos se pueden aplicar a la propiedad o el campo de respaldo de una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d5202-126">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="d5202-127">El atributo se aplica a la propiedad, a menos que se indique el especificador `field` en el atributo.</span><span class="sxs-lookup"><span data-stu-id="d5202-127">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="d5202-128">Ambos se muestran en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5202-128">Both are shown in the following example:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

<span data-ttu-id="d5202-129">Si el argumento <xref:System.AttributeUsageAttribute.AllowMultiple> es `true`, el atributo resultante se puede aplicar más de una vez a cada una de las entidades, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5202-129">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

<span data-ttu-id="d5202-130">En este caso, `MultiUseAttribute` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="d5202-130">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="d5202-131">Los dos formatos mostrados para aplicar varios atributos son válidos.</span><span class="sxs-lookup"><span data-stu-id="d5202-131">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="d5202-132">Si <xref:System.AttributeUsageAttribute.Inherited> se establece en `false`, las clases que se derivan de una clase con atributos no heredan el atributo.</span><span class="sxs-lookup"><span data-stu-id="d5202-132">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="d5202-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5202-133">For example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

<span data-ttu-id="d5202-134">En este caso, `NonInheritedAttribute` no se aplica a `DClass` a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="d5202-134">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5202-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5202-135">Remarks</span></span>

<span data-ttu-id="d5202-136">`AttributeUsage` es un atributo de uso único; no se puede aplicar más de una vez a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="d5202-136">The `AttributeUsage` attribute is a single-use attribute--it can't be applied more than once to the same class.</span></span> <span data-ttu-id="d5202-137">`AttributeUsage` es un alias de <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d5202-137">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="d5202-138">Para obtener más información, consulte [Acceder a atributos mediante reflexión (C#)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="d5202-138">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="d5202-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5202-139">Example</span></span>

<span data-ttu-id="d5202-140">En el ejemplo siguiente se muestra el efecto de los argumentos <xref:System.AttributeUsageAttribute.Inherited> y <xref:System.AttributeUsageAttribute.AllowMultiple> en el atributo <xref:System.AttributeUsageAttribute> y cómo se pueden enumerar los atributos personalizados aplicados a una clase.</span><span class="sxs-lookup"><span data-stu-id="d5202-140">The following example demonstrates the effect of the <xref:System.AttributeUsageAttribute.Inherited> and <xref:System.AttributeUsageAttribute.AllowMultiple> arguments to the <xref:System.AttributeUsageAttribute> attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a><span data-ttu-id="d5202-141">Resultados del ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5202-141">Sample Output</span></span>

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a><span data-ttu-id="d5202-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5202-142">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="d5202-143">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d5202-143">C# Programming Guide</span></span>](../..//index.md)
- [<span data-ttu-id="d5202-144">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5202-144">Attributes</span></span>](../../../..//standard/attributes/index.md)
- [<span data-ttu-id="d5202-145">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="d5202-145">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="d5202-146">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5202-146">Attributes</span></span>](index.md)
- [<span data-ttu-id="d5202-147">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="d5202-147">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="d5202-148">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="d5202-148">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
