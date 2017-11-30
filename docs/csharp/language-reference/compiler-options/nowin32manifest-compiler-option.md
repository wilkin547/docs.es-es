---
title: -nowin32manifest (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1e0d4697e0e14c84c4bc642521cf4f9cdf6a4ed6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nowin32manifest-c-compiler-options"></a><span data-ttu-id="cbe30-102">/nowin32manifest (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="cbe30-102">/nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="cbe30-103">Use la opción **/nowin32manifest** para indicar al compilador que no inserte ningún manifiesto de aplicación en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="cbe30-103">Use the **/nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbe30-104">Syntax</span></span>  
  
```console  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="cbe30-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbe30-105">Remarks</span></span>  
 <span data-ttu-id="cbe30-106">Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.</span><span class="sxs-lookup"><span data-stu-id="cbe30-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="cbe30-107">En Visual Studio, defina esta opción en la página de **propiedades de la aplicación** seleccionando la opción **Crear aplicación sin manifiesto** en la lista desplegable **Manifiesto**.</span><span class="sxs-lookup"><span data-stu-id="cbe30-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="cbe30-108">Para obtener más información, consulte [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="cbe30-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="cbe30-109">Para obtener más información sobre la creación de manifiestos, consulte [/win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md) (/win32manifest [Opciones del compilador de C#]).</span><span class="sxs-lookup"><span data-stu-id="cbe30-109">For more information about manifest creation, see [/win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe30-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbe30-110">See Also</span></span>  
 [<span data-ttu-id="cbe30-111">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="cbe30-111">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="cbe30-112">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="cbe30-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
