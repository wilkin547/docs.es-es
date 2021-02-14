---
description: 'Más información sobre: tipos de errores (Visual Basic)'
title: Tipos de errores
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: cc4fce5e0ce77a4e402ba832fd6f4e36e6feed07
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423776"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="37641-103">Tipos de error (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37641-103">Error Types (Visual Basic)</span></span>

<span data-ttu-id="37641-104">En Visual Basic, los errores se dividen en una de estas tres categorías: errores de sintaxis, errores en tiempo de ejecución y errores lógicos.</span><span class="sxs-lookup"><span data-stu-id="37641-104">In Visual Basic, errors fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>

## <a name="syntax-errors"></a><span data-ttu-id="37641-105">Errores de sintaxis</span><span class="sxs-lookup"><span data-stu-id="37641-105">Syntax Errors</span></span>

 <span data-ttu-id="37641-106">Los *errores de sintaxis* son los que aparecen mientras se escribe código.</span><span class="sxs-lookup"><span data-stu-id="37641-106">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="37641-107">Si usa Visual Studio, Visual Basic comprueba el código a medida que lo escribe en la ventana del **Editor de código** y le alerta Si comete un error, como la escritura incorrecta de una palabra o el uso de un elemento del lenguaje de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="37641-107">If you're using Visual Studio, Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="37641-108">Si se compila desde la línea de comandos, Visual Basic muestra un error del compilador con información sobre el error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="37641-108">If you compile from the command line, Visual Basic displays a compiler error with information about the syntax error.</span></span> <span data-ttu-id="37641-109">Los errores de sintaxis son el tipo más común de errores.</span><span class="sxs-lookup"><span data-stu-id="37641-109">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="37641-110">Puede corregirlas fácilmente en el entorno de codificación en cuanto se produzcan.</span><span class="sxs-lookup"><span data-stu-id="37641-110">You can fix them easily in the coding environment as soon as they occur.</span></span>

> [!NOTE]
> <span data-ttu-id="37641-111">La `Option Explicit` instrucción es un medio para evitar errores de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="37641-111">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="37641-112">Obliga a declarar, de antemano, todas las variables que se van a usar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37641-112">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="37641-113">Por lo tanto, cuando esas variables se usan en el código, los errores tipográficos se detectan inmediatamente y se pueden corregir.</span><span class="sxs-lookup"><span data-stu-id="37641-113">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>

## <a name="run-time-errors"></a><span data-ttu-id="37641-114">Errores de Run-Time</span><span class="sxs-lookup"><span data-stu-id="37641-114">Run-Time Errors</span></span>

 <span data-ttu-id="37641-115">Los *errores en tiempo de ejecución* son aquellos que aparecen solo después de compilar y ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="37641-115">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="37641-116">Estos incluyen código que puede parecer correcto en que no tiene errores de sintaxis, pero que no se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="37641-116">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="37641-117">Por ejemplo, puede escribir correctamente una línea de código para abrir un archivo.</span><span class="sxs-lookup"><span data-stu-id="37641-117">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="37641-118">Pero si el archivo no existe, la aplicación no puede abrir el archivo y produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="37641-118">But if the file does not exist, the application cannot open the file, and it throws an exception.</span></span> <span data-ttu-id="37641-119">Puede corregir la mayoría de los errores en tiempo de ejecución volviendo a escribir el código defectuoso o usando el [control de excepciones](../../language-reference/statements/try-catch-finally-statement.md)y, a continuación, volviendo a compilarlo y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="37641-119">You can fix most run-time errors by rewriting the faulty code or by using [exception handling](../../language-reference/statements/try-catch-finally-statement.md), and then recompiling and rerunning it.</span></span>
  
## <a name="logic-errors"></a><span data-ttu-id="37641-120">Errores lógicos</span><span class="sxs-lookup"><span data-stu-id="37641-120">Logic Errors</span></span>

 <span data-ttu-id="37641-121">Los *errores lógicos* son los que aparecen una vez que la aplicación está en uso.</span><span class="sxs-lookup"><span data-stu-id="37641-121">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="37641-122">Suelen ser suposiciones defectuosas realizadas por el desarrollador o resultados no deseados o inesperados en respuesta a las acciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="37641-122">They are most often faulty assumptions made by the developer, or unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="37641-123">Por ejemplo, una clave mal escrita podría proporcionar información incorrecta a un método, o puede suponer que siempre se suministra un valor válido a un método cuando no es el caso.</span><span class="sxs-lookup"><span data-stu-id="37641-123">For example, a mistyped key might provide incorrect information to a method, or you may assume that a valid value is always supplied to a method when that is not the case.</span></span> <span data-ttu-id="37641-124">Aunque los errores lógicos se pueden controlar mediante el [control de excepciones](../../language-reference/statements/try-catch-finally-statement.md) (por ejemplo, al comprobar si un argumento es `Nothing` e iniciar un <xref:System.ArgumentNullException> ), lo más habitual es que se solucionen corrigiendo el error en la lógica y volviendo a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37641-124">Although logic errors can be handled by using [exception handling](../../language-reference/statements/try-catch-finally-statement.md) (for example, by testing whether an argument is `Nothing` and throwing an <xref:System.ArgumentNullException>), most commonly they should be addressed by correcting the error in logic and recompiling the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="37641-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="37641-125">See also</span></span>

- [<span data-ttu-id="37641-126">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="37641-126">Try...Catch...Finally Statement</span></span>](../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="37641-127">Conceptos básicos del depurador</span><span class="sxs-lookup"><span data-stu-id="37641-127">Debugger Basics</span></span>](/visualstudio/debugger/debugger-feature-tour)
