---
title: Usar CodeDOM
description: Use Code Document Object Model (CodeDOM), que proporciona tipos que representan muchos tipos comunes de elementos de código fuente, para ensamblar un gráfico de objetos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- Code Document Object Model
- Code Document Object Model, graphs
- types, CodeDOM
- namespaces [.NET Framework], CodeDOM
- templated code generation
- dynamically representing source code
- source code models
- CodeDOM
- graphing with CodeDOM
- dynamic compilation
- code generators
- CodeDOM, graphs
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
ms.openlocfilehash: 476d8c18f386f889855c664147b1ee20995dc6f9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865221"
---
# <a name="using-the-codedom"></a><span data-ttu-id="ef6eb-103">Usar CodeDOM</span><span class="sxs-lookup"><span data-stu-id="ef6eb-103">Using the CodeDOM</span></span>
<span data-ttu-id="ef6eb-104">CodeDOM proporciona tipos que representan muchos tipos comunes de elementos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-104">The CodeDOM provides types that represent many common types of source code elements.</span></span> <span data-ttu-id="ef6eb-105">Se puede diseñar un programa que compile un modelo de código fuente utilizando los elementos de CodeDOM para ensamblar un gráfico de objetos.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-105">You can design a program that builds a source code model using CodeDOM elements to assemble an object graph.</span></span> <span data-ttu-id="ef6eb-106">Este gráfico de objetos se puede representar como código fuente utilizando un generador de código de CodeDOM para un lenguaje de programación compatible.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-106">This object graph can be rendered as source code using a CodeDOM code generator for a supported programming language.</span></span> <span data-ttu-id="ef6eb-107">CodeDOM también se puede utilizar para compilar código fuente en un ensamblado binario.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-107">The CodeDOM can also be used to compile source code into a binary assembly.</span></span>  
  
 <span data-ttu-id="ef6eb-108">Algunos usos habituales de CodeDOM son:</span><span class="sxs-lookup"><span data-stu-id="ef6eb-108">Some common uses for the CodeDOM include:</span></span>  
  
- <span data-ttu-id="ef6eb-109">Generación de código mediante plantillas: generación de código para ASP.NET, proxies de clientes de servicios Web XML, asistentes para código, diseñadores y otros mecanismos de emisión de código.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-109">Templated code generation: generating code for ASP.NET, XML Web services client proxies, code wizards, designers, or other code-emitting mechanisms.</span></span>  
  
- <span data-ttu-id="ef6eb-110">Compilación dinámica: compatibilidad para compilación de código en uno o varios lenguajes.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-110">Dynamic compilation: supporting code compilation in single or multiple languages.</span></span>  
  
## <a name="building-a-codedom-graph"></a><span data-ttu-id="ef6eb-111">Compilar un gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="ef6eb-111">Building a CodeDOM Graph</span></span>  
 <span data-ttu-id="ef6eb-112">El espacio de nombres <xref:System.CodeDom> proporciona clases para representar la estructura lógica del código fuente, independientemente de la sintaxis del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-112">The <xref:System.CodeDom> namespace provides classes for representing the logical structure of source code, independent of language syntax.</span></span>  
  
### <a name="the-structure-of-a-codedom-graph"></a><span data-ttu-id="ef6eb-113">La estructura de un gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="ef6eb-113">The Structure of a CodeDOM Graph</span></span>  
 <span data-ttu-id="ef6eb-114">La estructura de un gráfico CodeDOM es similar a un árbol de contenedores.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-114">The structure of a CodeDOM graph is like a tree of containers.</span></span> <span data-ttu-id="ef6eb-115">El contenedor raíz o el contenedor superior de cada gráfico CodeDOM compilable es una unidad <xref:System.CodeDom.CodeCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-115">The top-most, or root, container of each compilable CodeDOM graph is a <xref:System.CodeDom.CodeCompileUnit>.</span></span> <span data-ttu-id="ef6eb-116">Todos y cada uno de los elementos del modelo de código fuente deben estar vinculados en el gráfico mediante una propiedad de un objeto <xref:System.CodeDom.CodeObject> del gráfico.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-116">Every element of your source code model must be linked into the graph through a property of a <xref:System.CodeDom.CodeObject> in the graph.</span></span>  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a><span data-ttu-id="ef6eb-117">Compilar un modelo de código fuente para el programa de ejemplo Hola a todos</span><span class="sxs-lookup"><span data-stu-id="ef6eb-117">Building a Source Code Model for a Sample Hello World Program</span></span>  
 <span data-ttu-id="ef6eb-118">En el siguiente tutorial se muestra un ejemplo de cómo compilar un gráfico de objetos CodeDOM que representa el código de una aplicación Hola a todos sencilla.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-118">The following walkthrough provides an example of how to build a CodeDOM object graph that represents the code for a simple Hello World application.</span></span> <span data-ttu-id="ef6eb-119">Para obtener el código fuente completo de este código de ejemplo, vea el tema <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-119">For the complete source code for this code example, see the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> topic.</span></span>  
  
