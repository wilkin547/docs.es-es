---
description: 'Más información acerca de: Tutorial: implementar la herencia con objetos COM (Visual Basic)'
title: 'Tutorial: Implementación de la herencia mediante objetos COM'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: dc16990f25126cba52ef3ea457e8c3157c987c60
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438949"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="e4bf8-103">Tutorial: Implementar la herencia mediante objetos COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4bf8-103">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>

<span data-ttu-id="e4bf8-104">Puede derivar Visual Basic clases de `Public` clases de objetos com, incluso las creadas en versiones anteriores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-104">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="e4bf8-105">Las propiedades y los métodos de las clases heredadas de objetos COM se pueden invalidar o sobrecargar del mismo modo que las propiedades y los métodos de cualquier otra clase base se pueden invalidar o sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-105">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="e4bf8-106">La herencia de objetos COM resulta útil cuando tiene una biblioteca de clases existente que no desea volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-106">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>

<span data-ttu-id="e4bf8-107">En el procedimiento siguiente se muestra cómo utilizar Visual Basic 6,0 para crear un objeto COM que contenga una clase y, a continuación, utilizarlo como clase base.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-107">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="e4bf8-108">Para compilar el objeto COM que se usa en este tutorial</span><span class="sxs-lookup"><span data-stu-id="e4bf8-108">To build the COM object that is used in this walkthrough</span></span>

1. <span data-ttu-id="e4bf8-109">En Visual Basic 6,0, abra un nuevo proyecto DLL de ActiveX.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-109">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="e4bf8-110">Se crea un proyecto denominado `Project1` .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-110">A project named `Project1` is created.</span></span> <span data-ttu-id="e4bf8-111">Tiene una clase denominada `Class1` .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-111">It has a class named `Class1`.</span></span>

2. <span data-ttu-id="e4bf8-112">En el **Explorador de proyectos**, haga clic con el botón secundario en **Project1** y, a continuación, haga clic en **propiedades de Project1**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-112">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="e4bf8-113">Se muestra el cuadro de diálogo **propiedades del proyecto** .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-113">The **Project Properties** dialog box is displayed.</span></span>

3. <span data-ttu-id="e4bf8-114">En la pestaña **General** del cuadro de diálogo **propiedades del proyecto** , cambie el nombre del proyecto escribiendo `ComObject1` en el campo **nombre del proyecto** .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-114">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>

4. <span data-ttu-id="e4bf8-115">En el **Explorador de proyectos**, haga clic con el botón secundario `Class1` y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-115">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="e4bf8-116">Se muestra la ventana **propiedades** de la clase.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-116">The **Properties** window for the class is displayed.</span></span>

5. <span data-ttu-id="e4bf8-117">Cambie la `Name` propiedad a `MathFunctions` .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-117">Change the `Name` property to `MathFunctions`.</span></span>

6. <span data-ttu-id="e4bf8-118">En el **Explorador de proyectos**, haga clic con el botón secundario `MathFunctions` y, a continuación, haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-118">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="e4bf8-119">Se muestra el **Editor de código** .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-119">The **Code Editor** is displayed.</span></span>

7. <span data-ttu-id="e4bf8-120">Agregue una variable local para que contenga el valor de propiedad:</span><span class="sxs-lookup"><span data-stu-id="e4bf8-120">Add a local variable to hold the property value:</span></span>

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. <span data-ttu-id="e4bf8-121">Agregue `Let` los procedimientos de propiedad y propiedad de propiedad `Get` :</span><span class="sxs-lookup"><span data-stu-id="e4bf8-121">Add Property `Let` and Property `Get` property procedures:</span></span>

    ```vb
    Public Property Let Prop1(ByVal vData As Integer)
       'Used when assigning a value to the property.
       mvarProp1 = vData
    End Property
    Public Property Get Prop1() As Integer
       'Used when retrieving a property's value.
       Prop1 = mvarProp1
    End Property
    ```

9. <span data-ttu-id="e4bf8-122">Agregue una función:</span><span class="sxs-lookup"><span data-stu-id="e4bf8-122">Add a function:</span></span>

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. <span data-ttu-id="e4bf8-123">Cree y registre el objeto COM; para ello, haga clic en **crear ComObject1.dll** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-123">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4bf8-124">Aunque también puede exponer una clase creada con Visual Basic como un objeto COM, no es un objeto COM verdadero y no se puede usar en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-124">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="e4bf8-125">Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="e4bf8-125">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>

## <a name="interop-assemblies"></a><span data-ttu-id="e4bf8-126">Ensamblados de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="e4bf8-126">Interop Assemblies</span></span>

<span data-ttu-id="e4bf8-127">En el procedimiento siguiente, creará un ensamblado de interoperabilidad, que actúa como un puente entre el código no administrado (por ejemplo, un objeto COM) y el código administrado que usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-127">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="e4bf8-128">El ensamblado de interoperabilidad que Visual Basic crea controla muchos de los detalles del trabajo con objetos COM, como el *cálculo de referencias de interoperabilidad*, el proceso de empaquetado de parámetros y valores devueltos en tipos de datos equivalentes a medida que se mueven a objetos com y desde ellos.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-128">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="e4bf8-129">La referencia de la aplicación Visual Basic apunta al ensamblado de interoperabilidad, no al objeto COM real.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-129">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="e4bf8-130">Para usar un objeto COM con Visual Basic 2005 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e4bf8-130">To use a COM object with Visual Basic 2005 and later versions</span></span>

1. <span data-ttu-id="e4bf8-131">Abra un proyecto Aplicación Windows de Visual Basic nuevo.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-131">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="e4bf8-132">En el menú **Proyecto**, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-132">On the **Project** menu, click **Add Reference**.</span></span>

     <span data-ttu-id="e4bf8-133">Aparecerá el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-133">The **Add Reference** dialog box is displayed.</span></span>

