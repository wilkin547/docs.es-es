---
description: 'Más información acerca de: instrucción Stop (Visual Basic)'
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
ms.openlocfilehash: 1e25eb88d1b85f38a53023dfb7dfbc877f498e5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741086"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="7729e-103">Stop (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7729e-103">Stop Statement (Visual Basic)</span></span>

<span data-ttu-id="7729e-104">Suspende la ejecución.</span><span class="sxs-lookup"><span data-stu-id="7729e-104">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7729e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7729e-105">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="7729e-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7729e-106">Remarks</span></span>  

 <span data-ttu-id="7729e-107">Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución.</span><span class="sxs-lookup"><span data-stu-id="7729e-107">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="7729e-108">El uso de la `Stop` instrucción es similar al establecimiento de un punto de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="7729e-108">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="7729e-109">La `Stop` instrucción suspende la ejecución, pero, `End` a diferencia de, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.</span><span class="sxs-lookup"><span data-stu-id="7729e-109">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7729e-110">Si la `Stop` instrucción se encuentra en el código que se está ejecutando fuera del entorno de desarrollo integrado (IDE), se invoca al depurador.</span><span class="sxs-lookup"><span data-stu-id="7729e-110">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="7729e-111">Esto es así independientemente de si el código se compiló en modo de depuración o comercial.</span><span class="sxs-lookup"><span data-stu-id="7729e-111">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7729e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7729e-112">Example</span></span>  

 <span data-ttu-id="7729e-113">En este ejemplo se utiliza la `Stop` instrucción para suspender la ejecución de cada iteración a través del `For...Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="7729e-113">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="7729e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7729e-114">See also</span></span>

- [<span data-ttu-id="7729e-115">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7729e-115">End Statement</span></span>](end-statement.md)
