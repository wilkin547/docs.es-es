---
title: "Stop (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b7f04214234837a86bf0c77c0d7b6934e2babd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="c2254-102">Stop (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2254-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="c2254-103">Suspende la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c2254-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2254-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2254-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="c2254-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2254-105">Remarks</span></span>  
 <span data-ttu-id="c2254-106">Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c2254-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="c2254-107">Mediante el `Stop` instrucción es similar a establecer un punto de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="c2254-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="c2254-108">El `Stop` instrucción suspende la ejecución, pero, a diferencia `End`, no cierra ningún archivo ni borra variables, a menos que se encuentra en un archivo ejecutable compilado (.exe).</span><span class="sxs-lookup"><span data-stu-id="c2254-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2254-109">Si el `Stop` instrucción se encuentra en código que se ejecuta fuera del entorno de desarrollo integrado (IDE), se invoca el depurador.</span><span class="sxs-lookup"><span data-stu-id="c2254-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="c2254-110">Esto es cierto independientemente de si el código se compiló en modo de depuración o minorista.</span><span class="sxs-lookup"><span data-stu-id="c2254-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2254-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2254-111">Example</span></span>  
 <span data-ttu-id="c2254-112">Este ejemplo se utiliza la `Stop` instrucción para suspender la ejecución para cada iteración a través de la `For...Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="c2254-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c2254-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2254-113">See Also</span></span>  
 [<span data-ttu-id="c2254-114">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c2254-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
