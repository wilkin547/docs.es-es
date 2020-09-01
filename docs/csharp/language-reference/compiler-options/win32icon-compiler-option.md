---
description: -win32icon (Opciones del compilador de C#)
title: -win32icon (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 76a54f9011371492bdc15f15c3e40d51082deed3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138415"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="44b73-103">-win32icon (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="44b73-103">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="44b73-104">La opción **-win32icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia esperada en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="44b73-104">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44b73-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44b73-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="44b73-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="44b73-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="44b73-107">El archivo .ico que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="44b73-107">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44b73-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44b73-108">Remarks</span></span>  
 <span data-ttu-id="44b73-109">Se puede crear un archivo .ico con el [compilador de recursos](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="44b73-109">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="44b73-110">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="44b73-110">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="44b73-111">Vea [-linkresource](./linkresource-compiler-option.md) (para hacer referencia) o [-resource](./resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44b73-111">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="44b73-112">Vea [-win32res](./win32res-compiler-option.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="44b73-112">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="44b73-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44b73-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="44b73-114">Abra las páginas **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="44b73-114">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="44b73-115">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="44b73-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="44b73-116">Modifique la propiedad **Icono de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="44b73-116">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="44b73-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="44b73-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44b73-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44b73-118">Example</span></span>  
 <span data-ttu-id="44b73-119">Compile `in.cs` y adjunte un archivo .ico `rf.ico` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="44b73-119">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="44b73-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="44b73-120">See also</span></span>

- [<span data-ttu-id="44b73-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="44b73-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="44b73-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="44b73-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
