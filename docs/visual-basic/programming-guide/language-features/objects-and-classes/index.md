---
description: 'Más información sobre: objetos y clases en Visual Basic'
title: Objetos y clases
ms.date: 05/26/2020
helpviewer_keywords:
- classes [Visual Basic]
- objects [Visual Basic]
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
ms.openlocfilehash: 9cefcc117c9dd4ac42940f342dbf75d8ddb4f41d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462729"
---
# <a name="objects-and-classes-in-visual-basic"></a><span data-ttu-id="d3647-103">Objetos y clases de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3647-103">Objects and classes in Visual Basic</span></span>

<span data-ttu-id="d3647-104">Un *objeto* es una combinación de código y datos que se pueden tratar como una unidad.</span><span class="sxs-lookup"><span data-stu-id="d3647-104">An *object* is a combination of code and data that can be treated as a unit.</span></span> <span data-ttu-id="d3647-105">Un objeto puede ser una parte de una aplicación, como un control o un formulario.</span><span class="sxs-lookup"><span data-stu-id="d3647-105">An object can be a piece of an application, like a control or a form.</span></span> <span data-ttu-id="d3647-106">Toda la aplicación también puede ser un objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-106">An entire application can also be an object.</span></span>

<span data-ttu-id="d3647-107">Cuando se crea una aplicación en Visual Basic, se trabaja constantemente con objetos.</span><span class="sxs-lookup"><span data-stu-id="d3647-107">When you create an application in Visual Basic, you constantly work with objects.</span></span> <span data-ttu-id="d3647-108">Puede usar los objetos proporcionados por Visual Basic, como los controles, los formularios y los objetos de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="d3647-108">You can use objects provided by Visual Basic, such as controls, forms, and data access objects.</span></span> <span data-ttu-id="d3647-109">También puede utilizar objetos de otras aplicaciones dentro de la aplicación Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3647-109">You can also use objects from other applications within your Visual Basic application.</span></span> <span data-ttu-id="d3647-110">Incluso puede crear sus propios objetos y definir propiedades y métodos adicionales para ellos.</span><span class="sxs-lookup"><span data-stu-id="d3647-110">You can even create your own objects and define additional properties and methods for them.</span></span> <span data-ttu-id="d3647-111">Los objetos actúan como bloques de compilación prefabricados que permiten escribir un fragmento de código de una vez y utilizarlo una y otra vez.</span><span class="sxs-lookup"><span data-stu-id="d3647-111">Objects act like prefabricated building blocks for programs — they let you write a piece of code once and reuse it over and over.</span></span>

<span data-ttu-id="d3647-112">En este tema se proporciona información detallada sobre los objetos.</span><span class="sxs-lookup"><span data-stu-id="d3647-112">This topic discusses objects in detail.</span></span>

## <a name="objects-and-classes"></a><span data-ttu-id="d3647-113">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="d3647-113">Objects and classes</span></span>

<span data-ttu-id="d3647-114">Cada objeto de Visual Basic se define mediante una *clase*.</span><span class="sxs-lookup"><span data-stu-id="d3647-114">Each object in Visual Basic is defined by a *class*.</span></span> <span data-ttu-id="d3647-115">Una clase describe las variables, las propiedades, los procedimientos y los eventos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-115">A class describes the variables, properties, procedures, and events of an object.</span></span> <span data-ttu-id="d3647-116">Los objetos son instancias de clases; puede crear tantos objetos como sean necesarios una vez que haya definido una clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-116">Objects are instances of classes; you can create as many objects you need once you have defined a class.</span></span>

<span data-ttu-id="d3647-117">Para comprender la relación entre un objeto y su clase, piense en las galletas y en su molde.</span><span class="sxs-lookup"><span data-stu-id="d3647-117">To understand the relationship between an object and its class, think of cookie cutters and cookies.</span></span> <span data-ttu-id="d3647-118">El molde de la galleta es la clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-118">The cookie cutter is the class.</span></span> <span data-ttu-id="d3647-119">Define las características de cada galleta, por ejemplo, tamaño y forma.</span><span class="sxs-lookup"><span data-stu-id="d3647-119">It defines the characteristics of each cookie, for example size and shape.</span></span> <span data-ttu-id="d3647-120">La clase se usa para crear objetos.</span><span class="sxs-lookup"><span data-stu-id="d3647-120">The class is used to create objects.</span></span> <span data-ttu-id="d3647-121">Los objetos son las galletas.</span><span class="sxs-lookup"><span data-stu-id="d3647-121">The objects are the cookies.</span></span>

<span data-ttu-id="d3647-122">Debe crear un objeto para poder tener acceso a sus miembros, salvo para [`Shared`](../../../language-reference/modifiers/shared.md) los miembros a los que se puede tener acceso sin un objeto de la clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-122">You must create an object before you can access its members, except for [`Shared`](../../../language-reference/modifiers/shared.md) members which can be accessed without an object of the class.</span></span>

### <a name="create-an-object-from-a-class"></a><span data-ttu-id="d3647-123">Creación de un objeto a partir de una clase</span><span class="sxs-lookup"><span data-stu-id="d3647-123">Create an object from a class</span></span>

1. <span data-ttu-id="d3647-124">Determine en qué clase desea crear un objeto o defina su propia clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-124">Determine from which class you want to create an object, or define your own class.</span></span> <span data-ttu-id="d3647-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d3647-125">For example:</span></span>

   ```vb
   Public Class Customer
       Public Property AccountNumber As Integer
   End Class
   ```

