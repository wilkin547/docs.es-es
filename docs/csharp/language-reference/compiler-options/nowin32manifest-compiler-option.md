---
description: -nowin32manifest (Opciones del compilador de C#)
title: -nowin32manifest (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 8514ab5b118e320d456d1b7367fab3b463c3607a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125064"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="4cacd-103">-nowin32manifest (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4cacd-103">-nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="4cacd-104">Use la opción **-nowin32manifest** para indicar al compilador que no inserte ningún manifiesto de aplicación en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4cacd-104">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cacd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cacd-105">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="4cacd-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4cacd-106">Remarks</span></span>  
 <span data-ttu-id="4cacd-107">Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.</span><span class="sxs-lookup"><span data-stu-id="4cacd-107">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="4cacd-108">En Visual Studio, defina esta opción en la página de **propiedades de la aplicación** seleccionando la opción **Crear aplicación sin manifiesto** en la lista desplegable **Manifiesto**.</span><span class="sxs-lookup"><span data-stu-id="4cacd-108">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="4cacd-109">Para más información, vea [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="4cacd-109">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="4cacd-110">Para más información sobre la creación de manifiestos, vea [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md) (-win32manifest [Opciones del compilador de C#]).</span><span class="sxs-lookup"><span data-stu-id="4cacd-110">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cacd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cacd-111">See also</span></span>

- [<span data-ttu-id="4cacd-112">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="4cacd-112">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4cacd-113">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="4cacd-113">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
