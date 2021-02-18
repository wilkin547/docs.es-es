---
description: Mas información sobre -nologo (Visual Basic)
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 370889fbd5d4e499ba27ff8bee4adc16a7a71876
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434893"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="25d51-103">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25d51-103">-nologo (Visual Basic)</span></span>

<span data-ttu-id="25d51-104">Impide que la pancarta de copyright y los mensajes informativos se muestren durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="25d51-104">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25d51-105">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="25d51-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25d51-106">Remarks</span></span>  

 <span data-ttu-id="25d51-107">Si especifica `-nologo`, el compilador no mostrará una pancarta de copyright.</span><span class="sxs-lookup"><span data-stu-id="25d51-107">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="25d51-108">De forma predeterminada, `-nologo` no está en vigor.</span><span class="sxs-lookup"><span data-stu-id="25d51-108">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25d51-109">La opción `-nologo` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="25d51-109">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25d51-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25d51-110">Example</span></span>  

 <span data-ttu-id="25d51-111">El siguiente código compila `T2.vb` y no muestra ninguna pancarta de copyright.</span><span class="sxs-lookup"><span data-stu-id="25d51-111">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="25d51-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="25d51-112">See also</span></span>

- [<span data-ttu-id="25d51-113">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25d51-113">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="25d51-114">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="25d51-114">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
