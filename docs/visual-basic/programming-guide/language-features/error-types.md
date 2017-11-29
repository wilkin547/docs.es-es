---
title: Tipos de error (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e01ed588d284a475a537a5fcf5ca506d25ca69f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="75588-102">Tipos de error (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75588-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="75588-103">En [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], errores (también denominado *excepciones*) se dividen en tres categorías: errores de sintaxis, errores en tiempo de ejecución y errores lógicos.</span><span class="sxs-lookup"><span data-stu-id="75588-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="75588-104">Errores de sintaxis</span><span class="sxs-lookup"><span data-stu-id="75588-104">Syntax Errors</span></span>  
 <span data-ttu-id="75588-105">*Errores de sintaxis* son aquellos que aparecen mientras escribe el código.</span><span class="sxs-lookup"><span data-stu-id="75588-105">*Syntax errors* are those that appear while you write code.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="75588-106">comprueba el código mientras se escribe en el **Editor de código** ventana y le avisa si comete un error, como se ha escrito mal una palabra o uso incorrecto de un elemento del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="75588-106"> checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="75588-107">Errores de sintaxis son el tipo más común de errores.</span><span class="sxs-lookup"><span data-stu-id="75588-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="75588-108">Puede corregir fácilmente en el entorno de codificación en cuanto se producen.</span><span class="sxs-lookup"><span data-stu-id="75588-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75588-109">El `Option Explicit` instrucción es una forma de evitar errores de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="75588-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="75588-110">Obliga a declarar, por anticipado, todas las variables que se usará en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75588-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="75588-111">Por lo tanto, cuando esas variables se utilizan en el código, cualquier error tipográfico se detecta inmediatamente y se puede corregir.</span><span class="sxs-lookup"><span data-stu-id="75588-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="75588-112">Errores en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="75588-112">Run-Time Errors</span></span>  
 <span data-ttu-id="75588-113">*Errores en tiempo de ejecución* son aquellos que aparecen después de compilar y ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="75588-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="75588-114">Fragmentos de código que puede aparecer son correctos en que tiene no hay errores de sintaxis, pero que no se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="75588-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="75588-115">Por ejemplo, podría escribir correctamente una línea de código para abrir un archivo.</span><span class="sxs-lookup"><span data-stu-id="75588-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="75588-116">Pero si el archivo está dañado, la aplicación no puede realizar la `Open` función y deje de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="75588-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="75588-117">Puede corregir la mayoría de los errores de tiempo de ejecución por volver a escribir el código defectuoso y, a continuación, volver a compilar y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="75588-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="75588-118">Errores lógicos</span><span class="sxs-lookup"><span data-stu-id="75588-118">Logic Errors</span></span>  
 <span data-ttu-id="75588-119">*Errores lógicos* son aquellos que aparecen cuando la aplicación está en uso.</span><span class="sxs-lookup"><span data-stu-id="75588-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="75588-120">Únicamente son mayoría de los resultados inesperada o no deseada a menudo en respuesta a las acciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="75588-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="75588-121">Por ejemplo, una clave mal escrita u otra influencia externa podría hacer que la aplicación deje de funcionar en los parámetros previstos, o por completo.</span><span class="sxs-lookup"><span data-stu-id="75588-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="75588-122">Errores lógicos generalmente son el tipo más difícil de corregir, puesto que no queda siempre claro donde se originan.</span><span class="sxs-lookup"><span data-stu-id="75588-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75588-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="75588-123">See Also</span></span>  
 [<span data-ttu-id="75588-124">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="75588-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="75588-125">Conceptos básicos del depurador</span><span class="sxs-lookup"><span data-stu-id="75588-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
