---
title: Implementación de métodos en controles personalizados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], method implementation
- custom controls [Windows Forms], overloading methods
- custom controls [Windows Forms], method implementation
- methods [Windows Forms]
- methods [Windows Forms], custom controls
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
ms.openlocfilehash: 38dcad25af31b87afc1cc6ef4f89a1f7903bc0ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117422"
---
# <a name="method-implementation-in-custom-controls"></a><span data-ttu-id="d6b1f-102">Implementación de métodos en controles personalizados</span><span class="sxs-lookup"><span data-stu-id="d6b1f-102">Method Implementation in Custom Controls</span></span>
<span data-ttu-id="d6b1f-103">Un método se implementa en un control de la misma manera que se implementa en cualquier otro componente.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-103">A method is implemented in a control in the same manner a method would be implemented in any other component.</span></span>  
  
 <span data-ttu-id="d6b1f-104">En Visual Basic, si se necesita un método para devolver un valor, se implementa como `Public Function`.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-104">In Visual Basic, if a method is required to return a value, it is implemented as a `Public Function`.</span></span> <span data-ttu-id="d6b1f-105">Si no se devuelve ningún valor, se implementa como `Public Sub`.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-105">If no value is returned, it is implemented as a `Public Sub`.</span></span> <span data-ttu-id="d6b1f-106">Los métodos se declaran mediante la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d6b1f-106">Methods are declared using the following syntax:</span></span>  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 <span data-ttu-id="d6b1f-107">Como las funciones devuelven un valor, deben especificar un tipo de valor devuelto, por ejemplo, entero, cadena, objeto, etc.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-107">Because functions return a value, they must specify a return type, such as integer, string, object, and so on.</span></span> <span data-ttu-id="d6b1f-108">También se deben especificar los argumentos `Function` o `Sub` que toma el procedimiento, si corresponde.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-108">The arguments `Function` or `Sub` procedures take, if any, must also be specified.</span></span>  
  
 <span data-ttu-id="d6b1f-109">C# no realiza distinciones entre funciones y procedimientos como sí hace Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-109">C# makes no distinction between functions and procedures, as Visual Basic does.</span></span> <span data-ttu-id="d6b1f-110">Un método devuelve un valor o devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-110">A method either returns a value or returns `void`.</span></span> <span data-ttu-id="d6b1f-111">La sintaxis para declarar un método público de C# es:</span><span class="sxs-lookup"><span data-stu-id="d6b1f-111">The syntax for declaring a C# public method is:</span></span>  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 <span data-ttu-id="d6b1f-112">Cuando declare un método, declare todos sus argumentos como tipos de datos explícitos siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-112">When you declare a method, declare all of its arguments as explicit data types whenever possible.</span></span> <span data-ttu-id="d6b1f-113">Los argumentos que toman referencias de objeto se deben declarar como tipos de clase específicos, por ejemplo, `As Widget` en lugar de `As Object`.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-113">Arguments that take object references should be declared as specific class types — for example, `As Widget` instead of `As Object`.</span></span> <span data-ttu-id="d6b1f-114">En Visual Basic, la opción predeterminada `Option Strict` aplica automáticamente esta regla.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-114">In Visual Basic, the default setting `Option Strict` automatically enforces this rule.</span></span>  
  
 <span data-ttu-id="d6b1f-115">Los argumentos con tipo permiten capturar muchos errores del desarrollador en el compilador, en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-115">Typed arguments allow many developer errors to be caught by the compiler, rather than at run time.</span></span> <span data-ttu-id="d6b1f-116">El compilador siempre captura errores, mientras que las pruebas en tiempo de ejecución solo son buenas si el conjunto de pruebas lo es.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-116">The compiler always catches errors, whereas run-time testing is only as good as the test suite.</span></span>  
  
## <a name="overloaded-methods"></a><span data-ttu-id="d6b1f-117">Métodos sobrecargados</span><span class="sxs-lookup"><span data-stu-id="d6b1f-117">Overloaded Methods</span></span>  
 <span data-ttu-id="d6b1f-118">Si quiere que los usuarios del control puedan suministrar diferentes combinaciones de parámetros a un método, proporcione varias sobrecargas del método usando tipos de datos explícitos.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-118">If you want to allow users of your control to supply different combinations of parameters to a method, provide multiple overloads of the method, using explicit data types.</span></span> <span data-ttu-id="d6b1f-119">Evite crear parámetros declarados `As Object` que puedan contener algún tipo de datos, porque esto podría provocar errores que quizás no se capturen en las pruebas.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-119">Avoid creating parameters declared `As Object` that can contain any data type, as this can lead to errors that might not be caught in testing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6b1f-120">El tipo de datos universal en Common Language Runtime es `Object` en lugar de `Variant`.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-120">The universal data type in the common language runtime is `Object` rather than `Variant`.</span></span> <span data-ttu-id="d6b1f-121">`Variant` se ha quitado del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d6b1f-121">`Variant` has been removed from the language.</span></span>  
  
 <span data-ttu-id="d6b1f-122">Por ejemplo, el método `Spin` de un control `Widget` hipotético podría permitir especificar directamente la dirección y la velocidad de giro, o especificar otro objeto `Widget` desde el cual se absorba el momento angular:</span><span class="sxs-lookup"><span data-stu-id="d6b1f-122">For example, the `Spin` method of a hypothetical `Widget` control might allow either direct specification of spin direction and speed, or specification of another `Widget` object from which angular momentum is to be absorbed:</span></span>  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6b1f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6b1f-123">See also</span></span>

- [<span data-ttu-id="d6b1f-124">Eventos</span><span class="sxs-lookup"><span data-stu-id="d6b1f-124">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="d6b1f-125">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6b1f-125">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
