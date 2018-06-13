---
title: Asignación de variables de objeto (Visual Basic)
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
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656063"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="2abf4-102">Asignación de variables de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2abf4-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="2abf4-103">Usar una instrucción de asignación normal para asignar un objeto a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="2abf4-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="2abf4-104">Puede asignar una expresión de objeto o la [nada](../../../../visual-basic/language-reference/nothing.md) palabra clave, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="2abf4-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="2abf4-105">`Nothing` significa que no hay ningún objeto asignado actualmente a la variable.</span><span class="sxs-lookup"><span data-stu-id="2abf4-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="2abf4-106">Inicialización</span><span class="sxs-lookup"><span data-stu-id="2abf4-106">Initialization</span></span>  
 <span data-ttu-id="2abf4-107">Cuando el código inicia la ejecución, el objeto se inicializan las variables a `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2abf4-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="2abf4-108">Aquéllos cuyas declaraciones incluyen la inicialización se reinicializan con los valores especificados cuando se ejecutan las instrucciones de declaración.</span><span class="sxs-lookup"><span data-stu-id="2abf4-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="2abf4-109">Puede incluir la inicialización en su declaración utilizando el [New](../../../../visual-basic/language-reference/operators/new-operator.md) (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="2abf4-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="2abf4-110">Las siguientes instrucciones de declaración declaran variables de objeto `testUri` y `ver` y asignan objetos específicos.</span><span class="sxs-lookup"><span data-stu-id="2abf4-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="2abf4-111">Cada uno utiliza uno de los constructores sobrecargados de la clase adecuada para inicializar el objeto.</span><span class="sxs-lookup"><span data-stu-id="2abf4-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="2abf4-112">Desasociación</span><span class="sxs-lookup"><span data-stu-id="2abf4-112">Disassociation</span></span>  
 <span data-ttu-id="2abf4-113">Si se establece una variable de objeto en `Nothing` se interrumpe la asociación de la variable con cualquier objeto concreto.</span><span class="sxs-lookup"><span data-stu-id="2abf4-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="2abf4-114">Esto impide que se modifique accidentalmente el objeto cambiando la variable.</span><span class="sxs-lookup"><span data-stu-id="2abf4-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="2abf4-115">También permite comprobar si la variable de objeto hace referencia a un objeto válido, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2abf4-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="2abf4-116">Si el objeto al que hace referencia la variable está en otra aplicación, esta prueba no puede determinar si esa aplicación ha terminado o ha invalidado el objeto.</span><span class="sxs-lookup"><span data-stu-id="2abf4-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="2abf4-117">Una variable de objeto con un valor de `Nothing` también se denomina un *referencia nula*.</span><span class="sxs-lookup"><span data-stu-id="2abf4-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="2abf4-118">Instancia actual</span><span class="sxs-lookup"><span data-stu-id="2abf4-118">Current Instance</span></span>  
 <span data-ttu-id="2abf4-119">El *instancia actual* de un objeto es el que se está ejecutando el código actualmente.</span><span class="sxs-lookup"><span data-stu-id="2abf4-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="2abf4-120">Puesto que todo el código se ejecuta dentro de un procedimiento, la instancia actual es uno en el que se invocó el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2abf4-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="2abf4-121">El `Me` palabra clave actúa como una variable de objeto que hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="2abf4-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="2abf4-122">Si un procedimiento no es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), puede usar el `Me` palabra clave que se va a obtener un puntero a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="2abf4-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="2abf4-123">Los procedimientos compartidos no se pueden asociados a una instancia específica de una clase.</span><span class="sxs-lookup"><span data-stu-id="2abf4-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="2abf4-124">Usar `Me` es especialmente útil para pasar la instancia actual a un procedimiento en otro módulo.</span><span class="sxs-lookup"><span data-stu-id="2abf4-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="2abf4-125">Por ejemplo, suponga que tiene un número de documentos XML y desea agregar algún texto estándar a todos ellos.</span><span class="sxs-lookup"><span data-stu-id="2abf4-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="2abf4-126">En el ejemplo siguiente se define un procedimiento para hacer esto.</span><span class="sxs-lookup"><span data-stu-id="2abf4-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="2abf4-127">Cada objeto de documento XML, a continuación, podría llamar al procedimiento y pasar la instancia actual como un argumento.</span><span class="sxs-lookup"><span data-stu-id="2abf4-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="2abf4-128">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2abf4-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2abf4-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2abf4-129">See Also</span></span>  
 [<span data-ttu-id="2abf4-130">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="2abf4-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="2abf4-131">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="2abf4-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="2abf4-132">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="2abf4-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="2abf4-133">Cómo: declarar una Variable de objeto y asignarle un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2abf4-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="2abf4-134">Crear una variable de objeto que no haga referencia a ninguna instancia</span><span class="sxs-lookup"><span data-stu-id="2abf4-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [<span data-ttu-id="2abf4-135">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="2abf4-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
