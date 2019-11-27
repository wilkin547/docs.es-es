---
title: Stop (Instrucción)
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
ms.openlocfilehash: 497c5f207b2228412411cc3eb01976564f82bd6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346465"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="efa97-102">Stop (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efa97-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="efa97-103">Suspende la ejecución.</span><span class="sxs-lookup"><span data-stu-id="efa97-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efa97-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="efa97-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efa97-105">Remarks</span></span>  
 <span data-ttu-id="efa97-106">Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución.</span><span class="sxs-lookup"><span data-stu-id="efa97-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="efa97-107">El uso de la instrucción `Stop` es similar al establecimiento de un punto de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="efa97-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="efa97-108">La instrucción `Stop` suspende la ejecución, pero a diferencia de `End`, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.</span><span class="sxs-lookup"><span data-stu-id="efa97-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efa97-109">Si se encuentra la instrucción `Stop` en el código que se está ejecutando fuera del entorno de desarrollo integrado (IDE), se invoca al depurador.</span><span class="sxs-lookup"><span data-stu-id="efa97-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="efa97-110">Esto es así independientemente de si el código se compiló en modo de depuración o comercial.</span><span class="sxs-lookup"><span data-stu-id="efa97-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efa97-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efa97-111">Example</span></span>  
 <span data-ttu-id="efa97-112">En este ejemplo se utiliza la instrucción `Stop` para suspender la ejecución de cada iteración a través del bucle `For...Next`.</span><span class="sxs-lookup"><span data-stu-id="efa97-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="efa97-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="efa97-113">See also</span></span>

- [<span data-ttu-id="efa97-114">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="efa97-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
