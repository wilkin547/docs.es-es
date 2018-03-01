---
title: "La expresión es un valor y, por lo tanto, no puede ser destino de una asignación"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bec3e2d298160bd0b459dc3b7ef93b94648e439a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="668ed-102">La expresión es un valor y, por lo tanto, no puede ser destino de una asignación</span><span class="sxs-lookup"><span data-stu-id="668ed-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="668ed-103">Una instrucción intenta asignar un valor a una expresión.</span><span class="sxs-lookup"><span data-stu-id="668ed-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="668ed-104">Puede asignar un valor únicamente a una variable de lectura, una propiedad o un elemento de matriz en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="668ed-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="668ed-105">En el ejemplo siguiente se muestra cómo puede producirse este error.</span><span class="sxs-lookup"><span data-stu-id="668ed-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="668ed-106">Pudieron aplicar ejemplos similares a las propiedades y elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="668ed-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="668ed-107">**Acceso indirecto.**</span><span class="sxs-lookup"><span data-stu-id="668ed-107">**Indirect Access.**</span></span> <span data-ttu-id="668ed-108">Acceso indirecto a través de un tipo de valor también puede generar este error.</span><span class="sxs-lookup"><span data-stu-id="668ed-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="668ed-109">Considere el ejemplo de código siguiente, que intenta establecer el valor de <xref:System.Drawing.Point> obteniendo acceso a él indirectamente a través <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="668ed-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="668ed-110">La última instrucción del ejemplo anterior se produce un error porque crea solo una asignación temporal para la <xref:System.Drawing.Point> estructura devuelta por la <xref:System.Windows.Forms.Control.Location%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="668ed-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="668ed-111">Una estructura es un tipo de valor y la estructura temporal no se conserva después de que se ejecuta la instrucción.</span><span class="sxs-lookup"><span data-stu-id="668ed-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="668ed-112">El problema se resuelve declarando y utilizando una variable para <xref:System.Windows.Forms.Control.Location%2A>, que crea una asignación más permanente para la <xref:System.Drawing.Point> estructura.</span><span class="sxs-lookup"><span data-stu-id="668ed-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="668ed-113">En el ejemplo siguiente se muestra código que puede reemplazar la última instrucción del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="668ed-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="668ed-114">**Id. de error:** BC30068</span><span class="sxs-lookup"><span data-stu-id="668ed-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="668ed-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="668ed-115">To correct this error</span></span>  
  
-   <span data-ttu-id="668ed-116">Si la instrucción asigna un valor a una expresión, reemplace la expresión por una variable de escritura única, una propiedad o un elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="668ed-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
-   <span data-ttu-id="668ed-117">Si la instrucción obtiene acceso indirecto a través de un tipo de valor (normalmente una estructura), cree una variable para contener el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="668ed-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
-   <span data-ttu-id="668ed-118">Asigne la estructura adecuada (u otro tipo de valor) a la variable.</span><span class="sxs-lookup"><span data-stu-id="668ed-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
-   <span data-ttu-id="668ed-119">Utilice la variable para tener acceso a la propiedad para asignar un valor.</span><span class="sxs-lookup"><span data-stu-id="668ed-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668ed-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="668ed-120">See Also</span></span>  
 [<span data-ttu-id="668ed-121">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="668ed-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="668ed-122">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="668ed-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="668ed-123">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="668ed-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