#### <a name="creating-a-compile-unit"></a><span data-ttu-id="ef6eb-120">Crear una unidad de compilación</span><span class="sxs-lookup"><span data-stu-id="ef6eb-120">Creating a compile unit</span></span>  
 <span data-ttu-id="ef6eb-121">CodeDOM define un objeto denominado <xref:System.CodeDom.CodeCompileUnit>, que puede hacer referencia a un gráfico de objetos CodeDOM que modela el código fuente que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-121">The CodeDOM defines an object called a <xref:System.CodeDom.CodeCompileUnit>, which can reference a CodeDOM object graph that models the source code to compile.</span></span> <span data-ttu-id="ef6eb-122">Un objeto **CodeCompileUnit** dispone de propiedades para almacenar referencias a atributos, espacios de nombres y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-122">A **CodeCompileUnit** has properties for storing references to attributes, namespaces, and assemblies.</span></span>  
  
 <span data-ttu-id="ef6eb-123">Los proveedores CodeDom que derivan de la clase <xref:System.CodeDom.Compiler.CodeDomProvider> contienen métodos que procesan el gráfico de objetos a los que hace referencia **CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-123">The CodeDom providers that derive from the <xref:System.CodeDom.Compiler.CodeDomProvider> class contain methods that process the object graph referenced by a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="ef6eb-124">Para crear un gráfico de objetos para una aplicación sencilla, debe ensamblar el modelo de código fuente y hacer referencia a él desde **CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-124">To create an object graph for a simple application, you must assemble the source code model and reference it from a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="ef6eb-125">Se puede crear una nueva unidad de compilación con la sintaxis que muestra este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ef6eb-125">You can create a new compile unit with the syntax demonstrated in this example:</span></span>  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <span data-ttu-id="ef6eb-126"><xref:System.CodeDom.CodeSnippetCompileUnit> puede contener una sección de código fuente que ya está en el lenguaje de destino pero que no se puede representar en otro lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-126">A <xref:System.CodeDom.CodeSnippetCompileUnit> can contain a section of source code that is already in the target language, but cannot be rendered to another language.</span></span>  
  
