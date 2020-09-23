---
title: Determinación del tipo de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: ae338bc9bad9646abc045a652d4ef33a8863354b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086067"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="5e953-102">Determinar tipos de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e953-102">Determining Object Type (Visual Basic)</span></span>

<span data-ttu-id="5e953-103">Las variables de objeto genérico (es decir, las variables que se declaran como `Object` ) pueden contener objetos de cualquier clase.</span><span class="sxs-lookup"><span data-stu-id="5e953-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="5e953-104">Al usar variables de tipo `Object` , es posible que necesite realizar diferentes acciones en función de la clase del objeto; por ejemplo, algunos objetos podrían no admitir una propiedad o un método determinados.</span><span class="sxs-lookup"><span data-stu-id="5e953-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="5e953-105">Visual Basic proporciona dos formas de determinar qué tipo de objeto se almacena en una variable de objeto: la `TypeName` función y el `TypeOf...Is` operador.</span><span class="sxs-lookup"><span data-stu-id="5e953-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="5e953-106">TypeName y typeof... Encuentra</span><span class="sxs-lookup"><span data-stu-id="5e953-106">TypeName and TypeOf…Is</span></span>  

 <span data-ttu-id="5e953-107">La `TypeName` función devuelve una cadena y es la mejor opción cuando necesita almacenar o mostrar el nombre de clase de un objeto, tal y como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="5e953-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="5e953-108">El `TypeOf...Is` operador es la mejor opción para probar el tipo de un objeto, ya que es mucho más rápido que una comparación de cadenas equivalente mediante `TypeName` .</span><span class="sxs-lookup"><span data-stu-id="5e953-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="5e953-109">En el fragmento de código siguiente se usa `TypeOf...Is` dentro de una `If...Then...Else` instrucción:</span><span class="sxs-lookup"><span data-stu-id="5e953-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="5e953-110">Aquí se debe tener precaución.</span><span class="sxs-lookup"><span data-stu-id="5e953-110">A word of caution is due here.</span></span> <span data-ttu-id="5e953-111">El `TypeOf...Is` operador devuelve `True` si un objeto es de un tipo específico o se deriva de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="5e953-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="5e953-112">Casi todo lo que se hace con Visual Basic implica objetos, que incluyen algunos elementos que normalmente no se consideran objetos como, por ejemplo, cadenas y enteros.</span><span class="sxs-lookup"><span data-stu-id="5e953-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="5e953-113">Estos objetos se derivan de los métodos y heredan de <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="5e953-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="5e953-114">Cuando se pasa `Integer` y se evalúa con `Object` , el `TypeOf...Is` operador devuelve `True` .</span><span class="sxs-lookup"><span data-stu-id="5e953-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="5e953-115">En el ejemplo siguiente se informa de que el parámetro `InParam` es un `Object` y un `Integer` :</span><span class="sxs-lookup"><span data-stu-id="5e953-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="5e953-116">En el ejemplo siguiente se usan `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se le ha pasado en el `Ctrl` argumento.</span><span class="sxs-lookup"><span data-stu-id="5e953-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="5e953-117">El `TestObject` procedimiento llama a `ShowType` con tres tipos diferentes de controles.</span><span class="sxs-lookup"><span data-stu-id="5e953-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="5e953-118">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e953-118">To run the example</span></span>  
  
1. <span data-ttu-id="5e953-119">Cree un nuevo proyecto de aplicación para Windows y agregue un control <xref:System.Windows.Forms.Button> , un <xref:System.Windows.Forms.CheckBox> control y un <xref:System.Windows.Forms.RadioButton> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="5e953-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="5e953-120">En el botón del formulario, llame al `TestObject` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5e953-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="5e953-121">Agregue el código siguiente al formulario:</span><span class="sxs-lookup"><span data-stu-id="5e953-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="5e953-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e953-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="5e953-123">Llamar a una propiedad o método mediante un nombre de cadena</span><span class="sxs-lookup"><span data-stu-id="5e953-123">Calling a Property or Method Using a String Name</span></span>](calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="5e953-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="5e953-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="5e953-125">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="5e953-125">If...Then...Else Statement</span></span>](../../../language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="5e953-126">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="5e953-126">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="5e953-127">Tipo de datos Integer</span><span class="sxs-lookup"><span data-stu-id="5e953-127">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)
