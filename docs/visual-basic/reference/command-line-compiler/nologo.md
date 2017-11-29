---
title: /nologo (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c2c7e7a111a3763d7463f67c2d984955da33bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nologo-visual-basic"></a><span data-ttu-id="54862-102">/nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54862-102">/nologo (Visual Basic)</span></span>
<span data-ttu-id="54862-103">Suprime la presentación de la pancarta de copyright y mensajes informativos durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="54862-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54862-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54862-104">Syntax</span></span>  
  
```  
/nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="54862-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54862-105">Remarks</span></span>  
 <span data-ttu-id="54862-106">Si especifica `/nologo`, el compilador no mostrará un aviso de copyright.</span><span class="sxs-lookup"><span data-stu-id="54862-106">If you specify `/nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="54862-107">De forma predeterminada, `/nologo` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="54862-107">By default, `/nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54862-108">El `/nologo` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="54862-108">The `/nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54862-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54862-109">Example</span></span>  
 <span data-ttu-id="54862-110">El siguiente código compila `T2.vb` y no se muestra una pancarta de copyright.</span><span class="sxs-lookup"><span data-stu-id="54862-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="54862-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="54862-111">See Also</span></span>  
 [<span data-ttu-id="54862-112">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54862-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="54862-113">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="54862-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
