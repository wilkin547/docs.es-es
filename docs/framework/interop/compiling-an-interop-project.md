---
title: Compilar un proyecto de interoperabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bc92eb9d4b7b0ae5db56303f3fbfa991c58e06a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523833"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="bfbbe-102">Compilar un proyecto de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="bfbbe-102">Compiling an Interop Project</span></span>

<span data-ttu-id="bfbbe-103">Los proyectos de interoperabilidad COM que hacen referencia a uno o más ensamblados que contienen tipos COM importados se compilan como cualquier otro proyecto administrado.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="bfbbe-104">Puede hacer referencia a ensamblados de interoperabilidad en un entorno de desarrollo como Visual Studio, o hacer referencia a ellos cuando se usa un compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="bfbbe-105">En cualquier caso, para compilar correctamente, el ensamblado de interoperabilidad debe estar en el mismo directorio que los demás archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="bfbbe-106">Hay dos maneras de hacer referencia a ensamblados de interoperabilidad:</span><span class="sxs-lookup"><span data-stu-id="bfbbe-106">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="bfbbe-107">Tipos de interoperabilidad incrustados: a partir de los .NET Framework 4 y Visual Studio 2010, puede indicar al compilador que inserte información de tipos de un ensamblado de interoperabilidad en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-107">Embedded interop types: Beginning with the .NET Framework 4 and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="bfbbe-108">Esta es la técnica recomendada.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-108">This is the recommended technique.</span></span>

- <span data-ttu-id="bfbbe-109">Implementar ensamblados de interoperabilidad: puede crear una referencia estándar a un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="bfbbe-110">En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="bfbbe-111">Las diferencias entre estas dos técnicas se explican con más detalle en [Usar tipos COM en código administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bfbbe-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="bfbbe-112">En Tutorial: incrustar tipos [de ensamblados administrados en Visual Studio](../../standard/assembly/embed-types-visual-studio.md)se muestra cómo incrustar tipos de interoperabilidad con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="bfbbe-113">Para hacer referencia a un ensamblado de interoperabilidad con un compilador de línea de comandos e incrustar información de tipos en los ejecutables, use los modificadores [-Link (C# opciones del compilador)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="bfbbe-114">Las aplicaciones de Visual C++ no pueden insertar información de tipos, pero pueden interoperar con aplicaciones o complementos que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="bfbbe-115">Para compilar una aplicación que incluye un ensamblado de interoperabilidad primario cuando se implementa, use el modificador del compilador **/reference** y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="bfbbe-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfbbe-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfbbe-116">See also</span></span>

- [<span data-ttu-id="bfbbe-117">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bfbbe-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="bfbbe-118">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="bfbbe-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="bfbbe-119">[Uso de tipos COM en código administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bfbbe-119">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="bfbbe-120">Tutorial: Incrustar los tipos de los ensamblados administrados en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bfbbe-120">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="bfbbe-121">Importar una biblioteca de tipos como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="bfbbe-121">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
