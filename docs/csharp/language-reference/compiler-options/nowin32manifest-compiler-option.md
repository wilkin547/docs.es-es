---
title: -nowin32manifest (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowin32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
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
ms.openlocfilehash: 8314fd661ccce968238b480b54847abf7cbece74
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="nowin32manifest-c-compiler-options"></a><span data-ttu-id="267ef-102">/nowin32manifest (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="267ef-102">/nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="267ef-103">Use la opción **/nowin32manifest** para indicar al compilador que no inserte ningún manifiesto de aplicación en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="267ef-103">Use the **/nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="267ef-104">Syntax</span></span>  
  
```console  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="267ef-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="267ef-105">Remarks</span></span>  
 <span data-ttu-id="267ef-106">Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.</span><span class="sxs-lookup"><span data-stu-id="267ef-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="267ef-107">En Visual Studio, defina esta opción en la página de **propiedades de la aplicación** seleccionando la opción **Crear aplicación sin manifiesto** en la lista desplegable **Manifiesto**.</span><span class="sxs-lookup"><span data-stu-id="267ef-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="267ef-108">Para obtener más información, consulte [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="267ef-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="267ef-109">Para obtener más información sobre la creación de manifiestos, consulte [/win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md) (/win32manifest [Opciones del compilador de C#]).</span><span class="sxs-lookup"><span data-stu-id="267ef-109">For more information about manifest creation, see [/win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267ef-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="267ef-110">See Also</span></span>  
 <span data-ttu-id="267ef-111">[Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="267ef-111">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="267ef-112">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="267ef-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

