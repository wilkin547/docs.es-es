---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964376"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="0a754-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a754-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="0a754-103">Suprime la presentación de la pancarta de copyright y los mensajes informativos durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="0a754-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a754-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a754-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="0a754-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a754-105">Remarks</span></span>  
 <span data-ttu-id="0a754-106">Si especifica `-nologo`, el compilador no mostrará un titular de copyright.</span><span class="sxs-lookup"><span data-stu-id="0a754-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="0a754-107">De forma predeterminada, `-nologo` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="0a754-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a754-108">La `-nologo` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0a754-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a754-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a754-109">Example</span></span>  
 <span data-ttu-id="0a754-110">En el código siguiente se compila `T2.vb` y no se muestra un banner de copyright.</span><span class="sxs-lookup"><span data-stu-id="0a754-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a754-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a754-111">See also</span></span>

- [<span data-ttu-id="0a754-112">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a754-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0a754-113">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a754-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
