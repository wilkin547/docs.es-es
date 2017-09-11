---
title: -win32icon (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32icon
dev_langs:
- CSharp
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: af5b9c3a44163167d932d378cbac4976e07eacbf
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="win32icon-c-compiler-options"></a><span data-ttu-id="99789-102">/win32icon (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="99789-102">/win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="99789-103">La opción **/win32icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia deseada en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="99789-103">The **/win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99789-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99789-104">Syntax</span></span>  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="99789-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="99789-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="99789-106">El archivo .ico que quiere agregar a su archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="99789-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99789-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99789-107">Remarks</span></span>  
 <span data-ttu-id="99789-108">Se puede crear un archivo .ico con el [compilador de recursos](http://go.microsoft.com/fwlink/?LinkId=148370).</span><span class="sxs-lookup"><span data-stu-id="99789-108">An .ico file can be created with the [Resource Compiler](http://go.microsoft.com/fwlink/?LinkId=148370).</span></span> <span data-ttu-id="99789-109">Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="99789-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="99789-110">Vea [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (para hacer referencia) o [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99789-110">See [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="99789-111">Vea [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="99789-111">See [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="99789-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="99789-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="99789-113">Abra las páginas **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="99789-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="99789-114">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="99789-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="99789-115">Modifique la propiedad **Icono de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="99789-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="99789-116">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="99789-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99789-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99789-117">Example</span></span>  
 <span data-ttu-id="99789-118">Compile `in.cs` y adjunte un archivo .ico `rf.ico` para producir `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="99789-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="99789-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="99789-119">See Also</span></span>  
 <span data-ttu-id="99789-120">[Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="99789-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="99789-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="99789-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

