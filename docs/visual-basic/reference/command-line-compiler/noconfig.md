---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: bce2d98a8915e80cdecd7b67029b0c872cf70140
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650847"
---
# <a name="-noconfig"></a><span data-ttu-id="483e5-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="483e5-102">-noconfig</span></span>
<span data-ttu-id="483e5-103">Especifica que el compilador no debe automáticamente hacer referencia utilizados habitualmente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados o importar la `System` y `Microsoft.VisualBasic` los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="483e5-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="483e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="483e5-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="483e5-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="483e5-105">Remarks</span></span>  
 <span data-ttu-id="483e5-106">El `-noconfig` opción indica al compilador que no compile con el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="483e5-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="483e5-107">El archivo Vbc.rsp hace referencia utilizados habitualmente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados e importaciones el `System` y `Microsoft.VisualBasic` los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="483e5-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="483e5-108">El compilador hace referencia implícitamente a los del ensamblado System.dll a menos que el `-nostdlib` se especifica la opción.</span><span class="sxs-lookup"><span data-stu-id="483e5-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="483e5-109">El `-nostdlib` opción indica al compilador que no compila con Vbc.rsp o automáticamente hacen referencia al ensamblado de System.dll.</span><span class="sxs-lookup"><span data-stu-id="483e5-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="483e5-110">Siempre hacen referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="483e5-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="483e5-111">Puede modificar el archivo Vbc.rsp para especificar opciones adicionales del compilador que deben incluirse en cada compilación Vbc.exe (excepto cuando se especifica la `-noconfig` opción).</span><span class="sxs-lookup"><span data-stu-id="483e5-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="483e5-112">Para obtener más información, consulte [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="483e5-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="483e5-113">El compilador procesa las opciones que se pasan a la `vbc` último comando.</span><span class="sxs-lookup"><span data-stu-id="483e5-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="483e5-114">Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="483e5-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="483e5-115">El `-noconfig` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="483e5-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483e5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="483e5-116">See Also</span></span>  
 [<span data-ttu-id="483e5-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="483e5-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [<span data-ttu-id="483e5-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="483e5-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="483e5-119">@ (especificar archivo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="483e5-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [<span data-ttu-id="483e5-120">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="483e5-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
