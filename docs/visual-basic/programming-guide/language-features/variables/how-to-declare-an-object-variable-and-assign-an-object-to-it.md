---
title: Procedimiento Declarar una Variable de objeto y asignarle un objeto en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: fb6411efc190dce335422369a8d2bbff564b9523
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819676"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="e1600-102">Procedimiento Declarar una Variable de objeto y asignarle un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1600-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="e1600-103">Declare una variable de la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) especificando `As Object` en un [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e1600-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="e1600-104">Asignar un objeto a este tipo de variable colocando el objeto después del signo igual (`=`) en una cláusula de instrucción o la inicialización de la asignación.</span><span class="sxs-lookup"><span data-stu-id="e1600-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1600-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1600-105">Example</span></span>  
 <span data-ttu-id="e1600-106">En el ejemplo siguiente se declara un `Object` variable y asigna la instancia actual a él.</span><span class="sxs-lookup"><span data-stu-id="e1600-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="e1600-107">Puede combinar la declaración y asignación, inicialice la variable como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="e1600-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="e1600-108">El ejemplo siguiente es equivalente al ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e1600-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1600-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e1600-109">Compiling the Code</span></span>  
 <span data-ttu-id="e1600-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e1600-110">This example requires:</span></span>  
  
-   <span data-ttu-id="e1600-111">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="e1600-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="e1600-112">Una clase, estructura o módulo en el que se va a colocar el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e1600-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="e1600-113">Un procedimiento en el que se va a colocar la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="e1600-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1600-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1600-114">See also</span></span>

- [<span data-ttu-id="e1600-115">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="e1600-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="e1600-116">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="e1600-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="e1600-117">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="e1600-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="e1600-118">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="e1600-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="e1600-119">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e1600-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="e1600-120">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="e1600-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="e1600-121">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e1600-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
