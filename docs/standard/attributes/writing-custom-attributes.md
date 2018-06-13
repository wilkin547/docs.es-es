---
title: Escribir atributos personalizados
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET Framework], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 114d24c1fc523d5501deb4aa17f9541c5a918276
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574652"
---
# <a name="writing-custom-attributes"></a><span data-ttu-id="d5f39-102">Escribir atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="d5f39-102">Writing Custom Attributes</span></span>
<span data-ttu-id="d5f39-103">Para diseñar sus propios atributos personalizados, no necesitará dominar muchos conceptos nuevos.</span><span class="sxs-lookup"><span data-stu-id="d5f39-103">To design your own custom attributes, you do not need to master many new concepts.</span></span> <span data-ttu-id="d5f39-104">Si está familiarizado con la programación orientada a objetos y sabe cómo diseñar clases, ya tiene la mayoría de los conocimientos necesarios.</span><span class="sxs-lookup"><span data-stu-id="d5f39-104">If you are familiar with object-oriented programming and know how to design classes, you already have most of the knowledge needed.</span></span> <span data-ttu-id="d5f39-105">Los atributos personalizados son esencialmente clases tradicionales que se derivan directa o indirectamente de <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5f39-105">Custom attributes are essentially traditional classes that derive directly or indirectly from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d5f39-106">Como sucede con las clases tradicionales, los atributos personalizados contienen métodos que almacenan y recuperan datos.</span><span class="sxs-lookup"><span data-stu-id="d5f39-106">Just like traditional classes, custom attributes contain methods that store and retrieve data.</span></span>  
  
 <span data-ttu-id="d5f39-107">Los pasos principales para diseñar correctamente clases de atributos personalizados son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5f39-107">The primary steps to properly design custom attribute classes are as follows:</span></span>  
  