3. <span data-ttu-id="e4bf8-134">En la pestaña **com** , haga doble clic `ComObject1` en la lista **nombre de componente** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-134">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>

4. <span data-ttu-id="e4bf8-135">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-135">On the **Project** menu, click **Add New Item**.</span></span>

     <span data-ttu-id="e4bf8-136">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-136">The **Add New Item** dialog box is displayed.</span></span>

5. <span data-ttu-id="e4bf8-137">En el panel **plantillas** , haga clic en **clase**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-137">In the **Templates** pane, click **Class**.</span></span>

     <span data-ttu-id="e4bf8-138">El nombre de archivo predeterminado, `Class1.vb` , aparece en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-138">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="e4bf8-139">Cambie este campo a MathClass. VB y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-139">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="e4bf8-140">Esto crea una clase denominada `MathClass` y muestra su código.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-140">This creates a class named `MathClass`, and displays its code.</span></span>

6. <span data-ttu-id="e4bf8-141">Agregue el código siguiente al principio de `MathClass` para que herede de la clase com.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-141">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. <span data-ttu-id="e4bf8-142">Sobrecargue el método público de la clase base agregando el código siguiente a `MathClass` :</span><span class="sxs-lookup"><span data-stu-id="e4bf8-142">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. <span data-ttu-id="e4bf8-143">Extienda la clase heredada agregando el código siguiente a `MathClass` :</span><span class="sxs-lookup"><span data-stu-id="e4bf8-143">Extend the inherited class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

<span data-ttu-id="e4bf8-144">La nueva clase hereda las propiedades de la clase base en el objeto COM, sobrecarga un método y define un nuevo método para extender la clase.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-144">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>

### <a name="to-test-the-inherited-class"></a><span data-ttu-id="e4bf8-145">Para probar la clase heredada</span><span class="sxs-lookup"><span data-stu-id="e4bf8-145">To test the inherited class</span></span>

1. <span data-ttu-id="e4bf8-146">Agregue un botón al formulario de inicio y, a continuación, haga doble clic en él para ver su código.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-146">Add a button to your startup form, and then double-click it to view its code.</span></span>

2. <span data-ttu-id="e4bf8-147">En el procedimiento de `Click` controlador de eventos del botón, agregue el código siguiente para crear una instancia de `MathClass` y llamar a los métodos sobrecargados:</span><span class="sxs-lookup"><span data-stu-id="e4bf8-147">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. <span data-ttu-id="e4bf8-148">Ejecute el proyecto presionando F5.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-148">Run the project by pressing F5.</span></span>

<span data-ttu-id="e4bf8-149">Al hacer clic en el botón del formulario, `AddNumbers` se llama primero al método con `Short` números de tipo de datos y Visual Basic elige el método adecuado de la clase base.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-149">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="e4bf8-150">La segunda llamada a `AddNumbers` se dirige al método de sobrecarga desde `MathClass` .</span><span class="sxs-lookup"><span data-stu-id="e4bf8-150">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="e4bf8-151">La tercera llamada llama al `SubtractNumbers` método, que extiende la clase.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-151">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="e4bf8-152">Se establece la propiedad de la clase base y se muestra el valor.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-152">The property in the base class is set, and the value is displayed.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4bf8-153">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e4bf8-153">Next Steps</span></span>

<span data-ttu-id="e4bf8-154">Es posible que haya observado que la función sobrecargada `AddNumbers` parece tener el mismo tipo de datos que el método heredado de la clase base del objeto com.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-154">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="e4bf8-155">Esto se debe a que los argumentos y los parámetros del método de la clase base se definen como enteros de 16 bits en Visual Basic 6,0, pero se exponen como enteros de 16 bits de tipo `Short` en versiones posteriores de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-155">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="e4bf8-156">La nueva función acepta enteros de 32 bits y sobrecarga la función de clase base.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-156">The new function accepts 32-bit integers, and overloads the base class function.</span></span>

<span data-ttu-id="e4bf8-157">Al trabajar con objetos COM, asegúrese de comprobar el tamaño y los tipos de datos de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-157">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="e4bf8-158">Por ejemplo, cuando se usa un objeto COM que acepta un objeto de colección Visual Basic 6,0 como argumento, no se puede proporcionar una colección de una versión posterior de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-158">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>

<span data-ttu-id="e4bf8-159">Se pueden invalidar las propiedades y los métodos heredados de las clases COM, lo que significa que puede declarar una propiedad o un método local que reemplace una propiedad o un método heredado de una clase COM base.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-159">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="e4bf8-160">Las reglas para reemplazar propiedades COM heredadas son similares a las reglas para invalidar otras propiedades y métodos con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="e4bf8-160">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>

- <span data-ttu-id="e4bf8-161">Si invalida cualquier propiedad o método heredado de una clase COM, debe invalidar todas las demás propiedades y métodos heredados.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-161">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>

- <span data-ttu-id="e4bf8-162">Las propiedades que usan `ByRef` parámetros no se pueden invalidar.</span><span class="sxs-lookup"><span data-stu-id="e4bf8-162">Properties that use `ByRef` parameters cannot be overridden.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4bf8-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4bf8-163">See also</span></span>

- [<span data-ttu-id="e4bf8-164">Interoperabilidad COM en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e4bf8-164">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="e4bf8-165">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="e4bf8-165">Inherits Statement</span></span>](../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="e4bf8-166">Tipo de datos Short</span><span class="sxs-lookup"><span data-stu-id="e4bf8-166">Short Data Type</span></span>](../../language-reference/data-types/short-data-type.md)
