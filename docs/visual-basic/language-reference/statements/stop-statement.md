---
title: Stop (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 590ac27ebab881353a69077aabdf7a2def3396a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967854"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="e8a6d-102">Stop (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8a6d-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="e8a6d-103">Suspende la ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8a6d-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a6d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8a6d-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="e8a6d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8a6d-105">Remarks</span></span>  
 <span data-ttu-id="e8a6d-106">Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8a6d-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="e8a6d-107">Mediante el `Stop` instrucción es similar a la configuración de un punto de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="e8a6d-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="e8a6d-108">El `Stop` instrucción suspende la ejecución, pero, a diferencia `End`, no cierre los archivos ni borrar las variables, a menos que se encuentre en un archivo ejecutable compilado (.exe).</span><span class="sxs-lookup"><span data-stu-id="e8a6d-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8a6d-109">Si el `Stop` instrucción se encuentra en el código que se ejecuta fuera del entorno de desarrollo integrado (IDE), se invoca el depurador.</span><span class="sxs-lookup"><span data-stu-id="e8a6d-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="e8a6d-110">Esto es cierto independientemente de si se ha compilado el código en modo de depuración o comercial.</span><span class="sxs-lookup"><span data-stu-id="e8a6d-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8a6d-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8a6d-111">Example</span></span>  
 <span data-ttu-id="e8a6d-112">Este ejemplo se usa el `Stop` instrucción suspenda la ejecución para cada iteración a través de la `For...Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="e8a6d-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="e8a6d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8a6d-113">See also</span></span>
- [<span data-ttu-id="e8a6d-114">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8a6d-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
