---
title: Declaración de variables de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: 74b1401df3dbb2d744de74734d10cbcd92e9689e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077051"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="22bbc-102">Declaración de variables de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22bbc-102">Object Variable Declaration (Visual Basic)</span></span>

<span data-ttu-id="22bbc-103">Use una instrucción de declaración normal para declarar una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="22bbc-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="22bbc-104">Para el tipo de datos, se especifica `Object` (es decir, el [tipo de datos Object](../../../language-reference/data-types/object-data-type.md)) o una clase más específica de la que se va a crear el objeto.</span><span class="sxs-lookup"><span data-stu-id="22bbc-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="22bbc-105">Declarar una variable como `Object` es igual que la declaración como <xref:System.Object?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="22bbc-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="22bbc-106">Cuando se declara una variable con una clase de objeto específica, puede tener acceso a todos los métodos y propiedades expuestos por esa clase y las clases de las que hereda.</span><span class="sxs-lookup"><span data-stu-id="22bbc-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="22bbc-107">Si declara la variable con <xref:System.Object> , solo podrá tener acceso a los miembros de la <xref:System.Object> clase, a menos que Active `Option Strict Off` permitir el enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="22bbc-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="22bbc-108">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="22bbc-108">Declaration Syntax</span></span>  

 <span data-ttu-id="22bbc-109">Use la siguiente sintaxis para declarar una variable de objeto:</span><span class="sxs-lookup"><span data-stu-id="22bbc-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="22bbc-110">También puede especificar [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), `Protected Friend` , [Private](../../../language-reference/modifiers/private.md), [Shared](../../../language-reference/modifiers/shared.md)o [static](../../../language-reference/modifiers/static.md) en la declaración.</span><span class="sxs-lookup"><span data-stu-id="22bbc-110">You can also specify [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../language-reference/modifiers/private.md), [Shared](../../../language-reference/modifiers/shared.md), or [Static](../../../language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="22bbc-111">Las siguientes declaraciones de ejemplo son válidas:</span><span class="sxs-lookup"><span data-stu-id="22bbc-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="22bbc-112">Enlace en tiempo de ejecución y enlace temprano</span><span class="sxs-lookup"><span data-stu-id="22bbc-112">Late Binding and Early Binding</span></span>  

 <span data-ttu-id="22bbc-113">A veces, se desconoce la clase específica hasta que se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="22bbc-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="22bbc-114">En este caso, debe declarar la variable de objeto con el `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="22bbc-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="22bbc-115">Esto crea una referencia general a cualquier tipo de objeto y la clase específica se asigna en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="22bbc-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="22bbc-116">Esto se denomina *enlace en tiempo de ejecución*.</span><span class="sxs-lookup"><span data-stu-id="22bbc-116">This is called *late binding*.</span></span> <span data-ttu-id="22bbc-117">El enlace en tiempo de ejecución requiere tiempo de ejecución adicional.</span><span class="sxs-lookup"><span data-stu-id="22bbc-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="22bbc-118">También limita el código a los métodos y propiedades de la clase que se le ha asignado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="22bbc-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="22bbc-119">Esto puede producir errores en tiempo de ejecución si el código intenta obtener acceso a miembros de una clase diferente.</span><span class="sxs-lookup"><span data-stu-id="22bbc-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="22bbc-120">Cuando conozca la clase específica en tiempo de compilación, debe declarar la variable de objeto para que sea de esa clase.</span><span class="sxs-lookup"><span data-stu-id="22bbc-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="22bbc-121">Esto se denomina *enlace anticipado*.</span><span class="sxs-lookup"><span data-stu-id="22bbc-121">This is called *early binding*.</span></span> <span data-ttu-id="22bbc-122">El enlace temprano mejora el rendimiento y garantiza el acceso del código a todos los métodos y propiedades de la clase específica.</span><span class="sxs-lookup"><span data-stu-id="22bbc-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="22bbc-123">En las declaraciones de ejemplo anteriores, si variable `objA` solo usa objetos de clase <xref:System.Windows.Forms.Label?displayProperty=nameWithType> , debe especificar `As System.Windows.Forms.Label` en su declaración.</span><span class="sxs-lookup"><span data-stu-id="22bbc-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="22bbc-124">Ventajas del enlace anticipado</span><span class="sxs-lookup"><span data-stu-id="22bbc-124">Advantages of Early Binding</span></span>  

 <span data-ttu-id="22bbc-125">Declarar una variable de objeto como una clase específica proporciona varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="22bbc-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="22bbc-126">Comprobación automática de tipos</span><span class="sxs-lookup"><span data-stu-id="22bbc-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="22bbc-127">Acceso garantizado a todos los miembros de la clase específica</span><span class="sxs-lookup"><span data-stu-id="22bbc-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="22bbc-128">Compatibilidad de Microsoft IntelliSense en el editor de código</span><span class="sxs-lookup"><span data-stu-id="22bbc-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="22bbc-129">Mejora de la legibilidad del código</span><span class="sxs-lookup"><span data-stu-id="22bbc-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="22bbc-130">Menos errores en el código</span><span class="sxs-lookup"><span data-stu-id="22bbc-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="22bbc-131">Errores detectados en tiempo de compilación en lugar de en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="22bbc-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="22bbc-132">Ejecución de código más rápida</span><span class="sxs-lookup"><span data-stu-id="22bbc-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="22bbc-133">Acceso a los miembros de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="22bbc-133">Access to Object Variable Members</span></span>  

 <span data-ttu-id="22bbc-134">Cuando `Option Strict` se activa `On` , una variable de objeto solo puede tener acceso a los métodos y propiedades de la clase con la que se declara.</span><span class="sxs-lookup"><span data-stu-id="22bbc-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="22bbc-135">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="22bbc-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="22bbc-136">En este ejemplo, `p` puede usar solo los miembros de la propia clase <xref:System.Object> , que no incluyen la propiedad `Left` .</span><span class="sxs-lookup"><span data-stu-id="22bbc-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="22bbc-137">Por otro lado, `q` se ha declarado con el tipo <xref:System.Windows.Forms.Label>, así que puede usar todos los métodos y propiedades de la clase <xref:System.Windows.Forms.Label> en el espacio de nombres <xref:System.Windows.Forms> .</span><span class="sxs-lookup"><span data-stu-id="22bbc-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="22bbc-138">Flexibilidad de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="22bbc-138">Flexibility of Object Variables</span></span>  

 <span data-ttu-id="22bbc-139">Cuando se trabaja con objetos en una jerarquía de herencia, se puede elegir qué clase se debe usar para declarar las variables de objeto.</span><span class="sxs-lookup"><span data-stu-id="22bbc-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="22bbc-140">Al elegir esta opción, debe equilibrar la flexibilidad de la asignación de objetos con respecto al acceso a los miembros de una clase.</span><span class="sxs-lookup"><span data-stu-id="22bbc-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="22bbc-141">Por ejemplo, considere la jerarquía de herencia que conduce a la <xref:System.Windows.Forms.Form?displayProperty=nameWithType> clase:</span><span class="sxs-lookup"><span data-stu-id="22bbc-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="22bbc-142">Supongamos que la aplicación define una clase de formulario denominada `specialForm` , que hereda de la clase <xref:System.Windows.Forms.Form> .</span><span class="sxs-lookup"><span data-stu-id="22bbc-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="22bbc-143">Puede declarar una variable de objeto que haga referencia específicamente a `specialForm` , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="22bbc-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="22bbc-144">La declaración en el ejemplo anterior limita la variable `nextForm` a objetos de clase `specialForm` , pero también hace que todos los métodos y propiedades de `specialForm` estén disponibles para `nextForm` , así como todos los miembros de todas las clases de las que `specialForm` hereda.</span><span class="sxs-lookup"><span data-stu-id="22bbc-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="22bbc-145">Para hacer que una variable de objeto sea más general, puede declararla como de tipo <xref:System.Windows.Forms.Form> , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="22bbc-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="22bbc-146">La declaración en el ejemplo anterior le permite asignar cualquier formulario de la aplicación a `anyForm` .</span><span class="sxs-lookup"><span data-stu-id="22bbc-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="22bbc-147">Sin embargo, aunque `anyForm` puede tener acceso a todos los miembros de la clase <xref:System.Windows.Forms.Form> , no puede usar ninguno de los métodos o propiedades adicionales definidos para formularios específicos como `specialForm` .</span><span class="sxs-lookup"><span data-stu-id="22bbc-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="22bbc-148">Todos los miembros de una clase base están disponibles para las clases derivadas, pero los miembros adicionales de una clase derivada no están disponibles para la clase base.</span><span class="sxs-lookup"><span data-stu-id="22bbc-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22bbc-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="22bbc-149">See also</span></span>

- [<span data-ttu-id="22bbc-150">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="22bbc-150">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="22bbc-151">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="22bbc-151">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="22bbc-152">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="22bbc-152">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="22bbc-153">Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22bbc-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="22bbc-154">Procedimiento para obtener acceso a los miembros de un objeto</span><span class="sxs-lookup"><span data-stu-id="22bbc-154">How to: Access Members of an Object</span></span>](how-to-access-members-of-an-object.md)
- [<span data-ttu-id="22bbc-155">New (operador)</span><span class="sxs-lookup"><span data-stu-id="22bbc-155">New Operator</span></span>](../../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="22bbc-156">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="22bbc-156">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="22bbc-157">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="22bbc-157">Local Type Inference</span></span>](local-type-inference.md)
