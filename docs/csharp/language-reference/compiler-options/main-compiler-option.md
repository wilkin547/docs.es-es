---
title: -main (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a6dca6e62dbf69783babf2e16dc4e7c36c6705c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="main-c-compiler-options"></a><span data-ttu-id="5add0-102">/main (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="5add0-102">/main (C# Compiler Options)</span></span>
<span data-ttu-id="5add0-103">Esta opción especifica la clase que contiene el punto de entrada al programa si hay más de una clase que contenga un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="5add0-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5add0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5add0-104">Syntax</span></span>  
  
```console  
/main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="5add0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5add0-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="5add0-106">Tipo que contiene el método **Main**.</span><span class="sxs-lookup"><span data-stu-id="5add0-106">The type that contains the **Main** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5add0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5add0-107">Remarks</span></span>  
 <span data-ttu-id="5add0-108">Si la compilación incluye más de un tipo con un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md), puede especificar el tipo que contiene el método **Main** que quiere usar como punto de entrada en el programa.</span><span class="sxs-lookup"><span data-stu-id="5add0-108">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="5add0-109">Esta opción se usa al compilar un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="5add0-109">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5add0-110">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5add0-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5add0-111">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5add0-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="5add0-112">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="5add0-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="5add0-113">Modifique la propiedad **Objeto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="5add0-113">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="5add0-114">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="5add0-114">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5add0-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5add0-115">Example</span></span>  
 <span data-ttu-id="5add0-116">Compile `t2.cs` y `t3.cs` y especifique que el método **Main** se encuentra en `Test2`:</span><span class="sxs-lookup"><span data-stu-id="5add0-116">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="5add0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5add0-117">See Also</span></span>  
 [<span data-ttu-id="5add0-118">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="5add0-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="5add0-119">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="5add0-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
