---
description: 'Más información acerca de: propiedades implementadas automáticamente (Visual Basic)'
title: Propiedades autoimplementadas
ms.date: 07/20/2015
f1_keywords:
- vb.AutoProperty
- vb.AutoImplementedProperty
helpviewer_keywords:
- properties [Visual Basic], auto-implemented
- auto-implemented properties [Visual Basic]
ms.assetid: 5c669f0b-cf95-4b4e-ae84-9cc55212ca87
ms.openlocfilehash: 61f6565f9d4e7ea8731bb09c59cd6d942ab8c129
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472701"
---
# <a name="auto-implemented-properties-visual-basic"></a><span data-ttu-id="60b80-103">Propiedades implementadas automáticamente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60b80-103">Auto-Implemented Properties (Visual Basic)</span></span>

<span data-ttu-id="60b80-104">*Las propiedades implementadas automáticamente* permiten especificar rápidamente una propiedad de una clase sin tener que escribir código en `Get` y `Set` la propiedad.</span><span class="sxs-lookup"><span data-stu-id="60b80-104">*Auto-implemented properties* enable you to quickly specify a property of a class without having to write code to `Get` and `Set` the property.</span></span> <span data-ttu-id="60b80-105">Al escribir código para una propiedad implementada automáticamente, el compilador de Visual Basic crea de manera automática un campo privado para almacenar la variable de propiedad, además de crear los procedimientos `Get` y `Set` asociados.</span><span class="sxs-lookup"><span data-stu-id="60b80-105">When you write code for an auto-implemented property, the Visual Basic compiler automatically creates a private field to store the property variable in addition to creating the associated `Get` and `Set` procedures.</span></span>  
  
 <span data-ttu-id="60b80-106">Con las propiedades implementadas automáticamente, una propiedad (incluido un valor predeterminado) puede declararse en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="60b80-106">With auto-implemented properties, a property, including a default value, can be declared in a single line.</span></span> <span data-ttu-id="60b80-107">En el ejemplo siguiente se muestran tres declaraciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="60b80-107">The following example shows three property declarations.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#1)]  
  
 <span data-ttu-id="60b80-108">Una propiedad implementada automáticamente equivale a una propiedad cuyo valor se almacena en un campo privado.</span><span class="sxs-lookup"><span data-stu-id="60b80-108">An auto-implemented property is equivalent to a property for which the property value is stored in a private field.</span></span> <span data-ttu-id="60b80-109">En el siguiente ejemplo de código se muestra una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="60b80-109">The following code example shows an auto-implemented property.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#5)]  
  
 <span data-ttu-id="60b80-110">En el ejemplo de código siguiente se muestra el código equivalente al del ejemplo anterior de propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="60b80-110">The following code example shows the equivalent code for the previous auto-implemented property example.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#2)]  
  
 <span data-ttu-id="60b80-111">En el código siguiente se muestran las propiedades de solo lectura implementadoras:</span><span class="sxs-lookup"><span data-stu-id="60b80-111">The following code show implementing readonly properties:</span></span>  
  
