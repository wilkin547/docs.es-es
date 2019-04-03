---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: c1824e4a086ecdd4b6a776bd6894f6e003d02867
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822562"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="1b088-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b088-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="1b088-103">Suprime la presentación de la pancarta de copyright y mensajes informativos durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="1b088-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b088-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b088-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="1b088-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b088-105">Remarks</span></span>  
 <span data-ttu-id="1b088-106">Si especifica `-nologo`, el compilador no mostrará un aviso de copyright.</span><span class="sxs-lookup"><span data-stu-id="1b088-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="1b088-107">De forma predeterminada, `-nologo` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="1b088-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b088-108">El `-nologo` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="1b088-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b088-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b088-109">Example</span></span>  
 <span data-ttu-id="1b088-110">El siguiente código compila `T2.vb` y no se muestra un aviso de copyright.</span><span class="sxs-lookup"><span data-stu-id="1b088-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b088-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b088-111">See also</span></span>

- [<span data-ttu-id="1b088-112">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b088-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1b088-113">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b088-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
