---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c539f7833c86215a1b0f8102f9fc46419636bc7
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-nowin32manifest-visual-basic"></a><span data-ttu-id="bce8b-102">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce8b-102">-nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="bce8b-103">Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="bce8b-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bce8b-104">Syntax</span></span>  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="bce8b-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bce8b-105">Remarks</span></span>  
 <span data-ttu-id="bce8b-106">Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.</span><span class="sxs-lookup"><span data-stu-id="bce8b-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="bce8b-107">Para obtener más información acerca de la virtualización, vea [la implementación de ClickOnce en Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="bce8b-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="bce8b-108">Para obtener más información acerca de la creación de manifiestos, consulte [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span><span class="sxs-lookup"><span data-stu-id="bce8b-108">For more information about manifest creation, see [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce8b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bce8b-109">See Also</span></span>  
 [<span data-ttu-id="bce8b-110">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bce8b-110">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bce8b-111">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce8b-111">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
