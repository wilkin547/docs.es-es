---
title: -nowin32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: 9e5ad874431028faf17333a9bbd7e9356ef22d55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347892"
---
# <a name="-nowin32manifest-visual-basic"></a><span data-ttu-id="bdaac-102">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdaac-102">-nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="bdaac-103">Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="bdaac-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdaac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdaac-104">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="bdaac-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdaac-105">Remarks</span></span>  
 <span data-ttu-id="bdaac-106">Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.</span><span class="sxs-lookup"><span data-stu-id="bdaac-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="bdaac-107">Para más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="bdaac-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="bdaac-108">Para más información sobre la creación de manifiestos, vea [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span><span class="sxs-lookup"><span data-stu-id="bdaac-108">For more information about manifest creation, see [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdaac-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdaac-109">See also</span></span>

- [<span data-ttu-id="bdaac-110">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdaac-110">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bdaac-111">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdaac-111">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
