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
ms.openlocfilehash: 5b62bbfe28bb5aa82605a88a83cf82eff9278807
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168873"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="60e5a-103">-win32icon (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="60e5a-103">-win32icon (C# Compiler Options)</span></span>

<span data-ttu-id="60e5a-104">La opción **-win32icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia esperada en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="60e5a-104">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e5a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60e5a-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="60e5a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="60e5a-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="60e5a-107">El archivo .ico que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="60e5a-107">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60e5a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60e5a-108">Remarks</span></span>  

 <span data-ttu-id="60e5a-109">Se puede crear un archivo .ico con el [compilador de recursos](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="60e5a-109">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="60e5a-110">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="60e5a-110">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="60e5a-111">Vea [-linkresource](./linkresource-compiler-option.md) (para hacer referencia) o [-resource](./resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60e5a-111">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="60e5a-112">Vea [-win32res](./win32res-compiler-option.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="60e5a-112">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="60e5a-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="60e5a-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="60e5a-114">Abra las páginas **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="60e5a-114">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="60e5a-115">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="60e5a-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="60e5a-116">Modifique la propiedad **Icono de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="60e5a-116">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="60e5a-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e5a-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e5a-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60e5a-118">Example</span></span>  

 <span data-ttu-id="60e5a-119">Compile `in.cs` y adjunte un archivo .ico `rf.ico` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="60e5a-119">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="60e5a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="60e5a-120">See also</span></span>

- [<span data-ttu-id="60e5a-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="60e5a-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="60e5a-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="60e5a-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
