---
title: Determinar tipos de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a9852998abeae67b2a0e9dc3ffc85318ce5045da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648299"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="99476-102">Determinar tipos de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99476-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="99476-103">Variables de objeto genéricas (es decir, las variables se declara como `Object`) puede contener objetos de cualquier clase.</span><span class="sxs-lookup"><span data-stu-id="99476-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="99476-104">Al usar las variables de tipo `Object`, puede que necesite realizar diferentes acciones basadas en la clase del objeto; por ejemplo, algunos objetos podrían no admitir un método o propiedad determinado.</span><span class="sxs-lookup"><span data-stu-id="99476-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="99476-105">Visual Basic proporciona dos formas de determinar qué tipo de objeto se almacena en una variable de objeto: la `TypeName` función y el `TypeOf...Is` operador.</span><span class="sxs-lookup"><span data-stu-id="99476-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="99476-106">TypeName y TypeOf... Es</span><span class="sxs-lookup"><span data-stu-id="99476-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="99476-107">El `TypeName` función devuelve una cadena y es la mejor opción cuando necesite almacenar o mostrar el nombre de clase de un objeto, como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="99476-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 <span data-ttu-id="99476-108">El `TypeOf...Is` operador es la mejor opción para comprobar el tipo de un objeto, porque es mucho más rápido que una comparación de cadena equivalente mediante `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="99476-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="99476-109">En el fragmento de código siguiente se utiliza `TypeOf...Is` dentro de un `If...Then...Else` instrucción:</span><span class="sxs-lookup"><span data-stu-id="99476-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 <span data-ttu-id="99476-110">Una palabra de precaución aquí es debida.</span><span class="sxs-lookup"><span data-stu-id="99476-110">A word of caution is due here.</span></span> <span data-ttu-id="99476-111">El `TypeOf...Is` operador devuelve `True` si un objeto es de un tipo específico, o se deriva de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="99476-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="99476-112">Casi todo lo que haga con Visual Basic incluye objetos, que incluyen algunos elementos que normalmente no se suponen como objetos, como cadenas y números enteros.</span><span class="sxs-lookup"><span data-stu-id="99476-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="99476-113">Estos objetos se derivan y heredan métodos de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="99476-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="99476-114">Cuando se pasa un `Integer` y evaluado con `Object`, `TypeOf...Is` operador devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="99476-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="99476-115">En el ejemplo siguiente se notifica que el parámetro `InParam` es tanto un `Object` y `Integer`:</span><span class="sxs-lookup"><span data-stu-id="99476-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 <span data-ttu-id="99476-116">En el ejemplo siguiente se utiliza tanto `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se pasa en el `Ctrl` argumento.</span><span class="sxs-lookup"><span data-stu-id="99476-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="99476-117">El `TestObject` las llamadas a procedimiento `ShowType` con tres tipos diferentes de controles.</span><span class="sxs-lookup"><span data-stu-id="99476-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="99476-118">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="99476-118">To run the example</span></span>  
  
1.  <span data-ttu-id="99476-119">Cree un nuevo proyecto de aplicación para Windows y agregue un <xref:System.Windows.Forms.Button> (control), un <xref:System.Windows.Forms.CheckBox> (control) y un <xref:System.Windows.Forms.RadioButton> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="99476-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="99476-120">En el botón en el formulario, llame a la `TestObject` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="99476-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="99476-121">Agregue el código siguiente al formulario:</span><span class="sxs-lookup"><span data-stu-id="99476-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="99476-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="99476-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [<span data-ttu-id="99476-123">Llamada a una propiedad o método mediante un nombre de cadena</span><span class="sxs-lookup"><span data-stu-id="99476-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [<span data-ttu-id="99476-124">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="99476-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="99476-125">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="99476-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="99476-126">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="99476-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="99476-127">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="99476-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