```vb  
Class Customer  
   Public ReadOnly Property Tags As New List(Of String)  
   Public ReadOnly Property Name As String = ""  
   Public ReadOnly Property File As String  
  
   Sub New(file As String)  
      Me.File = file  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="60b80-112">Se pueden realizar asignaciones a la propiedad con expresiones de inicialización, como se muestra en el ejemplo, o se pueden realizar asignaciones a las propiedades en el constructor del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="60b80-112">You can assign to the property with initialization expressions as shown in the example, or you can assign to the properties in the containing type’s constructor.</span></span>  <span data-ttu-id="60b80-113">Siempre que lo desee, puede realizar asignaciones a los campos de respaldo de propiedades de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="60b80-113">You can assign to the backing fields of readonly properties at any time.</span></span>  
  
## <a name="backing-field"></a><span data-ttu-id="60b80-114">Campo de respaldo</span><span class="sxs-lookup"><span data-stu-id="60b80-114">Backing Field</span></span>  

 <span data-ttu-id="60b80-115">Cuando se declara una propiedad implementada automáticamente, Visual Basic crea automáticamente un campo privado oculto denominado *campo de respaldo* para contener el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="60b80-115">When you declare an auto-implemented property, Visual Basic automatically creates a hidden private field called the *backing field* to contain the property value.</span></span> <span data-ttu-id="60b80-116">El nombre del campo de respaldo es el nombre de la propiedad implementada automáticamente precedido por un carácter de subrayado (_).</span><span class="sxs-lookup"><span data-stu-id="60b80-116">The backing field name is the auto-implemented property name preceded by an underscore (_).</span></span> <span data-ttu-id="60b80-117">Por ejemplo, si declara una propiedad implementada automáticamente denominada `ID`, el campo de respaldo se denominará `_ID`.</span><span class="sxs-lookup"><span data-stu-id="60b80-117">For example, if you declare an auto-implemented property named `ID`, the backing field is named `_ID`.</span></span> <span data-ttu-id="60b80-118">Si se incluye un miembro de la clase que también se denomina `_ID`, se produce un conflicto de nomenclatura y Visual Basic informa de un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="60b80-118">If you include a member of your class that is also named `_ID`, you produce a naming conflict and Visual Basic reports a compiler error.</span></span>  
  
 <span data-ttu-id="60b80-119">El campo de respaldo también tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="60b80-119">The backing field also has the following characteristics:</span></span>  
  
- <span data-ttu-id="60b80-120">El modificador de acceso del campo de respaldo siempre es `Private`, incluso cuando la misma propiedad tiene un nivel de acceso diferente, como `Public`.</span><span class="sxs-lookup"><span data-stu-id="60b80-120">The access modifier for the backing field is always `Private`, even when the property itself has a different access level, such as `Public`.</span></span>  
  
- <span data-ttu-id="60b80-121">Si la propiedad está marcada como `Shared`, también se comparte el campo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="60b80-121">If the property is marked as `Shared`, the backing field also is shared.</span></span>  
  
- <span data-ttu-id="60b80-122">Los atributos especificados para la propiedad no se aplican al campo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="60b80-122">Attributes specified for the property do not apply to the backing field.</span></span>  
  
- <span data-ttu-id="60b80-123">El acceso al campo de respaldo se puede realizar desde el código contenido en la clase y desde herramientas de depuración como la ventana Inspección. </span><span class="sxs-lookup"><span data-stu-id="60b80-123">The backing field can be accessed from code within the class and from debugging tools such as the Watch window.</span></span> <span data-ttu-id="60b80-124">Sin embargo, dicho campo no se muestra en una lista de finalización de palabras de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="60b80-124">However, the backing field does not show in an IntelliSense word completion list.</span></span>  
  
## <a name="initializing-an-auto-implemented-property"></a><span data-ttu-id="60b80-125">Inicializar una propiedad implementada automáticamente</span><span class="sxs-lookup"><span data-stu-id="60b80-125">Initializing an Auto-Implemented Property</span></span>  

 <span data-ttu-id="60b80-126">Cualquier expresión que se pueda usar para inicializar un campo es válida para inicializar una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="60b80-126">Any expression that can be used to initialize a field is valid for initializing an auto-implemented property.</span></span> <span data-ttu-id="60b80-127">Al inicializar una propiedad implementada automáticamente, la expresión se evalúa y se pasa al procedimiento `Set` para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="60b80-127">When you initialize an auto-implemented property, the expression is evaluated and passed to the `Set` procedure for the property.</span></span> <span data-ttu-id="60b80-128">En los ejemplos de código siguientes se muestran algunas propiedades implementadas automáticamente que incluyen valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="60b80-128">The following code examples show some auto-implemented properties that include initial values.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#3)]  
  
 <span data-ttu-id="60b80-129">No se puede inicializar una propiedad implementada automáticamente que sea miembro de una `Interface` o que esté marcada como `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="60b80-129">You cannot initialize an auto-implemented property that is a member of an `Interface`, or one that is marked `MustOverride`.</span></span>  
  
 <span data-ttu-id="60b80-130">Al declarar una propiedad implementada automáticamente como miembro de una `Structure`, solo se puede inicializar la propiedad implementada automáticamente si se marca como `Shared`.</span><span class="sxs-lookup"><span data-stu-id="60b80-130">When you declare an auto-implemented property as a member of a `Structure`, you can only initialize the auto-implemented property if it is marked as `Shared`.</span></span>  
  
 <span data-ttu-id="60b80-131">Al declarar una propiedad implementada automáticamente como matriz, no se pueden especificar límites de matriz explícitos.</span><span class="sxs-lookup"><span data-stu-id="60b80-131">When you declare an auto-implemented property as an array, you cannot specify explicit array bounds.</span></span> <span data-ttu-id="60b80-132">Sin embargo, se puede proporcionar un valor con un inicializador de matriz, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="60b80-132">However, you can supply a value by using an array initializer, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#4)]  
  
## <a name="property-definitions-that-require-standard-syntax"></a><span data-ttu-id="60b80-133">Definiciones de propiedades que requieren sintaxis estándar</span><span class="sxs-lookup"><span data-stu-id="60b80-133">Property Definitions That Require Standard Syntax</span></span>  

 <span data-ttu-id="60b80-134">Las propiedades implementadas automáticamente son fáciles de usar y admiten muchos escenarios de programación.</span><span class="sxs-lookup"><span data-stu-id="60b80-134">Auto-implemented properties are convenient and support many programming scenarios.</span></span> <span data-ttu-id="60b80-135">Sin embargo, hay situaciones en las que no se puede usar una propiedad implementada automáticamente y, en su lugar, se debe usar la sintaxis de propiedades estándar o *expandida*.</span><span class="sxs-lookup"><span data-stu-id="60b80-135">However, there are situations in which you cannot use an auto-implemented property and must instead use standard, or *expanded*, property syntax.</span></span>  
  
 <span data-ttu-id="60b80-136">Si desea realizar una de las acciones siguientes, tiene que usar la sintaxis de definición de propiedades expandidas:</span><span class="sxs-lookup"><span data-stu-id="60b80-136">You have to use expanded property-definition syntax if you want to do any one of the following:</span></span>  
  