#### <a name="defining-a-namespace"></a><span data-ttu-id="ef6eb-127">Definir un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ef6eb-127">Defining a namespace</span></span>  
 <span data-ttu-id="ef6eb-128">Para definir un espacio de nombres, cree un objeto <xref:System.CodeDom.CodeNamespace> y asígnele un nombre con el constructor correspondiente o mediante el establecimiento de su propiedad **Name**.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-128">To define a namespace, create a <xref:System.CodeDom.CodeNamespace> and assign a name for it using the appropriate constructor or by setting its **Name** property.</span></span>  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a><span data-ttu-id="ef6eb-129">Importar un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ef6eb-129">Importing a namespace</span></span>  
 <span data-ttu-id="ef6eb-130">Para agregar una directiva de importación de espacios de nombres al espacio de nombres, agregue una importación <xref:System.CodeDom.CodeNamespaceImport> que indique el espacio de nombres que se va a importar a la colección **CodeNamespace.Imports**.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-130">To add a namespace import directive to the namespace, add a <xref:System.CodeDom.CodeNamespaceImport> that indicates the namespace to import to the **CodeNamespace.Imports** collection.</span></span>  
  
 <span data-ttu-id="ef6eb-131">En el siguiente código, se agrega una importación para el espacio de nombres **System** a la colección **Imports** de un espacio de nombres **CodeNamespace** denominado `samples`:</span><span class="sxs-lookup"><span data-stu-id="ef6eb-131">The following code adds an import for the **System** namespace to the **Imports** collection of a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a><span data-ttu-id="ef6eb-132">Vincular elementos de código al gráfico de objetos</span><span class="sxs-lookup"><span data-stu-id="ef6eb-132">Linking code elements into the object graph</span></span>  
 <span data-ttu-id="ef6eb-133">Todos los elementos de código que forman un gráfico CodeDOM deben estar vinculados a <xref:System.CodeDom.CodeCompileUnit>, que es el elemento raíz del árbol, mediante una serie de referencias entre elementos a los que se hace directamente referencia desde las propiedades del objeto raíz del gráfico.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-133">All code elements that form a CodeDOM graph must be linked to the <xref:System.CodeDom.CodeCompileUnit> that is the root element of the tree by a series of references between elements directly referenced from the properties of the root object of the graph.</span></span> <span data-ttu-id="ef6eb-134">Establezca un objeto en una propiedad de un objeto de contenedor para establecer una referencia desde el objeto de contenedor.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-134">Set an object to a property of a container object to establish a reference from the container object.</span></span>  
  
 <span data-ttu-id="ef6eb-135">La instrucción siguiente agrega el **CodeNamespace** `samples` a la propiedad de colección **Namespaces** del objeto raíz **CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-135">The following statement adds the `samples` **CodeNamespace** to the **Namespaces** collection property of the root **CodeCompileUnit**.</span></span>  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a><span data-ttu-id="ef6eb-136">Definir un tipo</span><span class="sxs-lookup"><span data-stu-id="ef6eb-136">Defining a type</span></span>  
 <span data-ttu-id="ef6eb-137">Para declarar una clase, estructura, interfaz o enumeración utilizando CodeDOM, cree un nuevo objeto <xref:System.CodeDom.CodeTypeDeclaration> y asígnele un nombre.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-137">To declare a class, structure, interface, or enumeration using the CodeDOM, create a new <xref:System.CodeDom.CodeTypeDeclaration>, and assign it a name.</span></span> <span data-ttu-id="ef6eb-138">En el siguiente ejemplo se muestra cómo hacerlo mediante una sobrecarga de constructor para establecer la propiedad **Name**:</span><span class="sxs-lookup"><span data-stu-id="ef6eb-138">The following example demonstrates this using a constructor overload to set the **Name** property:</span></span>  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 <span data-ttu-id="ef6eb-139">Para agregar un tipo a un espacio de nombres, agregue una declaración <xref:System.CodeDom.CodeTypeDeclaration> que represente el tipo que se va a agregar al espacio de nombres de la colección **Types** de un espacio de nombres **CodeNamespace**.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-139">To add a type to a namespace, add a <xref:System.CodeDom.CodeTypeDeclaration> that represents the type to add to the namespace to the **Types** collection of a **CodeNamespace**.</span></span>  
  
 <span data-ttu-id="ef6eb-140">En el siguiente ejemplo se muestra cómo agregar una clase denominada `class1` a un espacio de nombres **CodeNamespace** denominado `samples`:</span><span class="sxs-lookup"><span data-stu-id="ef6eb-140">The following example demonstrates how to add a class named `class1` to a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a><span data-ttu-id="ef6eb-141">Agregar miembros de clase a una clase</span><span class="sxs-lookup"><span data-stu-id="ef6eb-141">Adding class members to a class</span></span>  
 <span data-ttu-id="ef6eb-142">El espacio de nombres <xref:System.CodeDom> dispone de diferentes elementos que se pueden utilizar para representar miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-142">The <xref:System.CodeDom> namespace provides a variety of elements that can be used to represent class members.</span></span> <span data-ttu-id="ef6eb-143">Todos los miembros de clase pueden agregarse a la colección **Members** de una declaración <xref:System.CodeDom.CodeTypeDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-143">Each class member can be added to the **Members** collection of a <xref:System.CodeDom.CodeTypeDeclaration>.</span></span>  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a><span data-ttu-id="ef6eb-144">Definir un método de punto de entrada de código para un archivo ejecutable</span><span class="sxs-lookup"><span data-stu-id="ef6eb-144">Defining a code entry point method for an executable</span></span>  
 <span data-ttu-id="ef6eb-145">Si desea compilar el código de un programa ejecutable, es necesario indicar el punto de entrada de un programa creando un objeto <xref:System.CodeDom.CodeEntryPointMethod> que represente el método en el que debe comenzar la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-145">If you are building code for an executable program, it is necessary to indicate the entry point of a program by creating a <xref:System.CodeDom.CodeEntryPointMethod> to represent the method at which program execution should begin.</span></span>  
  
 <span data-ttu-id="ef6eb-146">En el siguiente ejemplo se muestra cómo definir un método de punto de entrada que contiene una expresión <xref:System.CodeDom.CodeMethodInvokeExpression> que llama a **System.Console.WriteLine** para imprimir "Hello World!":</span><span class="sxs-lookup"><span data-stu-id="ef6eb-146">The following example demonstrates how to define an entry point method that contains a <xref:System.CodeDom.CodeMethodInvokeExpression> that calls **System.Console.WriteLine** to print "Hello World!":</span></span>  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 <span data-ttu-id="ef6eb-147">La siguiente instrucción agrega el método de punto de entrada denominado `Start` a la colección **Members** de `class1`:</span><span class="sxs-lookup"><span data-stu-id="ef6eb-147">The following statement adds the entry point method named `Start` to the **Members** collection of `class1`:</span></span>  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 <span data-ttu-id="ef6eb-148">Ahora, la unidad <xref:System.CodeDom.CodeCompileUnit> denominada `compileUnit` contiene el gráfico CodeDOM para un programa Hello World sencillo.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-148">Now the <xref:System.CodeDom.CodeCompileUnit> named `compileUnit` contains the CodeDOM graph for a simple Hello World program.</span></span> <span data-ttu-id="ef6eb-149">Para obtener información sobre la forma de generar y compilar código desde un gráfico CodeDOM, vea [Generar código fuente y compilar un programa a partir de un gráfico CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md).</span><span class="sxs-lookup"><span data-stu-id="ef6eb-149">For information on generating and compiling code from a CodeDOM graph, see [Generating Source Code and Compiling a Program from a CodeDOM Graph](generating-and-compiling-source-code-from-a-codedom-graph.md).</span></span>  
  
