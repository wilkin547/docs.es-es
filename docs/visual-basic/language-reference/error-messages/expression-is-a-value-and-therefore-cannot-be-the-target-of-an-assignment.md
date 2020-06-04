---
title: La expresión es un valor y, por lo tanto, no puede ser destino de una asignación
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 9e4dbaf2f2800454c673cd58ddec4cf0f6e5c6b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409513"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="cda97-102">La expresión es un valor y, por lo tanto, no puede ser destino de una asignación</span><span class="sxs-lookup"><span data-stu-id="cda97-102">Expression is a value and therefore cannot be the target of an assignment</span></span>

<span data-ttu-id="cda97-103">Una instrucción intenta asignar un valor a una expresión.</span><span class="sxs-lookup"><span data-stu-id="cda97-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="cda97-104">Solo puede asignar un valor a una variable, propiedad o elemento de matriz de escritura en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cda97-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="cda97-105">En el ejemplo siguiente se muestra cómo se puede producir este error.</span><span class="sxs-lookup"><span data-stu-id="cda97-105">The following example illustrates how this error can occur.</span></span>

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

<span data-ttu-id="cda97-106">Pueden aplicarse ejemplos similares a las propiedades y los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cda97-106">Similar examples could apply to properties and array elements.</span></span>

<span data-ttu-id="cda97-107">**Acceso indirecto.**</span><span class="sxs-lookup"><span data-stu-id="cda97-107">**Indirect Access.**</span></span> <span data-ttu-id="cda97-108">El acceso indirecto a través de un tipo de valor también puede generar este error.</span><span class="sxs-lookup"><span data-stu-id="cda97-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="cda97-109">Considere el siguiente ejemplo de código, que intenta establecer el valor de accediendo <xref:System.Drawing.Point> indirectamente a través de <xref:System.Windows.Forms.Control.Location%2A> .</span><span class="sxs-lookup"><span data-stu-id="cda97-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

<span data-ttu-id="cda97-110">La última instrucción del ejemplo anterior produce un error porque solo crea una asignación temporal para la <xref:System.Drawing.Point> estructura devuelta por la <xref:System.Windows.Forms.Control.Location%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="cda97-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="cda97-111">Una estructura es un tipo de valor y la estructura temporal no se conserva después de que se ejecute la instrucción.</span><span class="sxs-lookup"><span data-stu-id="cda97-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="cda97-112">El problema se resuelve declarando y usando una variable para <xref:System.Windows.Forms.Control.Location%2A> , lo que crea una asignación más permanente para la <xref:System.Drawing.Point> estructura.</span><span class="sxs-lookup"><span data-stu-id="cda97-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="cda97-113">En el ejemplo siguiente se muestra código que puede reemplazar la última instrucción del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="cda97-113">The following example shows code that can replace the last statement of the preceding example.</span></span>

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

<span data-ttu-id="cda97-114">**Identificador de error:** BC30068</span><span class="sxs-lookup"><span data-stu-id="cda97-114">**Error ID:** BC30068</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="cda97-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cda97-115">To correct this error</span></span>

- <span data-ttu-id="cda97-116">Si la instrucción asigna un valor a una expresión, reemplace la expresión por una única variable, propiedad o elemento de matriz de escritura.</span><span class="sxs-lookup"><span data-stu-id="cda97-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>

- <span data-ttu-id="cda97-117">Si la instrucción hace acceso indirecto a través de un tipo de valor (normalmente una estructura), cree una variable que contenga el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="cda97-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>

- <span data-ttu-id="cda97-118">Asigne la estructura adecuada (u otro tipo de valor) a la variable.</span><span class="sxs-lookup"><span data-stu-id="cda97-118">Assign the appropriate structure (or other value type) to the variable.</span></span>

- <span data-ttu-id="cda97-119">Use la variable para tener acceso a la propiedad y asignarle un valor.</span><span class="sxs-lookup"><span data-stu-id="cda97-119">Use the variable to access the property to assign it a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="cda97-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cda97-120">See also</span></span>

- [<span data-ttu-id="cda97-121">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="cda97-121">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="cda97-122">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="cda97-122">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="cda97-123">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="cda97-123">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
