---
title: 'Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: ee7258a78ad0a434bfad08eebd596a8b889e2304
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826176"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="46aeb-102">Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46aeb-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="46aeb-103">Puede derivar clases de Visual Basic desde `Public` clases de objetos COM, incluso los creados en versiones anteriores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46aeb-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="46aeb-104">Las propiedades y métodos de clases que heredan de los objetos COM pueden ser invalidados o sobrecargados solo como propiedades y métodos de cualquier otra clase base pueden ser invalidados o sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="46aeb-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="46aeb-105">Herencia de objetos COM resulta útil cuando tiene una biblioteca de clases que no desea volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="46aeb-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="46aeb-106">El procedimiento siguiente muestra cómo usar Visual Basic 6.0 para crear un objeto COM que contiene una clase y, a continuación, usarlo como clase base.</span><span class="sxs-lookup"><span data-stu-id="46aeb-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="46aeb-107">Para crear el objeto COM que se usa en este tutorial</span><span class="sxs-lookup"><span data-stu-id="46aeb-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="46aeb-108">En Visual Basic 6.0, abra un nuevo proyecto de DLL de ActiveX.</span><span class="sxs-lookup"><span data-stu-id="46aeb-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="46aeb-109">Un proyecto denominado `Project1` se crea.</span><span class="sxs-lookup"><span data-stu-id="46aeb-109">A project named `Project1` is created.</span></span> <span data-ttu-id="46aeb-110">Tiene una clase denominada `Class1`.</span><span class="sxs-lookup"><span data-stu-id="46aeb-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="46aeb-111">En el **Explorador de proyectos**, haga clic en **Project1**y, a continuación, haga clic en **Project1 propiedades**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="46aeb-112">El **las propiedades del proyecto** se muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="46aeb-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="46aeb-113">En el **General** pestaña de la **las propiedades del proyecto** cuadro de diálogo, cambie el nombre del proyecto escribiendo `ComObject1` en el **nombre del proyecto** campo.</span><span class="sxs-lookup"><span data-stu-id="46aeb-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="46aeb-114">En el **Explorador de proyectos**, haga clic en `Class1`y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="46aeb-115">El **propiedades** se muestra la ventana de la clase.</span><span class="sxs-lookup"><span data-stu-id="46aeb-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="46aeb-116">Cambiar el `Name` propiedad `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="46aeb-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="46aeb-117">En el **Explorador de proyectos**, haga clic en `MathFunctions`y, a continuación, haga clic en **ver código**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="46aeb-118">El **Editor de código** se muestra.</span><span class="sxs-lookup"><span data-stu-id="46aeb-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="46aeb-119">Agregue una variable local para almacenar el valor de propiedad:</span><span class="sxs-lookup"><span data-stu-id="46aeb-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="46aeb-120">Agregar propiedad `Let` y propiedad `Get` procedimientos de propiedad:</span><span class="sxs-lookup"><span data-stu-id="46aeb-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. <span data-ttu-id="46aeb-121">Agregue una función:</span><span class="sxs-lookup"><span data-stu-id="46aeb-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="46aeb-122">Crear y registrar el objeto COM haciendo **ComObject1.dll realizar** en el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="46aeb-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46aeb-123">También puede exponer una clase creada con Visual Basic como un objeto COM, no es un verdadero objeto COM y no se puede usar en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="46aeb-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="46aeb-124">Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="46aeb-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="46aeb-125">Ensamblados de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="46aeb-125">Interop Assemblies</span></span>  
 <span data-ttu-id="46aeb-126">En el siguiente procedimiento, creará un ensamblado de interoperabilidad, que actúa como puente entre el código no administrado (por ejemplo, un objeto COM) y el código administrado que usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="46aeb-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="46aeb-127">El ensamblado de interoperabilidad que crea Visual Basic controla muchos de los detalles del trabajo con objetos COM, como *la serialización de interoperabilidad*, el proceso de empaquetado de parámetros y valores devueltos en datos equivalentes tipos cuando se mueven a y de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="46aeb-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="46aeb-128">La referencia de la aplicación Visual Basic apunta al ensamblado de interoperabilidad, no al objeto COM real.</span><span class="sxs-lookup"><span data-stu-id="46aeb-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="46aeb-129">Para utilizar un objeto COM con Visual Basic 2005 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="46aeb-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="46aeb-130">Abra un proyecto Aplicación Windows de Visual Basic nuevo.</span><span class="sxs-lookup"><span data-stu-id="46aeb-130">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="46aeb-131">En el menú **Proyecto**, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="46aeb-132">Aparecerá el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="46aeb-133">En el **COM** , haga doble clic `ComObject1` en el **nombre del componente** lista y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="46aeb-134">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="46aeb-135">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="46aeb-136">En el **plantillas** panel, haga clic en **clase**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="46aeb-137">El nombre de archivo predeterminado, `Class1.vb`, aparece en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="46aeb-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="46aeb-138">Modifique este campo MathClass.vb y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="46aeb-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="46aeb-139">Esto crea una clase denominada `MathClass`y muestra su código.</span><span class="sxs-lookup"><span data-stu-id="46aeb-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="46aeb-140">Agregue el código siguiente al principio del `MathClass` para heredar de la clase COM.</span><span class="sxs-lookup"><span data-stu-id="46aeb-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]  
  
7.  <span data-ttu-id="46aeb-141">Sobrecargar el método público de la clase base agregando el código siguiente al `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="46aeb-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]  
  
