---
title: Instrucción Stop
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
ms.openlocfilehash: 2ef1e2f9045e5509e11557c9fdaf3edd2786b72c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404231"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="fbf26-102">Stop (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbf26-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="fbf26-103">Suspende la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fbf26-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbf26-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="fbf26-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fbf26-105">Remarks</span></span>  
 <span data-ttu-id="fbf26-106">Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fbf26-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="fbf26-107">El uso de la `Stop` instrucción es similar al establecimiento de un punto de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="fbf26-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="fbf26-108">La `Stop` instrucción suspende la ejecución, pero, `End` a diferencia de, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.</span><span class="sxs-lookup"><span data-stu-id="fbf26-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbf26-109">Si la `Stop` instrucción se encuentra en el código que se está ejecutando fuera del entorno de desarrollo integrado (IDE), se invoca al depurador.</span><span class="sxs-lookup"><span data-stu-id="fbf26-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="fbf26-110">Esto es así independientemente de si el código se compiló en modo de depuración o comercial.</span><span class="sxs-lookup"><span data-stu-id="fbf26-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbf26-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbf26-111">Example</span></span>  
 <span data-ttu-id="fbf26-112">En este ejemplo se utiliza la `Stop` instrucción para suspender la ejecución de cada iteración a través del `For...Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="fbf26-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="fbf26-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbf26-113">See also</span></span>

- [<span data-ttu-id="fbf26-114">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fbf26-114">End Statement</span></span>](end-statement.md)
