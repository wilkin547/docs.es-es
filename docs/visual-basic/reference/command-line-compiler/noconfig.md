---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964394"
---
# <a name="-noconfig"></a><span data-ttu-id="2bc54-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="2bc54-102">-noconfig</span></span>
<span data-ttu-id="2bc54-103">Especifica que el compilador no debe hacer referencia automáticamente a los ensamblados de `System` .NET Framework `Microsoft.VisualBasic` usados normalmente o importar los espacios de nombres y.</span><span class="sxs-lookup"><span data-stu-id="2bc54-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bc54-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="2bc54-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2bc54-105">Remarks</span></span>  
 <span data-ttu-id="2bc54-106">La `-noconfig` opción indica al compilador que no compile con el archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe.</span><span class="sxs-lookup"><span data-stu-id="2bc54-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="2bc54-107">El archivo Vbc. rsp hace referencia a los ensamblados de .NET Framework usados `System` comúnmente `Microsoft.VisualBasic` e importa los espacios de nombres y.</span><span class="sxs-lookup"><span data-stu-id="2bc54-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="2bc54-108">El compilador hace referencia implícitamente al ensamblado System `-nostdlib` . dll a menos que se especifique la opción.</span><span class="sxs-lookup"><span data-stu-id="2bc54-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="2bc54-109">La `-nostdlib` opción indica al compilador que no compile con VBC. rsp ni haga referencia automáticamente al ensamblado System. dll.</span><span class="sxs-lookup"><span data-stu-id="2bc54-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2bc54-110">Siempre se hace referencia a los ensamblados mscorlib. dll y Microsoft. VisualBasic. dll.</span><span class="sxs-lookup"><span data-stu-id="2bc54-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="2bc54-111">Puede modificar el archivo Vbc. RSP para especificar opciones de compilador adicionales que deben incluirse en todas las compilaciones de VBC. exe `-noconfig` (excepto cuando se especifica la opción).</span><span class="sxs-lookup"><span data-stu-id="2bc54-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="2bc54-112">Para obtener más información, consulte [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="2bc54-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="2bc54-113">El compilador procesa las opciones que `vbc` se pasan al comando en último lugar.</span><span class="sxs-lookup"><span data-stu-id="2bc54-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="2bc54-114">Por lo tanto, cualquier opción de la línea de comandos invalida el valor de la misma opción en el archivo Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="2bc54-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2bc54-115">La `-noconfig` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2bc54-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc54-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bc54-116">See also</span></span>

- [<span data-ttu-id="2bc54-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bc54-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="2bc54-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2bc54-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2bc54-119">@ (especificar archivo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="2bc54-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="2bc54-120">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bc54-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