8.  <span data-ttu-id="46aeb-142">Extender la clase heredada agregando el código siguiente al `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="46aeb-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]  
  
 <span data-ttu-id="46aeb-143">La nueva clase hereda las propiedades de la clase base en el objeto COM, sobrecarga un método y define un nuevo método para extender la clase.</span><span class="sxs-lookup"><span data-stu-id="46aeb-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="46aeb-144">Para probar la clase heredada</span><span class="sxs-lookup"><span data-stu-id="46aeb-144">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="46aeb-145">Agregue un botón al formulario de inicio y, a continuación, haga doble clic en él para ver su código.</span><span class="sxs-lookup"><span data-stu-id="46aeb-145">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="46aeb-146">En el botón `Click` procedimiento del controlador de eventos, agregue el código siguiente para crear una instancia de `MathClass` y llamar a los métodos sobrecargados:</span><span class="sxs-lookup"><span data-stu-id="46aeb-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]  
  
3.  <span data-ttu-id="46aeb-147">Ejecute el proyecto presionando F5.</span><span class="sxs-lookup"><span data-stu-id="46aeb-147">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="46aeb-148">Al hacer clic en el botón en el formulario, el `AddNumbers` primero se llama al método con `Short` números, tipo de datos y Visual Basic, se elige el método adecuado de la clase base.</span><span class="sxs-lookup"><span data-stu-id="46aeb-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="46aeb-149">La segunda llamada a `AddNumbers` se dirige a la sobrecarga del método de `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="46aeb-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="46aeb-150">La tercera llamadas llamadas la `SubtractNumbers` método, que extiende la clase.</span><span class="sxs-lookup"><span data-stu-id="46aeb-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="46aeb-151">Se establece la propiedad de la clase base, y se muestra el valor.</span><span class="sxs-lookup"><span data-stu-id="46aeb-151">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="46aeb-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="46aeb-152">Next Steps</span></span>  
 <span data-ttu-id="46aeb-153">Es podrán que haya observado que sobrecargado `AddNumbers` función parece tener los mismos datos de tipo que el método se hereda de la clase base del objeto COM.</span><span class="sxs-lookup"><span data-stu-id="46aeb-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="46aeb-154">Esto es porque los argumentos y parámetros de método de clase base se definen como enteros de 16 bits en Visual Basic 6.0, pero se exponen como enteros de 16 bits de tipo `Short` en versiones posteriores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46aeb-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="46aeb-155">La nueva función acepta enteros de 32 bits y sobrecarga de la función de la clase base.</span><span class="sxs-lookup"><span data-stu-id="46aeb-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="46aeb-156">Cuando se trabaja con objetos COM, asegúrese de que compruebe el tamaño y tipos de datos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="46aeb-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="46aeb-157">Por ejemplo, cuando se usa un objeto COM que acepta un objeto de colección de Visual Basic 6.0 como argumento, no puede proporcionar una colección de una versión posterior de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46aeb-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="46aeb-158">Pueden invalidar las propiedades y métodos heredados de las clases COM, lo que significa que puede declarar una propiedad local o un método que reemplaza una propiedad o método heredado de una clase COM base.</span><span class="sxs-lookup"><span data-stu-id="46aeb-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="46aeb-159">Las reglas para reemplazar propiedades COM heredadas son similares a las reglas para reemplazar otras propiedades y métodos con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="46aeb-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="46aeb-160">Si reemplaza cualquier propiedad o método heredado de una clase COM, debe reemplazar todas las demás propiedades heredadas y métodos.</span><span class="sxs-lookup"><span data-stu-id="46aeb-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="46aeb-161">Las propiedades que usan `ByRef` no se puede invalidar los parámetros.</span><span class="sxs-lookup"><span data-stu-id="46aeb-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46aeb-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="46aeb-162">See also</span></span>

- [<span data-ttu-id="46aeb-163">Interoperabilidad COM en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="46aeb-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="46aeb-164">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="46aeb-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="46aeb-165">Short (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="46aeb-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
