---
title: Compilar un proyecto de interoperabilidad
description: Revise cómo compilar un proyecto de interoperabilidad COM, que se compila como un proyecto administrado si hace referencia a uno o varios ensamblados que contienen tipos COM importados.
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
ms.openlocfilehash: a8dfbeb88d0057eb3c9047b4435f021750ed86d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620864"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="4f7c5-103">Compilar un proyecto de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="4f7c5-103">Compiling an Interop Project</span></span>

<span data-ttu-id="4f7c5-104">Los proyectos de interoperabilidad COM que hacen referencia a uno o más ensamblados que contienen tipos COM importados se compilan como cualquier otro proyecto administrado.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-104">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="4f7c5-105">Puede hacer referencia a ensamblados de interoperabilidad en un entorno de desarrollo como Visual Studio, o hacer referencia a ellos cuando se usa un compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-105">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="4f7c5-106">En cualquier caso, para compilar correctamente, el ensamblado de interoperabilidad debe estar en el mismo directorio que los demás archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-106">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="4f7c5-107">Hay dos maneras de hacer referencia a ensamblados de interoperabilidad:</span><span class="sxs-lookup"><span data-stu-id="4f7c5-107">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="4f7c5-108">Tipos de interoperabilidad insertados: A partir de .NET Framework 4 y Visual Studio 2010, se puede indicar al compilador que inserte información de tipos de un ensamblado de interoperabilidad en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-108">Embedded interop types: Beginning with the .NET Framework 4 and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="4f7c5-109">Esta es la técnica recomendada.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-109">This is the recommended technique.</span></span>

- <span data-ttu-id="4f7c5-110">Implementación de ensamblados de interoperabilidad: se puede crear una referencia estándar a un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-110">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="4f7c5-111">En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-111">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="4f7c5-112">Las diferencias entre estas dos técnicas se explican con más detalle en [Usar tipos COM en código administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4f7c5-112">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="4f7c5-113">La inserción de tipos de interoperabilidad con Visual Studio se describe en [Tutorial: Insertar tipos de ensamblados administrados en Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4f7c5-113">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="4f7c5-114">Para hacer referencia a un ensamblado de interoperabilidad con un compilador de línea de comandos e insertar información de tipos en los archivos ejecutables, use el modificador del compilador [-link (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-114">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="4f7c5-115">Las aplicaciones de Visual C++ no pueden insertar información de tipos, pero pueden interoperar con aplicaciones o complementos que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-115">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="4f7c5-116">Para compilar una aplicación que incluye un ensamblado de interoperabilidad primario cuando se implementa, use el modificador del compilador **/reference** y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="4f7c5-116">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f7c5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f7c5-117">See also</span></span>

- [<span data-ttu-id="4f7c5-118">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4f7c5-118">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="4f7c5-119">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="4f7c5-119">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="4f7c5-120">[Uso de tipos COM en código administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4f7c5-120">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="4f7c5-121">Tutorial: Insertar tipos de ensamblados administrados en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4f7c5-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="4f7c5-122">Importar una biblioteca de tipos como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="4f7c5-122">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
