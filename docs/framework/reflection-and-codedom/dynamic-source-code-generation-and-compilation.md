---
title: Generación y compilación dinámicas de código fuente
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a90b4214e244bc1f9c5f8e71782e604bd6c7b619
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582598"
---
# <a name="dynamic-source-code-generation-and-compilation"></a><span data-ttu-id="26b8c-102">Generación y compilación dinámicas de código fuente</span><span class="sxs-lookup"><span data-stu-id="26b8c-102">Dynamic Source Code Generation and Compilation</span></span>
<span data-ttu-id="26b8c-103">.NET Framework incluye un mecanismo denominado Code Document Object Model (CodeDOM) que permite que los desarrolladores de programas que emiten código de origen generen código fuente en varios lenguajes de programación en tiempo de ejecución, en función de un único modelo que representa el código que se va a representar.</span><span class="sxs-lookup"><span data-stu-id="26b8c-103">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
 <span data-ttu-id="26b8c-104">Para representar el código fuente, los elementos CodeDOM se enlazan entre sí para formar una estructura de datos denominada gráfico CodeDOM, que modela la estructura de parte del código fuente.</span><span class="sxs-lookup"><span data-stu-id="26b8c-104">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
 <span data-ttu-id="26b8c-105">El espacio de nombres `System.CodeDom` define los tipos que pueden representar la estructura lógica del código fuente, independientemente de un lenguaje de programación específico.</span><span class="sxs-lookup"><span data-stu-id="26b8c-105">The `System.CodeDom` namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="26b8c-106">El espacio de nombres `System.CodeDom.Compiler` define los tipos para generar código fuente a partir de gráficos CodeDOM y para administrar la compilación del código fuente en los lenguajes admitidos.</span><span class="sxs-lookup"><span data-stu-id="26b8c-106">The `System.CodeDom.Compiler` namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="26b8c-107">Los desarrolladores o proveedores de compiladores pueden extender el conjunto de lenguajes admitidos.</span><span class="sxs-lookup"><span data-stu-id="26b8c-107">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
 <span data-ttu-id="26b8c-108">El modelado de código fuente independiente del lenguaje puede resultar valioso cuando un programa necesita generar código fuente para un modelo de programa en varios lenguajes o para un lenguaje de destino indeterminado.</span><span class="sxs-lookup"><span data-stu-id="26b8c-108">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="26b8c-109">Por ejemplo, algunos diseñadores usan CodeDOM como una interfaz de abstracción del lenguaje para generar código fuente en el lenguaje de programación correcto, si CodeDOM es compatible con el idioma.</span><span class="sxs-lookup"><span data-stu-id="26b8c-109">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
 <span data-ttu-id="26b8c-110">.NET Framework incluye los generadores de código y compiladores de código para <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> y <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="26b8c-110">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26b8c-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="26b8c-111">In This Section</span></span>  
 [<span data-ttu-id="26b8c-112">Usar CodeDOM</span><span class="sxs-lookup"><span data-stu-id="26b8c-112">Using the CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 <span data-ttu-id="26b8c-113">Describe los usos comunes y muestra cómo se compila un gráfico de objetos simple mediante CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="26b8c-113">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
 [<span data-ttu-id="26b8c-114">Generar código fuente y compilar un programa a partir de un gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="26b8c-114">Generating Source Code and Compiling a Program from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 <span data-ttu-id="26b8c-115">Describe cómo generar código fuente y compilar el código generado con un compilador externo mediante el uso de las clases definidas en el espacio de nombres `System.CodeDom.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="26b8c-115">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
 [<span data-ttu-id="26b8c-116">Cómo: Crear un archivo de documentación XML mediante CodeDOM</span><span class="sxs-lookup"><span data-stu-id="26b8c-116">How to: Create an XML Documentation File Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 <span data-ttu-id="26b8c-117">Describe cómo usar CodeDOM para generar código con comentarios de documentación XML y compilar el código generado para que cree la salida de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="26b8c-117">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
 [<span data-ttu-id="26b8c-118">Cómo: Crear un clase mediante CodeDOM</span><span class="sxs-lookup"><span data-stu-id="26b8c-118">How to: Create a Class Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 <span data-ttu-id="26b8c-119">Describe cómo usar CodeDOM para generar una clase que contenga campos, propiedades, un método, un constructor y un punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="26b8c-119">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="26b8c-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="26b8c-120">Reference</span></span>  
 <xref:System.CodeDom>  
 <span data-ttu-id="26b8c-121">Define los elementos que representan elementos de código en lenguajes de programación que tienen como destino Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="26b8c-121">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
 <xref:System.CodeDom.Compiler>  
 <span data-ttu-id="26b8c-122">Define las interfaces para generar y compilar código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="26b8c-122">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="26b8c-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="26b8c-123">Related Sections</span></span>  
 [<span data-ttu-id="26b8c-124">Referencia rápida de CodeDOM</span><span class="sxs-lookup"><span data-stu-id="26b8c-124">CodeDOM Quick Reference</span></span>](https://msdn.microsoft.com/library/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 <span data-ttu-id="26b8c-125">Proporciona una forma rápida para que los desarrolladores busquen los elementos CodeDOM que representan elementos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="26b8c-125">Provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
