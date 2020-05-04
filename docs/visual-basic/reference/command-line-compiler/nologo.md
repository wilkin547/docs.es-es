---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 03dc98c45a894304a67765c3e49cd19bbb089c8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335432"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="9ef5a-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ef5a-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="9ef5a-103">Impide que la pancarta de copyright y los mensajes informativos se muestren durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="9ef5a-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ef5a-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="9ef5a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ef5a-105">Remarks</span></span>  
 <span data-ttu-id="9ef5a-106">Si especifica `-nologo`, el compilador no mostrará una pancarta de copyright.</span><span class="sxs-lookup"><span data-stu-id="9ef5a-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="9ef5a-107">De forma predeterminada, `-nologo` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="9ef5a-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ef5a-108">La opción `-nologo` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9ef5a-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ef5a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ef5a-109">Example</span></span>  
 <span data-ttu-id="9ef5a-110">El siguiente código compila `T2.vb` y no muestra ninguna pancarta de copyright.</span><span class="sxs-lookup"><span data-stu-id="9ef5a-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ef5a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ef5a-111">See also</span></span>

- [<span data-ttu-id="9ef5a-112">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ef5a-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9ef5a-113">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ef5a-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