- <span data-ttu-id="60b80-137">Agregar código al procedimiento `Get` o `Set` de una propiedad, como código para validar los valores de entrada del procedimiento `Set`.</span><span class="sxs-lookup"><span data-stu-id="60b80-137">Add code to the `Get` or `Set` procedure of a property, such as code to validate incoming values in the `Set` procedure.</span></span> <span data-ttu-id="60b80-138">Por ejemplo, puede que desee comprobar si una cadena que representa un número de teléfono contiene la cantidad de números necesaria antes de establecer el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="60b80-138">For example, you might want to verify that a string that represents a telephone number contains the required number of numerals before setting the property value.</span></span>  
  
- <span data-ttu-id="60b80-139">Especificar distintos tipos de accesibilidad para los procedimientos `Get` y `Set`.</span><span class="sxs-lookup"><span data-stu-id="60b80-139">Specify different accessibility for the `Get` and `Set` procedure.</span></span> <span data-ttu-id="60b80-140">Por ejemplo, puede que desee establecer el procedimiento `Set` como `Private` y el procedimiento `Get` como `Public`.</span><span class="sxs-lookup"><span data-stu-id="60b80-140">For example, you might want to make the `Set` procedure `Private` and the `Get` procedure `Public`.</span></span>  
  
- <span data-ttu-id="60b80-141">Crear propiedades de tipo `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="60b80-141">Create properties that are `WriteOnly`.</span></span>  
  
- <span data-ttu-id="60b80-142">Usar propiedades parametrizadas (incluidas las propiedades `Default`).</span><span class="sxs-lookup"><span data-stu-id="60b80-142">Use parameterized properties (including `Default` properties).</span></span> <span data-ttu-id="60b80-143">Debe declarar una propiedad expandida para especificar un parámetro para la propiedad o para especificar parámetros adicionales para el procedimiento `Set`.</span><span class="sxs-lookup"><span data-stu-id="60b80-143">You must declare an expanded property in order to specify a parameter for the property, or to specify additional parameters for the `Set` procedure.</span></span>  
  
- <span data-ttu-id="60b80-144">Colocar un atributo en el campo de respaldo o cambiar el nivel de acceso del campo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="60b80-144">Place an attribute on the backing field, or change the access level of the backing field.</span></span>  
  
- <span data-ttu-id="60b80-145">Proporcionar comentarios XML para el campo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="60b80-145">Provide XML comments for the backing field.</span></span>  
  
## <a name="expanding-an-auto-implemented-property"></a><span data-ttu-id="60b80-146">Expandir una propiedad implementada automáticamente</span><span class="sxs-lookup"><span data-stu-id="60b80-146">Expanding an Auto-Implemented Property</span></span>  

 <span data-ttu-id="60b80-147">Si tiene que convertir una propiedad implementada automáticamente en una propiedad expandida que contiene un procedimiento `Get` o `Set`, el Editor de código de Visual Basic puede generar automáticamente los procedimientos `Get` y `Set` y la instrucción `End Property` para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="60b80-147">If you have to convert an auto-implemented property to an expanded property that contains a `Get` or `Set` procedure, the Visual Basic Code Editor can automatically generate the `Get` and `Set` procedures and `End Property` statement for the property.</span></span> <span data-ttu-id="60b80-148">El código se genera si coloca el cursor en una línea en blanco después de la `Property` instrucción, escriba `G` (para `Get` ) o `S` (para `Set` ) y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="60b80-148">The code is generated if you put the cursor on a blank line following the `Property` statement, type a `G` (for `Get`) or an `S` (for `Set`) and press ENTER.</span></span> <span data-ttu-id="60b80-149">El Editor de código de Visual Basic genera automáticamente el procedimiento `Get` o `Set` para las propiedades de solo lectura y de solo escritura al presionar ENTRAR al final de una instrucción `Property`.</span><span class="sxs-lookup"><span data-stu-id="60b80-149">The Visual Basic Code Editor automatically generates the `Get` or `Set` procedure for read-only and write-only properties when you press ENTER at the end of a `Property` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b80-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60b80-150">See also</span></span>

- [<span data-ttu-id="60b80-151">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60b80-151">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="60b80-152">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="60b80-152">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="60b80-153">Property Statement</span><span class="sxs-lookup"><span data-stu-id="60b80-153">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="60b80-154">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="60b80-154">ReadOnly</span></span>](../../../language-reference/modifiers/readonly.md)
- [<span data-ttu-id="60b80-155">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="60b80-155">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="60b80-156">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="60b80-156">Objects and Classes</span></span>](../objects-and-classes/index.md)
