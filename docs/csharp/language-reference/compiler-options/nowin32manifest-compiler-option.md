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
ms.openlocfilehash: 13bbee66901149d54632d9b164431f8898cdf52e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91194003"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="cf628-103">-nowin32manifest (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="cf628-103">-nowin32manifest (C# Compiler Options)</span></span>

<span data-ttu-id="cf628-104">Use la opción **-nowin32manifest** para indicar al compilador que no inserte ningún manifiesto de aplicación en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="cf628-104">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf628-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf628-105">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="cf628-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf628-106">Remarks</span></span>  

 <span data-ttu-id="cf628-107">Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.</span><span class="sxs-lookup"><span data-stu-id="cf628-107">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="cf628-108">En Visual Studio, defina esta opción en la página de **propiedades de la aplicación** seleccionando la opción **Crear aplicación sin manifiesto** en la lista desplegable **Manifiesto**.</span><span class="sxs-lookup"><span data-stu-id="cf628-108">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="cf628-109">Para más información, vea [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="cf628-109">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="cf628-110">Para más información sobre la creación de manifiestos, vea [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md) (-win32manifest [Opciones del compilador de C#]).</span><span class="sxs-lookup"><span data-stu-id="cf628-110">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf628-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf628-111">See also</span></span>

- [<span data-ttu-id="cf628-112">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="cf628-112">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="cf628-113">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="cf628-113">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
