---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: d1307603ebc06b4eb4c3786f1cd2fb432c0cf636
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360467"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="c0a9c-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0a9c-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="c0a9c-103">Impide que la pancarta de copyright y los mensajes informativos se muestren durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="c0a9c-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a9c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0a9c-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="c0a9c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0a9c-105">Remarks</span></span>  
 <span data-ttu-id="c0a9c-106">Si especifica `-nologo`, el compilador no mostrará una pancarta de copyright.</span><span class="sxs-lookup"><span data-stu-id="c0a9c-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="c0a9c-107">De forma predeterminada, `-nologo` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="c0a9c-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0a9c-108">La opción `-nologo` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c0a9c-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a9c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0a9c-109">Example</span></span>  
 <span data-ttu-id="c0a9c-110">El siguiente código compila `T2.vb` y no muestra ninguna pancarta de copyright.</span><span class="sxs-lookup"><span data-stu-id="c0a9c-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0a9c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0a9c-111">See also</span></span>

- [<span data-ttu-id="c0a9c-112">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0a9c-112">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c0a9c-113">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0a9c-113">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