-   [<span data-ttu-id="d5f39-108">Aplicar AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="d5f39-108">Applying the AttributeUsageAttribute</span></span>](#cpconapplyingattributeusageattribute)  
  
-   [<span data-ttu-id="d5f39-109">Declarar la clase de atributo</span><span class="sxs-lookup"><span data-stu-id="d5f39-109">Declaring the attribute class</span></span>](#cpcondeclaringattributeclass)  
  
-   [<span data-ttu-id="d5f39-110">Declarar constructores</span><span class="sxs-lookup"><span data-stu-id="d5f39-110">Declaring constructors</span></span>](#cpcondeclaringconstructors)  
  
-   [<span data-ttu-id="d5f39-111">Declarar propiedades</span><span class="sxs-lookup"><span data-stu-id="d5f39-111">Declaring properties</span></span>](#cpcondeclaringproperties)  
  
 <span data-ttu-id="d5f39-112">En esta sección se describe cada uno de estos pasos y, para finalizar, se muestra un [ejemplo de atributo personalizado](#cpconcustomattributeexample).</span><span class="sxs-lookup"><span data-stu-id="d5f39-112">This section describes each of these steps and concludes with a [custom attribute example](#cpconcustomattributeexample).</span></span>  
  
<a name="cpconapplyingattributeusageattribute"></a>   
## <a name="applying-the-attributeusageattribute"></a><span data-ttu-id="d5f39-113">Aplicar AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="d5f39-113">Applying the AttributeUsageAttribute</span></span>  
 <span data-ttu-id="d5f39-114">La declaración de un atributo personalizado empieza con **AttributeUsageAttribute**, que define algunas de las características clave de la clase de atributo.</span><span class="sxs-lookup"><span data-stu-id="d5f39-114">A custom attribute declaration begins with the **AttributeUsageAttribute**, which defines some of the key characteristics of your attribute class.</span></span> <span data-ttu-id="d5f39-115">Por ejemplo, puede especificar si el atributo lo pueden heredar otras clases o especificar los elementos a los que se puede aplicar el atributo.</span><span class="sxs-lookup"><span data-stu-id="d5f39-115">For example, you can specify whether your attribute can be inherited by other classes or specify which elements the attribute can be applied to.</span></span> <span data-ttu-id="d5f39-116">En el siguiente fragmento de código se muestra cómo utilizar **AttributeUsageAttribute**.</span><span class="sxs-lookup"><span data-stu-id="d5f39-116">The following code fragment demonstrates how to use the **AttributeUsageAttribute**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 <span data-ttu-id="d5f39-117"><xref:System.AttributeUsageAttribute?displayProperty=nameWithType> tiene tres miembros que son importantes para la creación de atributos personalizados: [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2) y [AllowMultiple](#cpconwritingcustomattributesanchor3).</span><span class="sxs-lookup"><span data-stu-id="d5f39-117">The <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> has three members that are important for the creation of custom attributes: [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2), and [AllowMultiple](#cpconwritingcustomattributesanchor3).</span></span>  
  
<a name="cpconwritingcustomattributesanchor1"></a>   
### <a name="attributetargets-member"></a><span data-ttu-id="d5f39-118">Miembro AttributeTargets</span><span class="sxs-lookup"><span data-stu-id="d5f39-118">AttributeTargets Member</span></span>  
 <span data-ttu-id="d5f39-119">En el ejemplo anterior, se especifica **AttributeTargets.All** , lo que indica que este atributo se puede aplicar a todos los elementos de programa.</span><span class="sxs-lookup"><span data-stu-id="d5f39-119">In the previous example, **AttributeTargets.All** is specified, indicating that this attribute can be applied to all program elements.</span></span> <span data-ttu-id="d5f39-120">Como alternativa, puede especificar **AttributeTargets.Class**, que indica que el atributo solo se puede aplicar a una clase, o **AttributeTargets.Method**, que indica que el atributo solo se puede aplicar a un método.</span><span class="sxs-lookup"><span data-stu-id="d5f39-120">Alternatively, you can specify **AttributeTargets.Class**, indicating that your attribute can be applied only to a class, or **AttributeTargets.Method**, indicating that your attribute can be applied only to a method.</span></span> <span data-ttu-id="d5f39-121">De esta manera, un atributo personalizado puede marcar para descripción todos los elementos del programa.</span><span class="sxs-lookup"><span data-stu-id="d5f39-121">All program elements can be marked for description by a custom attribute in this manner.</span></span>  
  
 <span data-ttu-id="d5f39-122">También se pueden pasar varias instancias de <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="d5f39-122">You can also pass multiple instances of <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="d5f39-123">El fragmento de código siguiente especifica que un atributo personalizado se puede aplicar a cualquier clase o método.</span><span class="sxs-lookup"><span data-stu-id="d5f39-123">The following code fragment specifies that a custom attribute can be applied to any class or method.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
<a name="cpconwritingcustomattributesanchor2"></a>   
### <a name="inherited-property"></a><span data-ttu-id="d5f39-124">Propiedad Inherited</span><span class="sxs-lookup"><span data-stu-id="d5f39-124">Inherited Property</span></span>  
 <span data-ttu-id="d5f39-125">La propiedad <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> indica si el atributo lo pueden heredar clases derivadas de las clases a las que se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="d5f39-125">The <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property indicates whether your attribute can be inherited by classes that are derived from the classes to which your attribute is applied.</span></span> <span data-ttu-id="d5f39-126">Esta propiedad acepta una marca **true** (valor predeterminado) o **false** .</span><span class="sxs-lookup"><span data-stu-id="d5f39-126">This property takes either a **true** (the default) or **false** flag.</span></span> <span data-ttu-id="d5f39-127">Por ejemplo, en el ejemplo siguiente, `MyAttribute` tiene un valor <xref:System.AttributeUsageAttribute.Inherited%2A> predeterminado de **true**, mientras que `YourAttribute` tiene un valor <xref:System.AttributeUsageAttribute.Inherited%2A> de **false**.</span><span class="sxs-lookup"><span data-stu-id="d5f39-127">For example, in the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.Inherited%2A> value of **true**, while `YourAttribute` has an <xref:System.AttributeUsageAttribute.Inherited%2A> value of **false**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 <span data-ttu-id="d5f39-128">Los dos atributos se aplican entonces a un método de la clase base `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="d5f39-128">The two attributes are then applied to a method in the base class `MyClass`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 <span data-ttu-id="d5f39-129">Por último, la clase `YourClass` se hereda de la clase base `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="d5f39-129">Finally, the class `YourClass` is inherited from the base class `MyClass`.</span></span> <span data-ttu-id="d5f39-130">El método `MyMethod` muestra `MyAttribute`, pero no `YourAttribute`.</span><span class="sxs-lookup"><span data-stu-id="d5f39-130">The method `MyMethod` shows `MyAttribute`, but not `YourAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
<a name="cpconwritingcustomattributesanchor3"></a>   
### <a name="allowmultiple-property"></a><span data-ttu-id="d5f39-131">Propiedad AllowMultiple</span><span class="sxs-lookup"><span data-stu-id="d5f39-131">AllowMultiple Property</span></span>  
 <span data-ttu-id="d5f39-132">La propiedad <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> indica si pueden existir varias instancias del atributo en un elemento.</span><span class="sxs-lookup"><span data-stu-id="d5f39-132">The <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> property indicates whether multiple instances of your attribute can exist on an element.</span></span> <span data-ttu-id="d5f39-133">Si establece en **true**, se permiten varias instancias; si se establece en **false** (el valor predeterminado), solo se permite una instancia.</span><span class="sxs-lookup"><span data-stu-id="d5f39-133">If set to **true**, multiple instances are allowed; if set to **false** (the default), only one instance is allowed.</span></span>  
  
 <span data-ttu-id="d5f39-134">En el ejemplo siguiente, `MyAttribute` tiene un valor <xref:System.AttributeUsageAttribute.AllowMultiple%2A> predeterminado de **false**, mientras que `YourAttribute` tiene un valor **true**.</span><span class="sxs-lookup"><span data-stu-id="d5f39-134">In the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.AllowMultiple%2A> value of **false**, while `YourAttribute` has a value of **true**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 <span data-ttu-id="d5f39-135">Si se aplican varias instancias de estos atributos, `MyAttribute` produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="d5f39-135">When multiple instances of these attributes are applied, `MyAttribute` produces a compiler error.</span></span> <span data-ttu-id="d5f39-136">En el ejemplo de código siguiente se muestra el uso válido de `YourAttribute` y el uso no válido de `MyAttribute`.</span><span class="sxs-lookup"><span data-stu-id="d5f39-136">The following code example shows the valid use of `YourAttribute` and the invalid use of `MyAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 <span data-ttu-id="d5f39-137">Si tanto la propiedad <xref:System.AttributeUsageAttribute.AllowMultiple%2A> como la propiedad <xref:System.AttributeUsageAttribute.Inherited%2A> se establecen en **true**, una clase que se hereda de otra clase puede heredar un atributo y tiene otra instancia del mismo atributo aplicada en la misma clase secundaria.</span><span class="sxs-lookup"><span data-stu-id="d5f39-137">If both the <xref:System.AttributeUsageAttribute.AllowMultiple%2A> property and the <xref:System.AttributeUsageAttribute.Inherited%2A> property are set to **true**, a class that is inherited from another class can inherit an attribute and have another instance of the same attribute applied in the same child class.</span></span> <span data-ttu-id="d5f39-138">Si se establece <xref:System.AttributeUsageAttribute.AllowMultiple%2A> en **false**, las instancias nuevas del mismo atributo de la clase secundaria sobrescribirán los valores de los atributos de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="d5f39-138">If <xref:System.AttributeUsageAttribute.AllowMultiple%2A> is set to **false**, the values of any attributes in the parent class will be overwritten by new instances of the same attribute in the child class.</span></span>  
  
<a name="cpcondeclaringattributeclass"></a>   
## <a name="declaring-the-attribute-class"></a><span data-ttu-id="d5f39-139">Declarar la clase de atributo</span><span class="sxs-lookup"><span data-stu-id="d5f39-139">Declaring the Attribute Class</span></span>  
 <span data-ttu-id="d5f39-140">Después de aplicar <xref:System.AttributeUsageAttribute>, puede empezar a definir los detalles del atributo.</span><span class="sxs-lookup"><span data-stu-id="d5f39-140">After you apply the <xref:System.AttributeUsageAttribute>, you can begin to define the specifics of your attribute.</span></span> <span data-ttu-id="d5f39-141">La declaración de una clase de atributo es similar a la declaración de una clase tradicional, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5f39-141">The declaration of an attribute class looks similar to the declaration of a traditional class, as demonstrated by the following code.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 <span data-ttu-id="d5f39-142">En esta definición de atributo se muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d5f39-142">This attribute definition demonstrates the following points:</span></span>  
  
-   <span data-ttu-id="d5f39-143">Las clases de atributos se deben declarar como clases públicas.</span><span class="sxs-lookup"><span data-stu-id="d5f39-143">Attribute classes must be declared as public classes.</span></span>  
  
-   <span data-ttu-id="d5f39-144">Por convención, el nombre de la clase de atributo termina con la palabra **Attribute**.</span><span class="sxs-lookup"><span data-stu-id="d5f39-144">By convention, the name of the attribute class ends with the word **Attribute**.</span></span> <span data-ttu-id="d5f39-145">Aunque no es obligatoria, se recomienda seguir esta convención para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="d5f39-145">While not required, this convention is recommended for readability.</span></span> <span data-ttu-id="d5f39-146">Cuando se aplica el atributo, la inclusión de la palabra Attribute es opcional.</span><span class="sxs-lookup"><span data-stu-id="d5f39-146">When the attribute is applied, the inclusion of the word Attribute is optional.</span></span>  
  
-   <span data-ttu-id="d5f39-147">Todas las clases de atributo deben heredar directa o indirectamente de **System.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="d5f39-147">All attribute classes must inherit directly or indirectly from **System.Attribute**.</span></span>  
  
-   <span data-ttu-id="d5f39-148">En Microsoft Visual Basic, todas las clases de atributos personalizados deben tener el atributo **AttributeUsageAttribute** .</span><span class="sxs-lookup"><span data-stu-id="d5f39-148">In Microsoft Visual Basic, all custom attribute classes must have the **AttributeUsageAttribute** attribute.</span></span>  
  
<a name="cpcondeclaringconstructors"></a>   
## <a name="declaring-constructors"></a><span data-ttu-id="d5f39-149">Declarar constructores</span><span class="sxs-lookup"><span data-stu-id="d5f39-149">Declaring Constructors</span></span>  
 <span data-ttu-id="d5f39-150">Los atributos se inicializan con constructores del mismo modo que las clases tradicionales.</span><span class="sxs-lookup"><span data-stu-id="d5f39-150">Attributes are initialized with constructors in the same way as traditional classes.</span></span> <span data-ttu-id="d5f39-151">En el siguiente fragmento de código se muestra un constructor de atributos típico.</span><span class="sxs-lookup"><span data-stu-id="d5f39-151">The following code fragment illustrates a typical attribute constructor.</span></span> <span data-ttu-id="d5f39-152">Este constructor público acepta un parámetro y establece su valor igual al de una variable miembro.</span><span class="sxs-lookup"><span data-stu-id="d5f39-152">This public constructor takes a parameter and sets its value equal to a member variable.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 <span data-ttu-id="d5f39-153">Puede sobrecargar el constructor para adaptarse a distintas combinaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="d5f39-153">You can overload the constructor to accommodate different combinations of values.</span></span> <span data-ttu-id="d5f39-154">Si también define una [propiedad](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52) para la clase de atributo personalizado, puede utilizar una combinación de parámetros con nombre y de posición al inicializar el atributo.</span><span class="sxs-lookup"><span data-stu-id="d5f39-154">If you also define a [property](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52) for your custom attribute class, you can use a combination of named and positional parameters when initializing the attribute.</span></span> <span data-ttu-id="d5f39-155">Normalmente, se definen todos los parámetros necesarios como de posición y todos parámetros opcionales como con nombre.</span><span class="sxs-lookup"><span data-stu-id="d5f39-155">Typically, you define all required parameters as positional and all optional parameters as named.</span></span> <span data-ttu-id="d5f39-156">En este caso, el atributo no se puede inicializar sin el parámetro obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d5f39-156">In this case, the attribute cannot be initialized without the required parameter.</span></span> <span data-ttu-id="d5f39-157">Todos los demás parámetros son opcionales.</span><span class="sxs-lookup"><span data-stu-id="d5f39-157">All other parameters are optional.</span></span> <span data-ttu-id="d5f39-158">Tenga en cuenta que en Visual Basic, los constructores de una clase de atributo no deben utilizar un argumento ParamArray.</span><span class="sxs-lookup"><span data-stu-id="d5f39-158">Note that in Visual Basic, constructors for an attribute class should not use a ParamArray argument.</span></span>  
  
 <span data-ttu-id="d5f39-159">En el ejemplo de código siguiente, se muestra cómo se puede aplicar un atributo que utiliza el constructor anterior mediante parámetros obligatorios y opcionales.</span><span class="sxs-lookup"><span data-stu-id="d5f39-159">The following code example shows how an attribute that uses the previous constructor can be applied using optional and required parameters.</span></span> <span data-ttu-id="d5f39-160">Se supone que el atributo tiene un valor booleano obligatorio y una propiedad de cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="d5f39-160">It assumes that the attribute has one required Boolean value and one optional string property.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
<a name="cpcondeclaringproperties"></a>   
## <a name="declaring-properties"></a><span data-ttu-id="d5f39-161">Declarar propiedades</span><span class="sxs-lookup"><span data-stu-id="d5f39-161">Declaring Properties</span></span>  
 <span data-ttu-id="d5f39-162">Si quiere definir un parámetro con nombre o proporcionar un método sencillo para devolver los valores almacenados por el atributo, declare una [propiedad](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span><span class="sxs-lookup"><span data-stu-id="d5f39-162">If you want to define a named parameter or provide an easy way to return the values stored by your attribute, declare a [property](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span></span> <span data-ttu-id="d5f39-163">Las propiedades de atributo deben declararse como entidades públicas con una descripción del tipo de datos que se devolverá.</span><span class="sxs-lookup"><span data-stu-id="d5f39-163">Attribute properties should be declared as public entities with a description of the data type that will be returned.</span></span> <span data-ttu-id="d5f39-164">Defina la variable que contendrá el valor de la propiedad y asóciela con los métodos **get** y **set** .</span><span class="sxs-lookup"><span data-stu-id="d5f39-164">Define the variable that will hold the value of your property and associate it with the **get** and **set** methods.</span></span> <span data-ttu-id="d5f39-165">En el ejemplo de código siguiente se muestra cómo implementar una propiedad simple en el atributo.</span><span class="sxs-lookup"><span data-stu-id="d5f39-165">The following code example demonstrates how to implement a simple property in your attribute.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
<a name="cpconcustomattributeexample"></a>   
## <a name="custom-attribute-example"></a><span data-ttu-id="d5f39-166">ejemplo de atributo personalizado</span><span class="sxs-lookup"><span data-stu-id="d5f39-166">Custom Attribute Example</span></span>  
 <span data-ttu-id="d5f39-167">En esta sección se incorpora la información anterior y se muestra cómo se diseña un atributo simple que documente información sobre el autor de una sección del código.</span><span class="sxs-lookup"><span data-stu-id="d5f39-167">This section incorporates the previous information and shows how to design a simple attribute that documents information about the author of a section of code.</span></span> <span data-ttu-id="d5f39-168">El atributo de este ejemplo almacena el nombre y el nivel del programador y si se ha revisado el código.</span><span class="sxs-lookup"><span data-stu-id="d5f39-168">The attribute in this example stores the name and level of the programmer, and whether the code has been reviewed.</span></span> <span data-ttu-id="d5f39-169">Utiliza tres variables privadas para almacenar los valores reales que se deben guardar.</span><span class="sxs-lookup"><span data-stu-id="d5f39-169">It uses three private variables to store the actual values to save.</span></span> <span data-ttu-id="d5f39-170">Cada variable se representa mediante una propiedad pública que obtiene y establece los valores.</span><span class="sxs-lookup"><span data-stu-id="d5f39-170">Each variable is represented by a public property that gets and sets the values.</span></span> <span data-ttu-id="d5f39-171">Por último, el constructor se define con dos parámetros obligatorios.</span><span class="sxs-lookup"><span data-stu-id="d5f39-171">Finally, the constructor is defined with two required parameters.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 <span data-ttu-id="d5f39-172">Puede aplicar este atributo con el nombre completo, `DeveloperAttribute`, o el nombre abreviado, `Developer`, de una de las maneras siguientes.</span><span class="sxs-lookup"><span data-stu-id="d5f39-172">You can apply this attribute using the full name, `DeveloperAttribute`, or using the abbreviated name, `Developer`, in one of the following ways.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 <span data-ttu-id="d5f39-173">En el primer ejemplo se muestra el atributo aplicado solo con los parámetros con nombre obligatorios, mientras que en el segundo ejemplo se muestra el atributo aplicado con los parámetros obligatorios y opcionales.</span><span class="sxs-lookup"><span data-stu-id="d5f39-173">The first example shows the attribute applied with only the required named parameters, while the second example shows the attribute applied with both the required and optional parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f39-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5f39-174">See Also</span></span>  
 <xref:System.Attribute?displayProperty=nameWithType>  
 <xref:System.AttributeUsageAttribute>  
 [<span data-ttu-id="d5f39-175">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5f39-175">Attributes</span></span>](../../../docs/standard/attributes/index.md)
