---
title: Generación y compilación dinámicas de código fuente
description: Compile y genere código fuente dinámico en .NET con Code Document Object Model (CodeDOM). Los elementos CodeDOM se vinculan para formar un gráfico CodeDOM.
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
ms.openlocfilehash: 3cdd89ac9745f6af133ca683afff64283f2727d1
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475104"
---
# <a name="compile-and-generate-dynamic-source-code"></a><span data-ttu-id="6b186-104">Compilación y generación de código fuente dinámico</span><span class="sxs-lookup"><span data-stu-id="6b186-104">Compile and generate dynamic source code</span></span>

<span data-ttu-id="6b186-105">.NET Framework incluye un mecanismo denominado Code Document Object Model (CodeDOM) que permite que los desarrolladores de programas que emiten código de origen generen código fuente en varios lenguajes de programación en tiempo de ejecución, en función de un único modelo que representa el código que se va a representar.</span><span class="sxs-lookup"><span data-stu-id="6b186-105">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
<span data-ttu-id="6b186-106">Para representar el código fuente, los elementos CodeDOM se enlazan entre sí para formar una estructura de datos denominada gráfico CodeDOM, que modela la estructura de parte del código fuente.</span><span class="sxs-lookup"><span data-stu-id="6b186-106">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
<span data-ttu-id="6b186-107">El espacio de nombres <xref:System.CodeDom?displayProperty=fullName> define los tipos que pueden representar la estructura lógica del código fuente, independientemente de un lenguaje de programación específico.</span><span class="sxs-lookup"><span data-stu-id="6b186-107">The <xref:System.CodeDom?displayProperty=fullName> namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="6b186-108">El espacio de nombres <xref:System.CodeDom.Compiler?displayProperty=fullName> define los tipos para generar código fuente a partir de gráficos CodeDOM y para administrar la compilación del código fuente en los lenguajes admitidos.</span><span class="sxs-lookup"><span data-stu-id="6b186-108">The <xref:System.CodeDom.Compiler?displayProperty=fullName> namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="6b186-109">Los desarrolladores o proveedores de compiladores pueden extender el conjunto de lenguajes admitidos.</span><span class="sxs-lookup"><span data-stu-id="6b186-109">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
<span data-ttu-id="6b186-110">El modelado de código fuente independiente del lenguaje puede resultar valioso cuando un programa necesita generar código fuente para un modelo de programa en varios lenguajes o para un lenguaje de destino indeterminado.</span><span class="sxs-lookup"><span data-stu-id="6b186-110">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="6b186-111">Por ejemplo, algunos diseñadores usan CodeDOM como una interfaz de abstracción del lenguaje para generar código fuente en el lenguaje de programación correcto, si CodeDOM es compatible con el idioma.</span><span class="sxs-lookup"><span data-stu-id="6b186-111">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
<span data-ttu-id="6b186-112">.NET Framework incluye los generadores de código y compiladores de código para <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> y <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="6b186-112">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b186-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6b186-113">In this section</span></span>

- [<span data-ttu-id="6b186-114">Usar CodeDOM</span><span class="sxs-lookup"><span data-stu-id="6b186-114">Using the CodeDOM</span></span>](using-the-codedom.md)

  <span data-ttu-id="6b186-115">Describe los usos comunes y muestra cómo se compila un gráfico de objetos simple mediante CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="6b186-115">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
- [<span data-ttu-id="6b186-116">Generación de código fuente y compilación de un programa a partir de un gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="6b186-116">Generate Source Code and Compile a Program from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)  

  <span data-ttu-id="6b186-117">Describe cómo generar código fuente y compilar el código generado con un compilador externo mediante el uso de las clases definidas en el espacio de nombres `System.CodeDom.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="6b186-117">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
- [<span data-ttu-id="6b186-118">Cómo: Crear un archivo de documentación XML mediante CodeDOM</span><span class="sxs-lookup"><span data-stu-id="6b186-118">How to: Create an XML Documentation File Using CodeDOM</span></span>](how-to-create-an-xml-documentation-file-using-codedom.md)  

  <span data-ttu-id="6b186-119">Describe cómo usar CodeDOM para generar código con comentarios de documentación XML y compilar el código generado para que cree la salida de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="6b186-119">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
- [<span data-ttu-id="6b186-120">Cómo: Crear un clase mediante CodeDOM</span><span class="sxs-lookup"><span data-stu-id="6b186-120">How to: Create a Class Using CodeDOM</span></span>](how-to-create-a-class-using-codedom.md)  

  <span data-ttu-id="6b186-121">Describe cómo usar CodeDOM para generar una clase que contenga campos, propiedades, un método, un constructor y un punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="6b186-121">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6b186-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="6b186-122">Reference</span></span>  

- <xref:System.CodeDom>  

  <span data-ttu-id="6b186-123">Define los elementos que representan elementos de código en lenguajes de programación que tienen como destino Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6b186-123">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
- <xref:System.CodeDom.Compiler>  

  <span data-ttu-id="6b186-124">Define las interfaces para generar y compilar código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6b186-124">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6b186-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6b186-125">Related sections</span></span>  

- <span data-ttu-id="6b186-126">La [Referencia rápida de CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) proporciona a los desarrolladores una forma rápida de encontrar los elementos CodeDOM que representan elementos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="6b186-126">[CodeDOM Quick Reference](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
