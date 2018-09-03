---
title: -nowin32manifest (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 3ab52d541c169850f6ae7ba7e7cfded290f890e7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43420624"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="f83a9-102">-nowin32manifest (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="f83a9-102">-nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="f83a9-103">Use la opción **-nowin32manifest** para indicar al compilador que no inserte ningún manifiesto de aplicación en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="f83a9-103">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f83a9-104">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="f83a9-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f83a9-105">Remarks</span></span>  
 <span data-ttu-id="f83a9-106">Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.</span><span class="sxs-lookup"><span data-stu-id="f83a9-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="f83a9-107">En Visual Studio, defina esta opción en la página de **propiedades de la aplicación** seleccionando la opción **Crear aplicación sin manifiesto** en la lista desplegable **Manifiesto**.</span><span class="sxs-lookup"><span data-stu-id="f83a9-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="f83a9-108">Para más información, vea [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="f83a9-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="f83a9-109">Para más información sobre la creación de manifiestos, vea [-win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md) (-win32manifest [Opciones del compilador de C#]).</span><span class="sxs-lookup"><span data-stu-id="f83a9-109">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83a9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f83a9-110">See Also</span></span>  

- [<span data-ttu-id="f83a9-111">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="f83a9-111">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="f83a9-112">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="f83a9-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
