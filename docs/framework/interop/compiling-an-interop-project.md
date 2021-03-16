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
ms.openlocfilehash: 9621d2e060db38549dcaab2e55e7645179831767
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480173"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="b28f2-103">Compilar un proyecto de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="b28f2-103">Compiling an Interop Project</span></span>

<span data-ttu-id="b28f2-104">Los proyectos de interoperabilidad COM que hacen referencia a uno o más ensamblados que contienen tipos COM importados se compilan como cualquier otro proyecto administrado.</span><span class="sxs-lookup"><span data-stu-id="b28f2-104">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="b28f2-105">Puede hacer referencia a ensamblados de interoperabilidad en un entorno de desarrollo como Visual Studio, o hacer referencia a ellos cuando se usa un compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b28f2-105">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="b28f2-106">En cualquier caso, para compilar correctamente, el ensamblado de interoperabilidad debe estar en el mismo directorio que los demás archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b28f2-106">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="b28f2-107">Hay dos maneras de hacer referencia a ensamblados de interoperabilidad:</span><span class="sxs-lookup"><span data-stu-id="b28f2-107">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="b28f2-108">Tipos de interoperabilidad insertados: A partir de .NET Framework 4 y Visual Studio 2010, se puede indicar al compilador que inserte información de tipos de un ensamblado de interoperabilidad en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="b28f2-108">Embedded interop types: Beginning with the .NET Framework 4 and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="b28f2-109">Esta es la técnica recomendada.</span><span class="sxs-lookup"><span data-stu-id="b28f2-109">This is the recommended technique.</span></span>

- <span data-ttu-id="b28f2-110">Implementación de ensamblados de interoperabilidad: se puede crear una referencia estándar a un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="b28f2-110">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="b28f2-111">En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b28f2-111">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="b28f2-112">Las diferencias entre estas dos técnicas se explican con más detalle en [Usar tipos COM en código administrado](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b28f2-112">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="b28f2-113">La inserción de tipos de interoperabilidad con Visual Studio se describe en [Tutorial: Insertar tipos de ensamblados administrados en Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b28f2-113">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="b28f2-114">Para hacer referencia a un ensamblado de interoperabilidad con un compilador de línea de comandos e insertar información de tipos en los archivos ejecutables, use el modificador del compilador [-link (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/inputs.md#embedinteroptypes) o [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="b28f2-114">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/inputs.md#embedinteroptypes) or the [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="b28f2-115">Las aplicaciones de Visual C++ no pueden insertar información de tipos, pero pueden interoperar con aplicaciones o complementos que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="b28f2-115">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="b28f2-116">Para compilar una aplicación que incluye un ensamblado de interoperabilidad primario cuando se implementa, use el modificador del compilador **/reference** y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="b28f2-116">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="b28f2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b28f2-117">See also</span></span>

- [<span data-ttu-id="b28f2-118">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b28f2-118">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="b28f2-119">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="b28f2-119">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="b28f2-120">[Uso de tipos COM en código administrado](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b28f2-120">[Using COM Types in Managed Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="b28f2-121">Tutorial: Insertar tipos de ensamblados administrados en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b28f2-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="b28f2-122">Importar una biblioteca de tipos como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="b28f2-122">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
