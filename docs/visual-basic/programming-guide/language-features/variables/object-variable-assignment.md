---
description: 'Más información sobre: asignación de variables de objeto (Visual Basic)'
title: Asignación de variables de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: ac5e534a03d651a23e651e1049477b2bd0769b82
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481654"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="f6e1f-103">Asignación de variables de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6e1f-103">Object Variable Assignment (Visual Basic)</span></span>

<span data-ttu-id="f6e1f-104">Use una instrucción de asignación normal para asignar un objeto a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-104">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="f6e1f-105">Puede asignar una expresión de objeto o la palabra clave [Nothing](../../../language-reference/nothing.md) , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-105">You can assign an object expression or the [Nothing](../../../language-reference/nothing.md) keyword, as the following example illustrates.</span></span>

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

<span data-ttu-id="f6e1f-106">`Nothing` significa que no hay ningún objeto asignado actualmente a la variable.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-106">`Nothing` means there is no object currently assigned to the variable.</span></span>

## <a name="initialization"></a><span data-ttu-id="f6e1f-107">Inicialización</span><span class="sxs-lookup"><span data-stu-id="f6e1f-107">Initialization</span></span>

<span data-ttu-id="f6e1f-108">Cuando el código comienza a ejecutarse, las variables de objeto se inicializan en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="f6e1f-108">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="f6e1f-109">Las declaraciones que incluyen la inicialización se reinicializan en los valores que se especifican cuando se ejecutan las instrucciones de declaración.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-109">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>

<span data-ttu-id="f6e1f-110">Puede incluir la inicialización en la declaración mediante la palabra clave [New](../../../language-reference/operators/new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="f6e1f-110">You can include initialization in your declaration by using the [New](../../../language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="f6e1f-111">Las siguientes instrucciones de declaración declaran variables de objeto `testUri` y `ver` y asignan objetos específicos a ellas.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-111">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="f6e1f-112">Cada usa uno de los constructores sobrecargados de la clase adecuada para inicializar el objeto.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-112">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a><span data-ttu-id="f6e1f-113">Desasociación</span><span class="sxs-lookup"><span data-stu-id="f6e1f-113">Disassociation</span></span>

<span data-ttu-id="f6e1f-114">Al establecer una variable de objeto en, se `Nothing` interrumpe la Asociación de la variable con cualquier objeto específico.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-114">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="f6e1f-115">Esto evita que cambie accidentalmente el objeto cambiando la variable.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-115">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="f6e1f-116">También permite probar si la variable de objeto apunta a un objeto válido, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-116">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

<span data-ttu-id="f6e1f-117">Si el objeto al que hace referencia la variable está en otra aplicación, esta prueba no puede determinar si la aplicación ha terminado o simplemente invalidado el objeto.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-117">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>

<span data-ttu-id="f6e1f-118">Una variable de objeto con un valor de `Nothing` también se denomina *referencia nula*.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-118">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>

## <a name="current-instance"></a><span data-ttu-id="f6e1f-119">Instancia actual</span><span class="sxs-lookup"><span data-stu-id="f6e1f-119">Current Instance</span></span>

<span data-ttu-id="f6e1f-120">La *instancia actual* de un objeto es aquella en la que se está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-120">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="f6e1f-121">Dado que todo el código se ejecuta dentro de un procedimiento, la instancia actual es aquella en la que se invocó el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-121">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>

<span data-ttu-id="f6e1f-122">La `Me` palabra clave actúa como una variable de objeto que hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-122">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="f6e1f-123">Si un procedimiento no está [compartido](../../../language-reference/modifiers/shared.md), puede usar la `Me` palabra clave para obtener un puntero a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-123">If a procedure is not [Shared](../../../language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="f6e1f-124">Los procedimientos compartidos no se pueden asociar a una instancia específica de una clase.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-124">Shared procedures cannot be associated with a specific instance of a class.</span></span>

<span data-ttu-id="f6e1f-125">`Me`El uso de es especialmente útil para pasar la instancia actual a un procedimiento de otro módulo.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-125">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="f6e1f-126">Por ejemplo, supongamos que tiene varios documentos XML y desea agregar texto estándar a todos ellos.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-126">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="f6e1f-127">En el ejemplo siguiente se define un procedimiento para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-127">The following example defines a procedure to do this.</span></span>

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

<span data-ttu-id="f6e1f-128">Cada objeto de documento XML podría llamar al procedimiento y pasar su instancia actual como argumento.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-128">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="f6e1f-129">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f6e1f-129">The following example demonstrates this.</span></span>

```vb
addStandardText(Me)
```

## <a name="see-also"></a><span data-ttu-id="f6e1f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6e1f-130">See also</span></span>

- [<span data-ttu-id="f6e1f-131">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="f6e1f-131">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="f6e1f-132">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="f6e1f-132">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="f6e1f-133">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="f6e1f-133">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="f6e1f-134">Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f6e1f-134">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="f6e1f-135">Procedimiento para crear una variable de objeto que no haga referencia a ninguna instancia</span><span class="sxs-lookup"><span data-stu-id="f6e1f-135">How to: Make an Object Variable Not Refer to Any Instance</span></span>](how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="f6e1f-136">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="f6e1f-136">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