### <a name="more-information-on-building-a-codedom-graph"></a><span data-ttu-id="ef6eb-150">Más información sobre la forma de compilar un gráfico CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-150">More information on building a CodeDOM graph</span></span>  
 <span data-ttu-id="ef6eb-151">CodeDOM admite muchos de los tipos comunes de elementos de código que se encuentran en los lenguajes de programación compatibles con Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-151">The CodeDOM supports the many common types of code elements found in programming languages that support the common language runtime.</span></span> <span data-ttu-id="ef6eb-152">CodeDOM no fue diseñado para disponer de elementos que representen todas las características posibles de un lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-152">The CodeDOM was not designed to provide elements to represent all possible programming language features.</span></span> <span data-ttu-id="ef6eb-153">El código que no se puede representar fácilmente con elementos CodeDOM se puede encapsular en un <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember> o <xref:System.CodeDom.CodeSnippetCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-153">Code that cannot be represented easily with CodeDOM elements can be encapsulated in a <xref:System.CodeDom.CodeSnippetExpression>, a <xref:System.CodeDom.CodeSnippetStatement>, a <xref:System.CodeDom.CodeSnippetTypeMember>, or a <xref:System.CodeDom.CodeSnippetCompileUnit>.</span></span> <span data-ttu-id="ef6eb-154">No obstante, los miniprogramas no pueden traducirse automáticamente a otros lenguajes por medio de CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-154">However, snippets cannot be translated to other languages automatically by the CodeDOM.</span></span>  
  
 <span data-ttu-id="ef6eb-155">Para obtener documentación de cada uno de los tipos CodeDOM, consulte la documentación de referencia del espacio de nombres <xref:System.CodeDom>.</span><span class="sxs-lookup"><span data-stu-id="ef6eb-155">For documentation for the each of the CodeDOM types, see the reference documentation for the <xref:System.CodeDom> namespace.</span></span>  
  
 <span data-ttu-id="ef6eb-156">Para ver un gráfico que localice rápidamente el elemento de CodeDOM que representa un tipo específico de elemento de código, vea [Referencia rápida de CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ef6eb-156">For a quick chart to locate the CodeDOM element that represents a specific type of code element, see the [CodeDOM Quick Reference](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).</span></span>
