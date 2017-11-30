---
title: -win32icon (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3f9419470d2f00a9f69aae24e925fea53d90cf10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon-c-compiler-options"></a><span data-ttu-id="cc5e7-102">/win32icon (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="cc5e7-102">/win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="cc5e7-103">La opción **/win32icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia deseada en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-103">The **/win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc5e7-104">Syntax</span></span>  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc5e7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cc5e7-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="cc5e7-106">El archivo .ico que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc5e7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc5e7-107">Remarks</span></span>  
 <span data-ttu-id="cc5e7-108">Se puede crear un archivo .ico con el [compilador de recursos](http://go.microsoft.com/fwlink/?LinkId=148370).</span><span class="sxs-lookup"><span data-stu-id="cc5e7-108">An .ico file can be created with the [Resource Compiler](http://go.microsoft.com/fwlink/?LinkId=148370).</span></span> <span data-ttu-id="cc5e7-109">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="cc5e7-110">Vea [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (para hacer referencia) o [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-110">See [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="cc5e7-111">Vea [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-111">See [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="cc5e7-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc5e7-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="cc5e7-113">Abra las páginas **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="cc5e7-114">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="cc5e7-115">Modifique la propiedad **Icono de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="cc5e7-116">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc5e7-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc5e7-117">Example</span></span>  
 <span data-ttu-id="cc5e7-118">Compile `in.cs` y adjunte un archivo .ico `rf.ico` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="cc5e7-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc5e7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc5e7-119">See Also</span></span>  
 [<span data-ttu-id="cc5e7-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="cc5e7-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="cc5e7-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="cc5e7-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
