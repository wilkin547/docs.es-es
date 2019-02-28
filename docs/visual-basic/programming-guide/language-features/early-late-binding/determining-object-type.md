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
ms.openlocfilehash: becbbef008e8a474db198748d45f260fcb90c758
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966780"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="c0488-102">Determinar tipos de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0488-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="c0488-103">Variables de objeto genéricas (es decir, las variables se declaran como `Object`) puede contener objetos de cualquier clase.</span><span class="sxs-lookup"><span data-stu-id="c0488-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="c0488-104">Al usar las variables de tipo `Object`, es posible que deba realizar diferentes acciones basadas en la clase del objeto; por ejemplo, algunos objetos podrían no admitir un método o propiedad concreta.</span><span class="sxs-lookup"><span data-stu-id="c0488-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="c0488-105">Visual Basic ofrece dos maneras de determinar qué tipo de objeto se almacena en una variable de objeto: el `TypeName` función y el `TypeOf...Is` operador.</span><span class="sxs-lookup"><span data-stu-id="c0488-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="c0488-106">TypeName y TypeOf... Es</span><span class="sxs-lookup"><span data-stu-id="c0488-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="c0488-107">El `TypeName` función devuelve una cadena y es la mejor opción cuando necesite almacenar o mostrar el nombre de clase de un objeto, como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="c0488-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="c0488-108">El `TypeOf...Is` operador es la mejor opción para comprobar el tipo de un objeto, porque es mucho más rápido que una comparación de cadena equivalente mediante `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="c0488-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="c0488-109">El siguiente fragmento de código utiliza `TypeOf...Is` dentro de un `If...Then...Else` instrucción:</span><span class="sxs-lookup"><span data-stu-id="c0488-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="c0488-110">Aquí vence una palabra de advertencia.</span><span class="sxs-lookup"><span data-stu-id="c0488-110">A word of caution is due here.</span></span> <span data-ttu-id="c0488-111">El `TypeOf...Is` operador devuelve `True` si un objeto es de un tipo específico, o se deriva de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="c0488-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="c0488-112">Casi todo lo que hace con Visual Basic implica objetos, que incluyen algunos elementos que normalmente no se considera objetos, como cadenas y enteros.</span><span class="sxs-lookup"><span data-stu-id="c0488-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="c0488-113">Estos objetos se derivan y heredan los métodos de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c0488-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="c0488-114">Cuando se pasa un `Integer` y evaluado con `Object`, `TypeOf...Is` operador devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="c0488-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="c0488-115">En el ejemplo siguiente se notifica que el parámetro `InParam` es tanto un `Object` y un `Integer`:</span><span class="sxs-lookup"><span data-stu-id="c0488-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="c0488-116">En el ejemplo siguiente se usa tanto `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se pasa en el `Ctrl` argumento.</span><span class="sxs-lookup"><span data-stu-id="c0488-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="c0488-117">El `TestObject` las llamadas a procedimiento `ShowType` con tres tipos diferentes de controles.</span><span class="sxs-lookup"><span data-stu-id="c0488-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="c0488-118">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0488-118">To run the example</span></span>  
  
1.  <span data-ttu-id="c0488-119">Cree un nuevo proyecto de aplicación de Windows y agregue un <xref:System.Windows.Forms.Button> (control), un <xref:System.Windows.Forms.CheckBox> control y un <xref:System.Windows.Forms.RadioButton> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="c0488-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="c0488-120">En el botón en el formulario, llame a la `TestObject` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c0488-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="c0488-121">Agregue el código siguiente al formulario:</span><span class="sxs-lookup"><span data-stu-id="c0488-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="c0488-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0488-122">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="c0488-123">Llamada a una propiedad o método mediante un nombre de cadena</span><span class="sxs-lookup"><span data-stu-id="c0488-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="c0488-124">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="c0488-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="c0488-125">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c0488-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="c0488-126">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c0488-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="c0488-127">Integer (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c0488-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