2. <span data-ttu-id="d3647-126">Escriba una [instrucción Dim](../../../language-reference/statements/dim-statement.md) para crear una variable a la que pueda asignar una instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-126">Write a [Dim Statement](../../../language-reference/statements/dim-statement.md) to create a variable to which you can assign a class instance.</span></span> <span data-ttu-id="d3647-127">La variable debe ser del tipo de la clase deseada.</span><span class="sxs-lookup"><span data-stu-id="d3647-127">The variable should be of the type of the desired class.</span></span>

   ```vb
   Dim nextCustomer As Customer
   ```

3. <span data-ttu-id="d3647-128">Agregue la palabra clave [Nuevo operador](../../../language-reference/operators/new-operator.md) para inicializar la variable en una nueva instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-128">Add the [New Operator](../../../language-reference/operators/new-operator.md) keyword to initialize the variable to a new instance of the class.</span></span>

   ```vb
   Dim nextCustomer As New Customer
   ```

4. <span data-ttu-id="d3647-129">Ahora puede tener acceso a los miembros de la clase a través de la variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-129">You can now access the members of the class through the object variable.</span></span>

   ```vb
   nextCustomer.AccountNumber = lastAccountNumber + 1
   ```

> [!NOTE]
> <span data-ttu-id="d3647-130">Siempre que sea posible, debe declarar la variable para que sea del tipo de clase al que pretende asignarla.</span><span class="sxs-lookup"><span data-stu-id="d3647-130">Whenever possible, you should declare the variable to be of the class type you intend to assign to it.</span></span> <span data-ttu-id="d3647-131">Esto se denomina *enlace anticipado*.</span><span class="sxs-lookup"><span data-stu-id="d3647-131">This is called *early binding*.</span></span> <span data-ttu-id="d3647-132">Si no conoce el tipo de clase en tiempo de compilación, puede invocar el *enlace en tiempo de ejecución* mediante la declaración de la variable para que sea del [tipo de datos de objeto](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-132">If you don't know the class type at compile time, you can invoke *late binding* by declaring the variable to be of the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="d3647-133">Sin embargo, el enlace en tiempo de ejecución puede ralentizar el rendimiento y limitar el acceso a los miembros del objeto de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d3647-133">However, late binding can make performance slower and limit access to the run-time object's members.</span></span> <span data-ttu-id="d3647-134">Para más información, vea [Declaración de variables de objeto](../variables/object-variable-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-134">For more information, see [Object Variable Declaration](../variables/object-variable-declaration.md).</span></span>

### <a name="multiple-instances"></a><span data-ttu-id="d3647-135">Varias instancias</span><span class="sxs-lookup"><span data-stu-id="d3647-135">Multiple instances</span></span>

<span data-ttu-id="d3647-136">Los objetos recién creados a partir de una clase suelen ser idénticos entre sí.</span><span class="sxs-lookup"><span data-stu-id="d3647-136">Objects newly created from a class are often identical to each other.</span></span> <span data-ttu-id="d3647-137">Una vez que existen como objetos individuales, sin embargo, sus variables y propiedades se pueden cambiar independientemente de las otras instancias.</span><span class="sxs-lookup"><span data-stu-id="d3647-137">Once they exist as individual objects, however, their variables and properties can be changed independently of the other instances.</span></span> <span data-ttu-id="d3647-138">Por ejemplo, si agrega tres casillas a un formulario, cada objeto de casilla es una instancia de la clase <xref:System.Windows.Forms.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="d3647-138">For example, if you add three check boxes to a form, each check box object is an instance of the <xref:System.Windows.Forms.CheckBox> class.</span></span> <span data-ttu-id="d3647-139">Los objetos <xref:System.Windows.Forms.CheckBox> individuales comparten un conjunto común de características y funciones (propiedades, variables, procedimientos y eventos) que define la clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-139">The individual <xref:System.Windows.Forms.CheckBox> objects share a common set of characteristics and capabilities (properties, variables, procedures, and events) defined by the class.</span></span> <span data-ttu-id="d3647-140">Sin embargo, cada uno tiene su propio nombre, pueden habilitarse y deshabilitarse por separado y se pueden colocar en una ubicación distinta en el formulario.</span><span class="sxs-lookup"><span data-stu-id="d3647-140">However, each has its own name, can be separately enabled and disabled, and can be placed in a different location on the form.</span></span>

## <a name="object-members"></a><span data-ttu-id="d3647-141">Miembros de objetos</span><span class="sxs-lookup"><span data-stu-id="d3647-141">Object members</span></span>

<span data-ttu-id="d3647-142">Un objeto es un elemento de una aplicación, que representa una *instancia* de una clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-142">An object is an element of an application, representing an *instance* of a class.</span></span> <span data-ttu-id="d3647-143">Los campos, las propiedades, los métodos y los eventos son los bloques de compilación de objetos y constituyen sus *miembros*.</span><span class="sxs-lookup"><span data-stu-id="d3647-143">Fields, properties, methods, and events are the building blocks of objects and constitute their *members*.</span></span>

### <a name="member-access"></a><span data-ttu-id="d3647-144">Acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="d3647-144">Member Access</span></span>

<span data-ttu-id="d3647-145">Para acceder al miembro de un objeto, especifique, en este mismo orden, el nombre de la variable de objeto, un punto (`.`) y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="d3647-145">You access a member of an object by specifying, in order, the name of the object variable, a period (`.`), and the name of the member.</span></span> <span data-ttu-id="d3647-146">En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Forms.Control.Text%2A> de un objeto <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="d3647-146">The following example sets the <xref:System.Windows.Forms.Control.Text%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
warningLabel.Text = "Data not saved"
```

#### <a name="intellisense-listing-of-members"></a><span data-ttu-id="d3647-147">Lista de miembros de IntelliSense</span><span class="sxs-lookup"><span data-stu-id="d3647-147">IntelliSense listing of members</span></span>

<span data-ttu-id="d3647-148">IntelliSense muestra los miembros de una clase cuando invoca su opción Lista de miembros, por ejemplo, al escribir un punto (`.`) como un operador de acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="d3647-148">IntelliSense lists members of a class when you invoke its List Members option, for example when you type a period (`.`) as a member-access operator.</span></span> <span data-ttu-id="d3647-149">Si escribe el punto después del nombre de una variable declarada como una instancia de esa clase, IntelliSense muestra todos los miembros de instancia y ningún miembro compartido.</span><span class="sxs-lookup"><span data-stu-id="d3647-149">If you type the period following the name of a variable declared as an instance of that class, IntelliSense lists all the instance members and none of the shared members.</span></span> <span data-ttu-id="d3647-150">Si escribe el punto después del nombre de clase, IntelliSense muestra todos los miembros compartidos y ningún miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="d3647-150">If you type the period following the class name itself, IntelliSense lists all the shared members and none of the instance members.</span></span> <span data-ttu-id="d3647-151">Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="d3647-151">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>

### <a name="fields-and-properties"></a><span data-ttu-id="d3647-152">Campos y propiedades</span><span class="sxs-lookup"><span data-stu-id="d3647-152">Fields and properties</span></span>

<span data-ttu-id="d3647-153">Los *campos* y las *propiedades* representan información almacenada en un objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-153">*Fields* and *properties* represent information stored in an object.</span></span> <span data-ttu-id="d3647-154">Puede recuperar y establecer sus valores con instrucciones de asignación de la misma forma en que se recuperan y establecen las variables locales en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d3647-154">You retrieve and set their values with assignment statements the same way you retrieve and set local variables in a procedure.</span></span> <span data-ttu-id="d3647-155">En el ejemplo siguiente se recupera la propiedad <xref:System.Windows.Forms.Control.Width%2A> y se establece la propiedad <xref:System.Windows.Forms.Control.ForeColor%2A> de un objeto <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="d3647-155">The following example retrieves the <xref:System.Windows.Forms.Control.Width%2A> property and sets the <xref:System.Windows.Forms.Control.ForeColor%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
Dim warningWidth As Integer = warningLabel.Width
warningLabel.ForeColor = System.Drawing.Color.Red
```

<span data-ttu-id="d3647-156">Tenga en cuenta que a un campo también se le denomina *variable de miembro*.</span><span class="sxs-lookup"><span data-stu-id="d3647-156">Note that a field is also called a *member variable*.</span></span>

<span data-ttu-id="d3647-157">Use procedimientos de propiedad cuando:</span><span class="sxs-lookup"><span data-stu-id="d3647-157">Use property procedures when:</span></span>

- <span data-ttu-id="d3647-158">Necesite controlar cuándo y cómo se establece o recupera un valor.</span><span class="sxs-lookup"><span data-stu-id="d3647-158">You need to control when and how a value is set or retrieved.</span></span>

- <span data-ttu-id="d3647-159">La propiedad tiene un conjunto bien definido de valores que precisan de validación.</span><span class="sxs-lookup"><span data-stu-id="d3647-159">The property has a well-defined set of values that need to be validated.</span></span>

- <span data-ttu-id="d3647-160">La configuración del valor genera algún cambio perceptible en el estado del objeto, como una propiedad `IsVisible`.</span><span class="sxs-lookup"><span data-stu-id="d3647-160">Setting the value causes some perceptible change in the object's state, such as an `IsVisible` property.</span></span>

- <span data-ttu-id="d3647-161">La configuración de la propiedad provoca cambios en otras variables internas o en los valores de otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="d3647-161">Setting the property causes changes to other internal variables or to the values of other properties.</span></span>

- <span data-ttu-id="d3647-162">Es necesario realizar una serie de pasos antes de que la propiedad se pueda establecer o recuperar.</span><span class="sxs-lookup"><span data-stu-id="d3647-162">A set of steps must be performed before the property can be set or retrieved.</span></span>

<span data-ttu-id="d3647-163">Utilice campos cuando:</span><span class="sxs-lookup"><span data-stu-id="d3647-163">Use fields when:</span></span>

- <span data-ttu-id="d3647-164">El valor sea de un tipo de autovalidación.</span><span class="sxs-lookup"><span data-stu-id="d3647-164">The value is of a self-validating type.</span></span> <span data-ttu-id="d3647-165">Por ejemplo, se produce un error o una conversión de datos automática si un valor distinto de `True` o `False` se asigna a una variable `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d3647-165">For example, an error or automatic data conversion occurs if a value other than `True` or `False` is assigned to a `Boolean` variable.</span></span>

- <span data-ttu-id="d3647-166">Cualquier valor del intervalo admitido por el tipo de datos es válido.</span><span class="sxs-lookup"><span data-stu-id="d3647-166">Any value in the range supported by the data type is valid.</span></span> <span data-ttu-id="d3647-167">Esto mismo sucede con muchas propiedades del tipo `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="d3647-167">This is true of many properties of type `Single` or `Double`.</span></span>

- <span data-ttu-id="d3647-168">La propiedad es un tipo de datos `String`, y no hay ninguna restricción del tamaño o el valor de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d3647-168">The property is a `String` data type, and there is no constraint on the size or value of the string.</span></span>

- <span data-ttu-id="d3647-169">Para más información, vea [Procedimientos de propiedad](../procedures/property-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-169">For more information, see [Property Procedures](../procedures/property-procedures.md).</span></span>

> [!TIP]
> <span data-ttu-id="d3647-170">Mantenga siempre los campos no constantes privados.</span><span class="sxs-lookup"><span data-stu-id="d3647-170">Always keep the non-constant fields private.</span></span> <span data-ttu-id="d3647-171">Si desea que sea público, use una propiedad en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d3647-171">When you want to make it public, use a property instead.</span></span>

### <a name="methods"></a><span data-ttu-id="d3647-172">Métodos</span><span class="sxs-lookup"><span data-stu-id="d3647-172">Methods</span></span>

<span data-ttu-id="d3647-173">Un *método* es una acción que un objeto puede realizar.</span><span class="sxs-lookup"><span data-stu-id="d3647-173">A *method* is an action that an object can perform.</span></span> <span data-ttu-id="d3647-174">Por ejemplo, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> es un método del objeto <xref:System.Windows.Forms.ComboBox> que agrega una entrada nueva al cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="d3647-174">For example, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> is a method of the <xref:System.Windows.Forms.ComboBox> object that adds a new entry to a combo box.</span></span>

<span data-ttu-id="d3647-175">En el ejemplo siguiente se muestra el método <xref:System.Windows.Forms.Timer.Start%2A> de un objeto <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="d3647-175">The following example demonstrates the <xref:System.Windows.Forms.Timer.Start%2A> method of a <xref:System.Windows.Forms.Timer> object.</span></span>

```vb
Dim safetyTimer As New System.Windows.Forms.Timer
safetyTimer.Start()
```

<span data-ttu-id="d3647-176">Tenga en cuenta que un método es simplemente un *procedimiento* que se expone mediante un objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-176">Note that a method is simply a *procedure* that is exposed by an object.</span></span>

<span data-ttu-id="d3647-177">Para más información, vea [Procedimientos en Visual Basic](../procedures/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-177">For more information, see [Procedures](../procedures/index.md).</span></span>

### <a name="events"></a><span data-ttu-id="d3647-178">Eventos</span><span class="sxs-lookup"><span data-stu-id="d3647-178">Events</span></span>

<span data-ttu-id="d3647-179">Un evento es una acción reconocida por un objeto, como hacer clic con el ratón o presionar una tecla, para la que puede escribir código para que responda.</span><span class="sxs-lookup"><span data-stu-id="d3647-179">An event is an action recognized by an object, such as clicking the mouse or pressing a key, and for which you can write code to respond.</span></span> <span data-ttu-id="d3647-180">Los eventos pueden producirse como resultado de una acción del usuario o código de programa, o puede provocarlos el sistema.</span><span class="sxs-lookup"><span data-stu-id="d3647-180">Events can occur as a result of a user action or program code, or they can be caused by the system.</span></span> <span data-ttu-id="d3647-181">Se dice que el código que señala un evento *genera* el evento y el código que responde a él se dice que lo *controla*.</span><span class="sxs-lookup"><span data-stu-id="d3647-181">Code that signals an event is said to *raise* the event, and code that responds to it is said to *handle* it.</span></span>

<span data-ttu-id="d3647-182">También puede desarrollar sus propios eventos personalizados para que los generen sus objetos y los controlen otros objetos.</span><span class="sxs-lookup"><span data-stu-id="d3647-182">You can also develop your own custom events to be raised by your objects and handled by other objects.</span></span> <span data-ttu-id="d3647-183">Para más información, vea [Eventos](../events/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-183">For more information, see [Events](../events/index.md).</span></span>

### <a name="instance-members-and-shared-members"></a><span data-ttu-id="d3647-184">Miembros de instancia y miembros compartidos</span><span class="sxs-lookup"><span data-stu-id="d3647-184">Instance members and shared members</span></span>

<span data-ttu-id="d3647-185">Cuando se crea un objeto de una clase, el resultado es una instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-185">When you create an object from a class, the result is an instance of that class.</span></span> <span data-ttu-id="d3647-186">Los miembros no declarados con la palabra clave [Shared](../../../language-reference/modifiers/shared.md) son *miembros de instancia*, que pertenecen estrictamente a esa instancia concreta.</span><span class="sxs-lookup"><span data-stu-id="d3647-186">Members that are not declared with the [Shared](../../../language-reference/modifiers/shared.md) keyword are *instance members*, which belong strictly to that particular instance.</span></span> <span data-ttu-id="d3647-187">Un miembro de instancia en una instancia es independiente del mismo miembro en otra instancia de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-187">An instance member in one instance is independent of the same member in another instance of the same class.</span></span> <span data-ttu-id="d3647-188">Por ejemplo, una variable de miembro de instancia puede tener valores diferentes en instancias distintas.</span><span class="sxs-lookup"><span data-stu-id="d3647-188">An instance member variable, for example, can have different values in different instances.</span></span>

<span data-ttu-id="d3647-189">Los miembros declarados con la palabra clave `Shared` son *miembros compartidos*, que pertenecen a la clase como un todo y no a una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="d3647-189">Members declared with the `Shared` keyword are *shared members*, which belong to the class as a whole and not to any particular instance.</span></span> <span data-ttu-id="d3647-190">Un miembro compartido existe solo una vez, independientemente del número de instancias de su clase, o incluso si no crea ninguna.</span><span class="sxs-lookup"><span data-stu-id="d3647-190">A shared member exists only once, no matter how many instances of its class you create, or even if you create no instances.</span></span> <span data-ttu-id="d3647-191">Una variable de miembro compartido, por ejemplo, tiene un único valor, que está disponible para todo el código que puede tener acceso a la clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-191">A shared member variable, for example, has only one value, which is available to all code that can access the class.</span></span>

#### <a name="accessing-non-shared-members"></a><span data-ttu-id="d3647-192">Obtener acceso a miembros no compartidos</span><span class="sxs-lookup"><span data-stu-id="d3647-192">Accessing non-shared members</span></span>

1. <span data-ttu-id="d3647-193">Asegúrese de que el objeto se crea a partir de su clase y de que se asigna a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-193">Make sure the object has been created from its class and assigned to an object variable.</span></span>

   ```vb
   Dim secondForm As New System.Windows.Forms.Form
   ```

2. <span data-ttu-id="d3647-194">En la instrucción que tiene acceso al miembro, siga el nombre de la variable de objeto con el *operador de acceso a miembro* ( `.` ) y, a continuación, el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="d3647-194">In the statement that accesses the member, follow the object variable name with the *member-access operator* (`.`) and then the member name.</span></span>

   ```vb
   secondForm.Show()
   ```

#### <a name="accessing-shared-members"></a><span data-ttu-id="d3647-195">Acceso a miembros compartidos</span><span class="sxs-lookup"><span data-stu-id="d3647-195">Accessing shared members</span></span>

- <span data-ttu-id="d3647-196">Siga el nombre de clase con el *operador de acceso a miembros* ( `.` ) y, a continuación, el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="d3647-196">Follow the class name with the *member-access operator* (`.`) and then the member name.</span></span> <span data-ttu-id="d3647-197">Siempre debe acceder a un miembro `Shared` del objeto directamente a través del nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-197">You should always access a `Shared` member of the object directly through the class name.</span></span>

   ```vb
   Console.WriteLine("This computer is called " & Environment.MachineName)
   ```

- <span data-ttu-id="d3647-198">Si ya ha creado un objeto de la clase, también puede acceder a un miembro `Shared` a través de la variable del objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-198">If you have already created an object from the class, you can alternatively access a `Shared` member through the object's variable.</span></span>

### <a name="differences-between-classes-and-modules"></a><span data-ttu-id="d3647-199">Diferencias entre clases y módulos</span><span class="sxs-lookup"><span data-stu-id="d3647-199">Differences between classes and modules</span></span>

<span data-ttu-id="d3647-200">La diferencia principal entre clases y módulos es que pueden crearse instancias de clases como objetos, pero no de los módulos estándar.</span><span class="sxs-lookup"><span data-stu-id="d3647-200">The main difference between classes and modules is that classes can be instantiated as objects while standard modules cannot.</span></span> <span data-ttu-id="d3647-201">Como solo hay una copia de los datos de un módulo estándar, cuando una parte del programa cambia una variable pública en un módulo estándar, cualquier otra parte del programa obtiene el mismo valor si lee luego esa variable.</span><span class="sxs-lookup"><span data-stu-id="d3647-201">Because there is only one copy of a standard module's data, when one part of your program changes a public variable in a standard module, any other part of the program gets the same value if it then reads that variable.</span></span> <span data-ttu-id="d3647-202">En cambio, los datos de objeto existen por separado para cada objeto con instancias.</span><span class="sxs-lookup"><span data-stu-id="d3647-202">In contrast, object data exists separately for each instantiated object.</span></span> <span data-ttu-id="d3647-203">Otra diferencia es que, a diferencia de los módulos estándar, las clases pueden implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="d3647-203">Another difference is that unlike standard modules, classes can implement interfaces.</span></span> <span data-ttu-id="d3647-204">Si una clase está marcada con el modificador [MustInherit](../../../language-reference/modifiers/mustinherit.md) , no se pueden crear instancias de ella directamente.</span><span class="sxs-lookup"><span data-stu-id="d3647-204">If a class is marked with the [MustInherit](../../../language-reference/modifiers/mustinherit.md) modifier, it can't be instantiated directly.</span></span> <span data-ttu-id="d3647-205">Sin embargo, todavía es diferente de un módulo, ya que se puede heredar, mientras que los módulos no se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="d3647-205">However, it's still different from a module as it can be inherited while modules can't be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="d3647-206">Cuando el modificador `Shared` se aplica a un miembro de clase, se asocia a la propia clase, en lugar de a una instancia particular de una clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-206">When the `Shared` modifier is applied to a class member, it is associated with the class itself instead of a particular instance of the class.</span></span> <span data-ttu-id="d3647-207">Al miembro se accede directamente con el nombre de clase, de la misma forma que se accede a los miembros del módulo.</span><span class="sxs-lookup"><span data-stu-id="d3647-207">The member is accessed directly by using the class name, the same way module members are accessed.</span></span>

<span data-ttu-id="d3647-208">Las clases y los módulos también emplean ámbitos diferentes para sus miembros.</span><span class="sxs-lookup"><span data-stu-id="d3647-208">Classes and modules also use different scopes for their members.</span></span> <span data-ttu-id="d3647-209">Los miembros definidos dentro de una clase tienen el ámbito de una instancia específica de la clase y solo durante la vigencia del objeto.</span><span class="sxs-lookup"><span data-stu-id="d3647-209">Members defined within a class are scoped within a specific instance of the class and exist only for the lifetime of the object.</span></span> <span data-ttu-id="d3647-210">Para acceder a miembros de clase desde fuera de una clase, debe utilizar nombres completos con el formato de *Objeto*.*Miembro*.</span><span class="sxs-lookup"><span data-stu-id="d3647-210">To access class members from outside a class, you must use fully qualified names in the format of *Object*.*Member*.</span></span>

<span data-ttu-id="d3647-211">Por otro lado, los miembros declarados dentro de un módulo son de acceso público de forma predeterminada a través de cualquier código que pueda tener acceso al módulo.</span><span class="sxs-lookup"><span data-stu-id="d3647-211">On the other hand, members declared within a module are publicly accessible by default, and can be accessed by any code that can access the module.</span></span> <span data-ttu-id="d3647-212">Esto significa que las variables de un módulo estándar son variables globales porque son visibles desde cualquier parte del proyecto y, además, existen durante la vigencia del programa.</span><span class="sxs-lookup"><span data-stu-id="d3647-212">This means that variables in a standard module are effectively global variables because they are visible from anywhere in your project, and they exist for the life of the program.</span></span>

## <a name="reusing-classes-and-objects"></a><span data-ttu-id="d3647-213">Reutilización de clases y objetos</span><span class="sxs-lookup"><span data-stu-id="d3647-213">Reusing classes and objects</span></span>

<span data-ttu-id="d3647-214">Los objetos permiten declarar variables y procedimientos una vez, para luego reutilizarlos siempre que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d3647-214">Objects let you declare variables and procedures once and then reuse them whenever needed.</span></span> <span data-ttu-id="d3647-215">Por ejemplo, si desea agregar un corrector ortográfico a una aplicación, podría definir todas las variables y funciones compatibles para proporcionar la funcionalidad de revisión ortográfica.</span><span class="sxs-lookup"><span data-stu-id="d3647-215">For example, if you want to add a spelling checker to an application you could define all the variables and support functions to provide spell-checking functionality.</span></span> <span data-ttu-id="d3647-216">Si crea el corrector ortográfico como una clase, puede reutilizarlo en otras aplicaciones mediante la incorporación de una referencia al ensamblado compilado.</span><span class="sxs-lookup"><span data-stu-id="d3647-216">If you create your spelling checker as a class, you can then reuse it in other applications by adding a reference to the compiled assembly.</span></span> <span data-ttu-id="d3647-217">Mejor aún, puede ahorrarse trabajo mediante el uso de una clase de corrector ortográfico que otra persona ya ha desarrollado.</span><span class="sxs-lookup"><span data-stu-id="d3647-217">Better yet, you may be able to save yourself some work by using a spelling checker class that someone else has already developed.</span></span>

<span data-ttu-id="d3647-218">.NET proporciona muchos ejemplos de componentes que están disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="d3647-218">.NET provides many examples of components that are available for use.</span></span> <span data-ttu-id="d3647-219">En el ejemplo siguiente se usa la clase <xref:System.TimeZone> en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="d3647-219">The following example uses the <xref:System.TimeZone> class in the <xref:System> namespace.</span></span> <span data-ttu-id="d3647-220"><xref:System.TimeZone> proporciona miembros que permiten recuperar información sobre la zona horaria del equipo actual.</span><span class="sxs-lookup"><span data-stu-id="d3647-220"><xref:System.TimeZone> provides members that allow you to retrieve information about the time zone of the current computer system.</span></span>

```vb
Public Sub ExamineTimeZone()
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone
    Dim s As String = "Current time zone is "
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "
    s &= "different from UTC (coordinated universal time)"
    s &= vbCrLf & "and is currently "
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "
    s &= "on ""summer time""."
    Console.WriteLine(s)
End Sub
```

<span data-ttu-id="d3647-221">En el ejemplo anterior, la primera [instrucción Dim](../../../language-reference/statements/dim-statement.md) declara una variable de objeto del tipo <xref:System.TimeZone> y le asigna un objeto <xref:System.TimeZone> que devuelve la propiedad <xref:System.TimeZone.CurrentTimeZone%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3647-221">In the preceding example, the first [Dim Statement](../../../language-reference/statements/dim-statement.md) declares an object variable of type <xref:System.TimeZone> and assigns to it a <xref:System.TimeZone> object returned by the <xref:System.TimeZone.CurrentTimeZone%2A> property.</span></span>

## <a name="relationships-among-objects"></a><span data-ttu-id="d3647-222">Relaciones entre objetos</span><span class="sxs-lookup"><span data-stu-id="d3647-222">Relationships among objects</span></span>

<span data-ttu-id="d3647-223">Los objetos pueden relacionarse entre sí de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="d3647-223">Objects can be related to each other in several ways.</span></span> <span data-ttu-id="d3647-224">Los tipos principales de relación son *jerárquica* y de *contención*.</span><span class="sxs-lookup"><span data-stu-id="d3647-224">The principal kinds of relationship are *hierarchical* and *containment*.</span></span>

### <a name="hierarchical-relationship"></a><span data-ttu-id="d3647-225">Relación jerárquica</span><span class="sxs-lookup"><span data-stu-id="d3647-225">Hierarchical relationship</span></span>

<span data-ttu-id="d3647-226">Cuando las clases se derivan de clases más fundamentales, se dice que tienen una *relación jerárquica*.</span><span class="sxs-lookup"><span data-stu-id="d3647-226">When classes are derived from more fundamental classes, they are said to have a *hierarchical relationship*.</span></span> <span data-ttu-id="d3647-227">Las jerarquías de clases son útiles cuando se describen elementos que constituyen un subtipo de una clase más general.</span><span class="sxs-lookup"><span data-stu-id="d3647-227">Class hierarchies are useful when describing items that are a subtype of a more general class.</span></span>

<span data-ttu-id="d3647-228">En el ejemplo siguiente, suponga que quiere definir un tipo especial de <xref:System.Windows.Forms.Button> que actúa como un <xref:System.Windows.Forms.Button> normal, pero también expone un método que invierte los colores de primer plano y de fondo.</span><span class="sxs-lookup"><span data-stu-id="d3647-228">In the following example, suppose you want to define a special kind of <xref:System.Windows.Forms.Button> that acts like a normal <xref:System.Windows.Forms.Button> but also exposes a method that reverses the foreground and background colors.</span></span>

#### <a name="define-a-class-that-is-derived-from-an-already-existing-class"></a><span data-ttu-id="d3647-229">Definir una clase que se deriva de una clase ya existente</span><span class="sxs-lookup"><span data-stu-id="d3647-229">Define a class that is derived from an already existing class</span></span>

1. <span data-ttu-id="d3647-230">Use una [instrucción Class](../../../language-reference/statements/class-statement.md) para definir una clase desde la que crear el objeto que necesita.</span><span class="sxs-lookup"><span data-stu-id="d3647-230">Use a [Class Statement](../../../language-reference/statements/class-statement.md) to define a class from which to create the object you need.</span></span>

   ```vb
   Public Class ReversibleButton
   ```

   <span data-ttu-id="d3647-231">Asegúrese de que una instrucción `End Class` sigue a la última línea de código de la clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-231">Be sure an `End Class` statement follows the last line of code in your class.</span></span> <span data-ttu-id="d3647-232">De forma predeterminada, el entorno de desarrollo integrado (IDE) genera automáticamente `End Class` al escribir una instrucción `Class`.</span><span class="sxs-lookup"><span data-stu-id="d3647-232">By default, the integrated development environment (IDE) automatically generates an `End Class` when you enter a `Class` statement.</span></span>

2. <span data-ttu-id="d3647-233">Siga a la instrucción `Class` inmediatamente con una [instrucción Inherits](../../../language-reference/statements/inherits-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-233">Follow the `Class` statement immediately with an [Inherits Statement](../../../language-reference/statements/inherits-statement.md).</span></span> <span data-ttu-id="d3647-234">Especifique la clase de la que deriva la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-234">Specify the class from which your new class derives.</span></span>

   ```vb
   Inherits System.Windows.Forms.Button
   ```

   <span data-ttu-id="d3647-235">La nueva clase hereda todos los miembros definidos por la clase base.</span><span class="sxs-lookup"><span data-stu-id="d3647-235">Your new class inherits all the members defined by the base class.</span></span>

3. <span data-ttu-id="d3647-236">Agregue el código para los miembros adicionales que la clase derivada expone.</span><span class="sxs-lookup"><span data-stu-id="d3647-236">Add the code for the additional members your derived class exposes.</span></span> <span data-ttu-id="d3647-237">Por ejemplo, puede agregar un método `ReverseColors` y la clase derivada podría tener el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3647-237">For example, you might add a `ReverseColors` method, and your derived class might look as follows:</span></span>

   ```vb
   Public Class ReversibleButton
       Inherits System.Windows.Forms.Button
           Public Sub ReverseColors()
               Dim saveColor As System.Drawing.Color = Me.BackColor
               Me.BackColor = Me.ForeColor
               Me.ForeColor = saveColor
          End Sub
   End Class
   ```

   <span data-ttu-id="d3647-238">Si crea un objeto a partir de la `ReversibleButton` clase, puede tener acceso a todos los miembros de la <xref:System.Windows.Forms.Button> clase, así como al método y a todos los `ReverseColors` miembros nuevos que defina en `ReversibleButton` .</span><span class="sxs-lookup"><span data-stu-id="d3647-238">If you create an object from the `ReversibleButton` class, it can access all the members of the <xref:System.Windows.Forms.Button> class, as well as the `ReverseColors` method and any other new members you define in `ReversibleButton`.</span></span>

<span data-ttu-id="d3647-239">Las clases derivadas heredan miembros de la clase en que se basan, lo que permite agregar complejidad a medida que progresa en una jerarquía de clases.</span><span class="sxs-lookup"><span data-stu-id="d3647-239">Derived classes inherit members from the class they are based on, allowing you to add complexity as you progress in a class hierarchy.</span></span> <span data-ttu-id="d3647-240">Para más información, vea [Fundamentos de la herencia](inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-240">For more information, see [Inheritance Basics](inheritance-basics.md).</span></span>

### <a name="compile-the-code"></a><span data-ttu-id="d3647-241">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d3647-241">Compile the code</span></span>

<span data-ttu-id="d3647-242">Asegúrese de que el compilador puede tener acceso a la clase de la que pretende derivar la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-242">Be sure the compiler can access the class from which you intend to derive your new class.</span></span> <span data-ttu-id="d3647-243">Esto puede conllevar su nombre completo, como en el ejemplo anterior, o la identificación de su espacio de nombres en una [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="d3647-243">This might mean fully qualifying its name, as in the preceding example, or identifying its namespace in an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="d3647-244">Si la clase está en un proyecto diferente, tendrá que agregar una referencia a ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="d3647-244">If the class is in a different project, you might need to add a reference to that project.</span></span> <span data-ttu-id="d3647-245">Para más información, vea [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project).</span><span class="sxs-lookup"><span data-stu-id="d3647-245">For more information, see [Managing references in a project](/visualstudio/ide/managing-references-in-a-project).</span></span>

### <a name="containment-relationship"></a><span data-ttu-id="d3647-246">Relaciones de contención</span><span class="sxs-lookup"><span data-stu-id="d3647-246">Containment relationship</span></span>

<span data-ttu-id="d3647-247">Otra forma de relacionar ese objeto es mediante una *relación de contención*.</span><span class="sxs-lookup"><span data-stu-id="d3647-247">Another way that objects can be related is a *containment relationship*.</span></span> <span data-ttu-id="d3647-248">Los objetos contenedores lógicamente encapsulan otros objetos.</span><span class="sxs-lookup"><span data-stu-id="d3647-248">Container objects logically encapsulate other objects.</span></span> <span data-ttu-id="d3647-249">Por ejemplo, el objeto <xref:System.OperatingSystem> contiene lógicamente un objeto <xref:System.Version>, el cual devuelve a través de su propiedad <xref:System.OperatingSystem.Version%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3647-249">For example, the <xref:System.OperatingSystem> object logically contains a <xref:System.Version> object, which it returns through its <xref:System.OperatingSystem.Version%2A> property.</span></span> <span data-ttu-id="d3647-250">Tenga en cuenta que el objeto contenedor no contiene ningún otro objeto físicamente.</span><span class="sxs-lookup"><span data-stu-id="d3647-250">Note that the container object does not physically contain any other object.</span></span>

#### <a name="collections"></a><span data-ttu-id="d3647-251">Colecciones</span><span class="sxs-lookup"><span data-stu-id="d3647-251">Collections</span></span>

<span data-ttu-id="d3647-252">Un tipo concreto de contención de objeto se representa mediante *colecciones*.</span><span class="sxs-lookup"><span data-stu-id="d3647-252">One particular type of object containment is represented by *collections*.</span></span> <span data-ttu-id="d3647-253">Las colecciones son grupos de objetos similares que se pueden enumerar.</span><span class="sxs-lookup"><span data-stu-id="d3647-253">Collections are groups of similar objects that can be enumerated.</span></span> <span data-ttu-id="d3647-254">Visual Basic admite una sintaxis específica en la [... Instrucción siguiente](../../../language-reference/statements/for-each-next-statement.md) que permite recorrer en iteración los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="d3647-254">Visual Basic supports a specific syntax in the [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md) that allows you to iterate through the items of a collection.</span></span> <span data-ttu-id="d3647-255">Además, las colecciones suelen permitir usar un <xref:Microsoft.VisualBasic.Collection.Item%2A> para recuperar elementos en función de su índice o asociándolos con una cadena única.</span><span class="sxs-lookup"><span data-stu-id="d3647-255">Additionally, collections often allow you to use an <xref:Microsoft.VisualBasic.Collection.Item%2A> to retrieve elements by their index or by associating them with a unique string.</span></span> <span data-ttu-id="d3647-256">Las colecciones pueden ser más fáciles de utilizar que las matrices puesto que permiten agregar o quitar elementos sin utilizar índices.</span><span class="sxs-lookup"><span data-stu-id="d3647-256">Collections can be easier to use than arrays because they allow you to add or remove items without using indexes.</span></span> <span data-ttu-id="d3647-257">Debido a su facilidad de uso, las colecciones se utilizan a menudo para almacenar formularios y controles.</span><span class="sxs-lookup"><span data-stu-id="d3647-257">Because of their ease of use, collections are often used to store forms and controls.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3647-258">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d3647-258">Related topics</span></span>

<span data-ttu-id="d3647-259">[Tutorial: definir clases](walkthrough-defining-classes.md)</span><span class="sxs-lookup"><span data-stu-id="d3647-259">[Walkthrough: Defining Classes](walkthrough-defining-classes.md)</span></span>\
<span data-ttu-id="d3647-260">Proporciona una descripción detallada sobre cómo crear una clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-260">Provides a step-by-step description of how to create a class.</span></span>

<span data-ttu-id="d3647-261">[Propiedades y métodos sobrecargados](overloaded-properties-and-methods.md)</span><span class="sxs-lookup"><span data-stu-id="d3647-261">[Overloaded Properties and Methods](overloaded-properties-and-methods.md)</span></span>\
<span data-ttu-id="d3647-262">Propiedades y métodos sobrecargados</span><span class="sxs-lookup"><span data-stu-id="d3647-262">Overloaded Properties and Methods</span></span>

<span data-ttu-id="d3647-263">[Fundamentos de la herencia](inheritance-basics.md)</span><span class="sxs-lookup"><span data-stu-id="d3647-263">[Inheritance Basics](inheritance-basics.md)</span></span>\
<span data-ttu-id="d3647-264">Se tratan los modificadores de herencia, con la sustitución de métodos y propiedades, MyClass y MyBase.</span><span class="sxs-lookup"><span data-stu-id="d3647-264">Covers inheritance modifiers, overriding methods and properties, MyClass, and MyBase.</span></span>

<span data-ttu-id="d3647-265">[Duración de los objetos: cómo se crean y destruyen](object-lifetime-how-objects-are-created-and-destroyed.md)</span><span class="sxs-lookup"><span data-stu-id="d3647-265">[Object Lifetime: How Objects Are Created and Destroyed](object-lifetime-how-objects-are-created-and-destroyed.md)</span></span>\
<span data-ttu-id="d3647-266">Describe cómo crear y eliminar instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="d3647-266">Discusses creating and disposing of class instances.</span></span>

<span data-ttu-id="d3647-267">[Tipos anónimos](anonymous-types.md)</span><span class="sxs-lookup"><span data-stu-id="d3647-267">[Anonymous Types](anonymous-types.md)</span></span>\
<span data-ttu-id="d3647-268">Describe cómo crear y usar tipos anónimos que permiten crear objetos sin escribir una definición de clase para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d3647-268">Describes how to create and use anonymous types, which allow you to create objects without writing a class definition for the data type.</span></span>

<span data-ttu-id="d3647-269">[Inicializadores de objeto: tipos con nombre y anónimos](object-initializers-named-and-anonymous-types.md)</span><span class="sxs-lookup"><span data-stu-id="d3647-269">[Object Initializers: Named and Anonymous Types](object-initializers-named-and-anonymous-types.md)</span></span>\
<span data-ttu-id="d3647-270">Explica los inicializadores de objeto, que se usan para crear instancias de tipos con nombre y anónimos mediante una sola expresión.</span><span class="sxs-lookup"><span data-stu-id="d3647-270">Discusses object initializers, which are used to create instances of named and anonymous types by using a single expression.</span></span>

<span data-ttu-id="d3647-271">[Cómo: deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span><span class="sxs-lookup"><span data-stu-id="d3647-271">[How to: Infer Property Names and Types in Anonymous Type Declarations](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span></span>\
<span data-ttu-id="d3647-272">Explica cómo deducir tipos y nombres de propiedades en declaraciones de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="d3647-272">Explains how to infer property names and types in anonymous type declarations.</span></span> <span data-ttu-id="d3647-273">Proporciona ejemplos de inferencia correcta e incorrecta.</span><span class="sxs-lookup"><span data-stu-id="d3647-273">Provides examples of successful and unsuccessful inference.</span></span>
