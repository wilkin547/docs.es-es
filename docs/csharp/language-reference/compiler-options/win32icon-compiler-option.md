---
title: -win32icon (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: f3df92d8d0b0135eac1a055afafffa0015fecc2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606282"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="a014e-102">-win32icon (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="a014e-102">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="a014e-103">La opción **-win32icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia esperada en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="a014e-103">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a014e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a014e-104">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="a014e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a014e-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="a014e-106">El archivo .ico que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="a014e-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a014e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a014e-107">Remarks</span></span>  
 <span data-ttu-id="a014e-108">Se puede crear un archivo .ico con el [compilador de recursos](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="a014e-108">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="a014e-109">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="a014e-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="a014e-110">Vea [-linkresource](./linkresource-compiler-option.md) (para hacer referencia) o [-resource](./resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a014e-110">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="a014e-111">Vea [-win32res](./win32res-compiler-option.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="a014e-111">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a014e-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a014e-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="a014e-113">Abra las páginas **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a014e-113">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="a014e-114">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="a014e-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="a014e-115">Modifique la propiedad **Icono de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="a014e-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="a014e-116">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="a014e-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a014e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a014e-117">Example</span></span>  
 <span data-ttu-id="a014e-118">Compile `in.cs` y adjunte un archivo .ico `rf.ico` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="a014e-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a014e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a014e-119">See also</span></span>

- [<span data-ttu-id="a014e-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="a014e-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a014e-121">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="a014e-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
