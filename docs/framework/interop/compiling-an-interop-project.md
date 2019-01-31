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
ms.openlocfilehash: 5a1e6ea8a7a7e6869ca9bc6c1b635f30574ac97f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695199"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="9b572-102">Compilar un proyecto de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9b572-102">Compiling an Interop Project</span></span>

<span data-ttu-id="9b572-103">Los proyectos de interoperabilidad COM que hacen referencia a uno o más ensamblados que contienen tipos COM importados se compilan como cualquier otro proyecto administrado.</span><span class="sxs-lookup"><span data-stu-id="9b572-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="9b572-104">Puede hacer referencia a ensamblados de interoperabilidad en un entorno de desarrollo como Visual Studio, o hacer referencia a ellos cuando se usa un compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9b572-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="9b572-105">En cualquier caso, para compilar correctamente, el ensamblado de interoperabilidad debe estar en el mismo directorio que los demás archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b572-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="9b572-106">Hay dos maneras de hacer referencia a ensamblados de interoperabilidad:</span><span class="sxs-lookup"><span data-stu-id="9b572-106">There are two ways to reference interop assemblies:</span></span>

-   <span data-ttu-id="9b572-107">Tipos de interoperabilidad insertados: a partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] y Visual Studio 2010, se puede indicar al compilador que inserte información de tipos de un ensamblado de interoperabilidad en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="9b572-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="9b572-108">Esta es la técnica recomendada.</span><span class="sxs-lookup"><span data-stu-id="9b572-108">This is the recommended technique.</span></span>

-   <span data-ttu-id="9b572-109">Implementación de ensamblados de interoperabilidad: se puede crear una referencia estándar a un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="9b572-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="9b572-110">En este caso, el ensamblado de interoperabilidad debe implementarse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b572-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="9b572-111">Las diferencias entre estas dos técnicas se explican con más detalle en [Usar tipos COM en código administrado](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9b572-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span></span>

 <span data-ttu-id="9b572-112">La inserción de tipos de interoperabilidad con Visual Studio se describe en [Tutorial: Inserción de información de tipos de los ensamblados de Microsoft Office](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) y [Tutorial: Insertar los tipos de los ensamblados administrados](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span><span class="sxs-lookup"><span data-stu-id="9b572-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) and [Walkthrough: Embedding Types from Managed Assemblies](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>

 <span data-ttu-id="9b572-113">Para hacer referencia a un ensamblado de interoperabilidad con un compilador de línea de comandos e insertar información de tipos en los archivos ejecutables, use el modificador del compilador [/link (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="9b572-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="9b572-114">Las aplicaciones de Visual C++ no pueden insertar información de tipos, pero pueden interoperar con aplicaciones o complementos que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="9b572-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="9b572-115">Para compilar una aplicación que incluye un ensamblado de interoperabilidad primario cuando se implementa, use el modificador del compilador **/reference** y especifique el nombre del ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="9b572-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b572-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b572-116">See also</span></span>

- [<span data-ttu-id="9b572-117">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9b572-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="9b572-118">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="9b572-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="9b572-119">[Uso de tipos COM en código administrado](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9b572-119">[Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span></span>
- <span data-ttu-id="9b572-120">[Tutorial: Inserción de información de tipos de los ensamblados de Microsoft Office](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9b572-120">[Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span></span>
- [<span data-ttu-id="9b572-121">Tutorial: Inserción de tipos de ensamblados administrados</span><span class="sxs-lookup"><span data-stu-id="9b572-121">Walkthrough: Embedding Types from Managed Assemblies</span></span>](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)
- [<span data-ttu-id="9b572-122">Importar una biblioteca de tipos como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="9b572-122">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)