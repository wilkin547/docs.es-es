---
title: Aplicar atributos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- attributes [.NET Framework], applying
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
ms.openlocfilehash: 14cd6fef80ff9ae3a9d78531785edab0da7cc6b9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130912"
---
# <a name="applying-attributes"></a><span data-ttu-id="c92c5-102">Aplicar atributos</span><span class="sxs-lookup"><span data-stu-id="c92c5-102">Applying Attributes</span></span>
<span data-ttu-id="c92c5-103">Para aplicar un atributo a un elemento del código se puede utilizar el proceso siguiente:</span><span class="sxs-lookup"><span data-stu-id="c92c5-103">Use the following process to apply an attribute to an element of your code.</span></span>  
  
1. <span data-ttu-id="c92c5-104">Definir un atributo nuevo o utilizar uno existente importando su espacio de nombres de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c92c5-104">Define a new attribute or use an existing attribute by importing its namespace from the .NET Framework.</span></span>  
  
2. <span data-ttu-id="c92c5-105">Aplique el atributo al elemento de código colocándolo inmediatamente antes del elemento.</span><span class="sxs-lookup"><span data-stu-id="c92c5-105">Apply the attribute to the code element by placing it immediately before the element.</span></span>  
  
     <span data-ttu-id="c92c5-106">Cada lenguaje tiene su propia sintaxis de atributo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-106">Each language has its own attribute syntax.</span></span> <span data-ttu-id="c92c5-107">En C++ y C#, el atributo está incluido entre corchetes y separado del elemento por un espacio en blanco, que puede incluir un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="c92c5-107">In C++ and C#, the attribute is surrounded by square brackets and separated from the element by white space, which can include a line break.</span></span> <span data-ttu-id="c92c5-108">En Visual Basic, el atributo está incluido entre corchetes angulares y debe estar en la misma línea lógica; se puede utilizar el carácter de continuación de línea si se desea un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="c92c5-108">In Visual Basic, the attribute is surrounded by angle brackets and must be on the same logical line; the line continuation character can be used if a line break is desired.</span></span>
  
3. <span data-ttu-id="c92c5-109">Especifique parámetros posicionales y parámetros con nombre para el atributo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-109">Specify positional parameters and named parameters for the attribute.</span></span>  
  
     <span data-ttu-id="c92c5-110">Los parámetros posicionales son obligatorios y preceden a cualquier parámetro con nombre; corresponden a los parámetros de uno de los constructores del atributo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-110">Positional parameters are required and must come before any named parameters; they correspond to the parameters of one of the attribute's constructors.</span></span> <span data-ttu-id="c92c5-111">Los parámetros con nombre son opcionales y corresponden a las propiedades de lectura y escritura del atributo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-111">Named parameters are optional and correspond to read/write properties of the attribute.</span></span> <span data-ttu-id="c92c5-112">En C++ y C#, especifique `name`=`value` para cada parámetro opcional, donde `name` es el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c92c5-112">In C++, and C#, specify `name`=`value` for each optional parameter, where `name` is the name of the property.</span></span> <span data-ttu-id="c92c5-113">En Visual Basic, especifique `name`:=`value`.</span><span class="sxs-lookup"><span data-stu-id="c92c5-113">In Visual Basic, specify `name`:=`value`.</span></span>  
  
 <span data-ttu-id="c92c5-114">El atributo se emite en metadatos al compilar el código y queda disponible para Common Language Runtime y cualquier aplicación o herramienta personalizada a través de los servicios de reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c92c5-114">The attribute is emitted into metadata when you compile your code and is available to the common language runtime and any custom tool or application through the runtime reflection services.</span></span>  
  
 <span data-ttu-id="c92c5-115">Por convención, todos los nombres de atributos terminan con la palabra Attribute.</span><span class="sxs-lookup"><span data-stu-id="c92c5-115">By convention, all attribute names end with Attribute.</span></span> <span data-ttu-id="c92c5-116">Sin embargo, algunos lenguajes orientados a Common Language Runtime, como Visual Basic y C#, no requieren que se especifique el nombre completo de los atributos.</span><span class="sxs-lookup"><span data-stu-id="c92c5-116">However, several languages that target the runtime, such as Visual Basic and C#, do not require you to specify the full name of an attribute.</span></span> <span data-ttu-id="c92c5-117">Por ejemplo, si desea inicializar <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, solo es necesario hacer referencia al mismo como **Obsolete**.</span><span class="sxs-lookup"><span data-stu-id="c92c5-117">For example, if you want to initialize <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, you only need to reference it as **Obsolete**.</span></span>  
  
## <a name="applying-an-attribute-to-a-method"></a><span data-ttu-id="c92c5-118">Aplicar un atributo a un método</span><span class="sxs-lookup"><span data-stu-id="c92c5-118">Applying an Attribute to a Method</span></span>  
 <span data-ttu-id="c92c5-119">El siguiente ejemplo de código muestra cómo se declara **System.ObsoleteAttribute**, que marca código como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c92c5-119">The following code example shows how to declare **System.ObsoleteAttribute**, which marks code as obsolete.</span></span> <span data-ttu-id="c92c5-120">La cadena `"Will be removed in next version"` se pasa al atributo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-120">The string `"Will be removed in next version"` is passed to the attribute.</span></span> <span data-ttu-id="c92c5-121">Este atributo da lugar a una advertencia del compilador que muestra la cadena transferida cuando se llama al código que describe el atributo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-121">This attribute causes a compiler warning that displays the passed string when code that the attribute describes is called.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## <a name="applying-attributes-at-the-assembly-level"></a><span data-ttu-id="c92c5-122">Aplicar atributos a ensamblados</span><span class="sxs-lookup"><span data-stu-id="c92c5-122">Applying Attributes at the Assembly Level</span></span>  
 <span data-ttu-id="c92c5-123">Si desea aplicar un atributo a un ensamblado, utilice la palabra clave **assembly** (`Assembly` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c92c5-123">If you want to apply an attribute at the assembly level, use the **assembly** (`Assembly` in Visual Basic) keyword.</span></span> <span data-ttu-id="c92c5-124">El código siguiente muestra el atributo**AssemblyTitleAttribute** aplicado al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c92c5-124">The following code shows the **AssemblyTitleAttribute** applied at the assembly level.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 <span data-ttu-id="c92c5-125">Cuando se aplica este atributo, la cadena `"My Assembly"` se coloca en el manifiesto del ensamblado, en la parte de metadatos del archivo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-125">When this attribute is applied, the string `"My Assembly"` is placed in the assembly manifest in the metadata portion of the file.</span></span> <span data-ttu-id="c92c5-126">Se puede ver el atributo utilizando el [Desensamblador de MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) o creando un programa personalizado que recupere el atributo.</span><span class="sxs-lookup"><span data-stu-id="c92c5-126">You can view the attribute either by using the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by creating a custom program to retrieve the attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92c5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c92c5-127">See also</span></span>

- [<span data-ttu-id="c92c5-128">Atributos</span><span class="sxs-lookup"><span data-stu-id="c92c5-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="c92c5-129">Recuperar la información almacenada en atributos</span><span class="sxs-lookup"><span data-stu-id="c92c5-129">Retrieving Information Stored in Attributes</span></span>](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="c92c5-130">Conceptos</span><span class="sxs-lookup"><span data-stu-id="c92c5-130">Concepts</span></span>](/cpp/windows/attributed-programming-concepts)
- [<span data-ttu-id="c92c5-131">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="c92c5-131">Attributes (C#)</span></span>](../../csharp/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="c92c5-132">Información general sobre los atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c92c5-132">Attributes overview (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/attributes/index.md)
