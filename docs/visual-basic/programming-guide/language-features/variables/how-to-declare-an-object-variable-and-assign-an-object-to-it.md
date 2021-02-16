---
description: 'Más información sobre: Cómo: declarar una variable de objeto y asignarle un objeto en Visual Basic'
title: Procedimiento para declarar una variable de objeto y asignarle un objeto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: f79cda4507a3dbf2a6946dee7d909b6d1b10802d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481953"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="b6f86-103">Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6f86-103">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="b6f86-104">Declare una variable del [tipo de datos Object](../../../language-reference/data-types/object-data-type.md) especificando `As Object` en una [instrucción Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b6f86-104">You declare a variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="b6f86-105">Para asignar un objeto a esta variable, coloque el objeto después del signo igual ( `=` ) en una instrucción de asignación o una cláusula de inicialización.</span><span class="sxs-lookup"><span data-stu-id="b6f86-105">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="b6f86-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6f86-106">Example</span></span>

<span data-ttu-id="b6f86-107">En el ejemplo siguiente se declara una `Object` variable y se le asigna la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="b6f86-107">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="b6f86-108">Puede combinar la declaración y la asignación inicializando la variable como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="b6f86-108">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="b6f86-109">El ejemplo siguiente es equivalente al ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="b6f86-109">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="b6f86-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b6f86-110">Compile the code</span></span>

<span data-ttu-id="b6f86-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b6f86-111">This example requires:</span></span>

- <span data-ttu-id="b6f86-112">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="b6f86-112">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="b6f86-113">Clase, estructura o módulo en el que se va a colocar la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b6f86-113">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="b6f86-114">Procedimiento en el que se va a colocar la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="b6f86-114">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6f86-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6f86-115">See also</span></span>

- [<span data-ttu-id="b6f86-116">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="b6f86-116">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="b6f86-117">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b6f86-117">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="b6f86-118">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b6f86-118">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="b6f86-119">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="b6f86-119">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="b6f86-120">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="b6f86-120">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="b6f86-121">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="b6f86-121">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="b6f86-122">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b6f86-122">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
