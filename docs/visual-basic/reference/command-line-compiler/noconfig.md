---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: b707899c845b6b08e008fe229497f682c930044a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588845"
---
# <a name="-noconfig"></a><span data-ttu-id="8ee48-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="8ee48-102">-noconfig</span></span>
<span data-ttu-id="8ee48-103">Especifica que el compilador debe hacer referencia a los ensamblados de .NET Framework usados o importar automáticamente la `System` y `Microsoft.VisualBasic` espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="8ee48-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee48-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ee48-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ee48-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ee48-105">Remarks</span></span>  
 <span data-ttu-id="8ee48-106">El `-noconfig` opción indica al compilador que no compile con el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="8ee48-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="8ee48-107">El archivo Vbc.rsp hace referencia a los ensamblados de .NET Framework usados e importa el `System` y `Microsoft.VisualBasic` espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="8ee48-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="8ee48-108">El compilador hace referencia implícitamente a los del ensamblado System.dll a menos que el `-nostdlib` se especifica la opción.</span><span class="sxs-lookup"><span data-stu-id="8ee48-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="8ee48-109">El `-nostdlib` opción indica al compilador que no compila con vbc.rsp o referencia al ensamblado System.dll de automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8ee48-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ee48-110">Los ensamblados de Mscorlib.dll y Microsoft.VisualBasic.dll siempre se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8ee48-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="8ee48-111">Puede modificar el archivo Vbc.rsp para especificar opciones de compiladores adicionales que deben incluirse en cada compilación Vbc.exe (excepto cuando se especifica la `-noconfig` opción).</span><span class="sxs-lookup"><span data-stu-id="8ee48-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="8ee48-112">Para obtener más información, consulte [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="8ee48-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="8ee48-113">El compilador procesa las opciones que se pasan a la `vbc` comando por última vez.</span><span class="sxs-lookup"><span data-stu-id="8ee48-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="8ee48-114">Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="8ee48-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ee48-115">El `-noconfig` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="8ee48-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee48-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ee48-116">See also</span></span>

- [<span data-ttu-id="8ee48-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ee48-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="8ee48-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ee48-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8ee48-119">@ (especificar archivo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="8ee48-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="8ee48-120">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ee48-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
