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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957619"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="2a331-102">Stop (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a331-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="2a331-103">Suspende la ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a331-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a331-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a331-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="2a331-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a331-105">Remarks</span></span>  
 <span data-ttu-id="2a331-106">Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a331-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="2a331-107">El uso `Stop` de la instrucción es similar al establecimiento de un punto de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="2a331-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="2a331-108">La `Stop` instrucción suspende la ejecución, pero, a `End`diferencia de, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.</span><span class="sxs-lookup"><span data-stu-id="2a331-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a331-109">Si la `Stop` instrucción se encuentra en el código que se está ejecutando fuera del entorno de desarrollo integrado (IDE), se invoca al depurador.</span><span class="sxs-lookup"><span data-stu-id="2a331-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="2a331-110">Esto es así independientemente de si el código se compiló en modo de depuración o comercial.</span><span class="sxs-lookup"><span data-stu-id="2a331-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a331-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a331-111">Example</span></span>  
 <span data-ttu-id="2a331-112">En este ejemplo se `Stop` utiliza la instrucción para suspender la ejecución de `For...Next` cada iteración a través del bucle.</span><span class="sxs-lookup"><span data-stu-id="2a331-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="2a331-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a331-113">See also</span></span>

- [<span data-ttu-id="2a331-114">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a331-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
