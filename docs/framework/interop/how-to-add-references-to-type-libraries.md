---
title: Procedimiento para agregar referencias a bibliotecas de tipos
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a666c0e079fb30ecdd32aad64f44434d8253acf4
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971900"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="9fb36-102">Procedimiento para agregar referencias a bibliotecas de tipos</span><span class="sxs-lookup"><span data-stu-id="9fb36-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="9fb36-103">Visual Studio genera un ensamblado de interoperabilidad que contiene metadatos cuando se agrega una referencia a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="9fb36-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="9fb36-104">Si el ensamblado de interoperabilidad principal está disponible, Visual Studio usa el ensamblado existente antes de generar un nuevo ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="9fb36-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="9fb36-105">Para agregar una referencia a una biblioteca de tipos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9fb36-105">To add a reference to a type library in Visual Studio</span></span>  
  
1. <span data-ttu-id="9fb36-106">Instale el archivo COM DLL o EXE en su equipo, a menos que un archivo Setup.exe de Windows realice la instalación automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9fb36-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2. <span data-ttu-id="9fb36-107">Seleccione **Proyecto**, **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="9fb36-107">Choose **Project**, **Add Reference**.</span></span>  
  
3. <span data-ttu-id="9fb36-108">En el Administrador de referencias, elija **COM**.</span><span class="sxs-lookup"><span data-stu-id="9fb36-108">In the Reference Manager, choose **COM**.</span></span>  
  
4. <span data-ttu-id="9fb36-109">Seleccione la biblioteca de tipos en la lista o busque el archivo .tlb.</span><span class="sxs-lookup"><span data-stu-id="9fb36-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5. <span data-ttu-id="9fb36-110">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9fb36-110">Choose **OK**.</span></span>  
  
6. <span data-ttu-id="9fb36-111">En el Explorador de soluciones, abra el menú contextual de la referencia que acaba de agregar y elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9fb36-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7. <span data-ttu-id="9fb36-112">En la ventana **Propiedades**, asegúrese de que el valor de la propiedad **Incrustar tipos de interoperabilidad** es **True**.</span><span class="sxs-lookup"><span data-stu-id="9fb36-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="9fb36-113">Esto hace que Visual Studio incruste información sobre los tipos COM en los ejecutables, eliminando así la necesidad de implementar ensamblados de interoperabilidad principales con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9fb36-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fb36-114">Las opciones de los menús y cuadros de diálogo puede variar según la versión de Visual Studio que esté usando.</span><span class="sxs-lookup"><span data-stu-id="9fb36-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="9fb36-115">Para agregar una referencia a una biblioteca de tipos para la compilación en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9fb36-115">To add a reference to a type library for command-line compilation</span></span>  
  
1. <span data-ttu-id="9fb36-116">Genere un ensamblado de interoperabilidad tal y como se describe en [Cómo: Generar ensamblados de interoperabilidad a partir de bibliotecas de tipos](how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="9fb36-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2. <span data-ttu-id="9fb36-117">Use la opción de compilador [/link (Opciones del compilador de C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) con el nombre del ensamblado de interoperabilidad para insertar la información sobre los tipos COM en los archivos ejecutable.</span><span class="sxs-lookup"><span data-stu-id="9fb36-117">Use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb36-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fb36-118">See also</span></span>

- [<span data-ttu-id="9fb36-119">Importar una biblioteca de tipos como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="9fb36-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="9fb36-120">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9fb36-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="9fb36-121">Tutorial: Insertar tipos de ensamblados administrados en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9fb36-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md) 
- [<span data-ttu-id="9fb36-122">/link (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="9fb36-122">/link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="9fb36-123">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fb36-123">/link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
