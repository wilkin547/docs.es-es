---
title: 'Tutorial: Crear un control compuesto con Visual C#'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ad9aad026a1a6a1266845736d7651db77fd5d5c
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546729"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="24b7b-102">Tutorial: Crear un control compuesto con C\#</span><span class="sxs-lookup"><span data-stu-id="24b7b-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="24b7b-103">Los controles compuestos proporcionan una forma de crear y reutilizar interfaces gráficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="24b7b-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="24b7b-104">Un control compuesto es esencialmente un componente con una representación visual.</span><span class="sxs-lookup"><span data-stu-id="24b7b-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="24b7b-105">Como tal, puede constar de uno o varios controles de Windows Forms, componentes o bloques de código que pueden extender funcionalidad al validar la entrada del usuario, modificar propiedades de presentación o realizar otras tareas requeridas por el autor.</span><span class="sxs-lookup"><span data-stu-id="24b7b-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="24b7b-106">Los controles compuestos se pueden colocar en Windows Forms de la misma manera que otros controles.</span><span class="sxs-lookup"><span data-stu-id="24b7b-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="24b7b-107">En la primera parte de este tutorial, creará un control compuesto simple denominado `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="24b7b-108">En la segunda parte, extenderá la funcionalidad de `ctlClock` mediante herencia.</span><span class="sxs-lookup"><span data-stu-id="24b7b-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="24b7b-109">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="24b7b-109">Create the Project</span></span>

<span data-ttu-id="24b7b-110">Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y asegúrese de que el componente predeterminado estará en el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="24b7b-111">Para crear la biblioteca de controles ctlClockLib y el control ctlClock</span><span class="sxs-lookup"><span data-stu-id="24b7b-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="24b7b-112">En Visual Studio, cree un nuevo proyecto de biblioteca de controles de **formularios Windows Forms** y asímócelo **ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="24b7b-113">El nombre del proyecto, `ctlClockLib`, también se asigna de forma predeterminada al espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="24b7b-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="24b7b-114">El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="24b7b-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="24b7b-115">Por ejemplo, si dos ensamblados proporcionan componentes denominados `ctlClock`, puede especificar su componente `ctlClock` mediante `ctlClockLib.ctlClock.`</span><span class="sxs-lookup"><span data-stu-id="24b7b-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="24b7b-116">En **el Explorador**de soluciones , haga clic con el botón secundario en **UserControl1.cs**y, a continuación, haga clic en Cambiar **nombre**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="24b7b-117">Cambie el nombre del archivo a `ctlClock.cs`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="24b7b-118">Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="24b7b-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="24b7b-119">De forma predeterminada, un control <xref:System.Windows.Forms.UserControl> compuesto hereda de la clase proporcionada por el sistema.</span><span class="sxs-lookup"><span data-stu-id="24b7b-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="24b7b-120">La <xref:System.Windows.Forms.UserControl> clase proporciona funcionalidad requerida por todos los controles compuestos e implementa propiedades y métodos estándar.</span><span class="sxs-lookup"><span data-stu-id="24b7b-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="24b7b-121">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="24b7b-122">Agregar controles y componentes de Windows al control compuesto</span><span class="sxs-lookup"><span data-stu-id="24b7b-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="24b7b-123">Una interfaz visual es una parte esencial de su control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="24b7b-124">Esta interfaz visual se implementa agregando uno o más controles de Windows a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="24b7b-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="24b7b-125">En la demostración siguiente, incorporará controles de Windows al control compuesto y escribirá código para implementar funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="24b7b-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="24b7b-126">Para agregar una etiqueta y un temporizador al control compuesto</span><span class="sxs-lookup"><span data-stu-id="24b7b-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="24b7b-127">En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClock.cs**y, a continuación, haga clic en Diseñador **de vistas**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="24b7b-128">En el cuadro de **herramientas**, expanda el nodo **Controles comunes** y, a continuación, haga doble clic en **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="24b7b-129">Se <xref:System.Windows.Forms.Label> agrega `label1` un control denominado al control en la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="24b7b-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="24b7b-130">En el diseñador, haga clic en **label1**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-130">In the designer, click **label1**.</span></span> <span data-ttu-id="24b7b-131">En la ventana Propiedades, establezca las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="24b7b-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="24b7b-132">Propiedad</span><span class="sxs-lookup"><span data-stu-id="24b7b-132">Property</span></span>|<span data-ttu-id="24b7b-133">Cambiar a</span><span class="sxs-lookup"><span data-stu-id="24b7b-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="24b7b-134">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="24b7b-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="24b7b-135">**Texto**</span><span class="sxs-lookup"><span data-stu-id="24b7b-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="24b7b-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="24b7b-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="24b7b-137">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="24b7b-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="24b7b-138">En el **cuadro de herramientas**, expanda el nodo **Componentes** y haga doble clic en **Temporizador**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="24b7b-139">Dado <xref:System.Windows.Forms.Timer> que a es un componente, no tiene ninguna representación visual en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="24b7b-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="24b7b-140">Por lo tanto, no aparece con los controles en la superficie del diseñador, sino en el Diseñador de **componentes** (una bandeja en la parte inferior de la superficie del diseñador).</span><span class="sxs-lookup"><span data-stu-id="24b7b-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="24b7b-141">En el **Diseñador de componentes**, <xref:System.Windows.Forms.Timer.Interval%2A> haga `1000` clic <xref:System.Windows.Forms.Timer.Enabled%2A> en `true` **timer1**y, a continuación, establezca la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="24b7b-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="24b7b-142">La <xref:System.Windows.Forms.Timer.Interval%2A> propiedad controla la <xref:System.Windows.Forms.Timer> frecuencia con la que el componente marca.</span><span class="sxs-lookup"><span data-stu-id="24b7b-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="24b7b-143">Cada vez que `timer1` hace tic, se ejecuta el código en el evento `timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="24b7b-144">El intervalo representa el número de milisegundos entre tics.</span><span class="sxs-lookup"><span data-stu-id="24b7b-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="24b7b-145">En el **Diseñador de componentes**, haga doble `ctlClock`clic en **timer1** para ir al `timer1_Tick` evento para .</span><span class="sxs-lookup"><span data-stu-id="24b7b-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="24b7b-146">Modifique el código para que se parezca al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="24b7b-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="24b7b-147">Asegúrese de cambiar el modificador de acceso de `private` a `protected`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="24b7b-148">Este código hará que la hora actual se muestre en `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="24b7b-149">Como el intervalo de `timer1` se estableció en `1000`, este evento se producirá cada mil milisegundos, lo que actualiza la hora actual cada segundo.</span><span class="sxs-lookup"><span data-stu-id="24b7b-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="24b7b-150">Modifique el método para que se pueda reemplazar con la palabra clave `virtual`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="24b7b-151">Para más información, consulte la sección "Heredar de un control compuesto".</span><span class="sxs-lookup"><span data-stu-id="24b7b-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="24b7b-152">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="24b7b-153">Agregar propiedades al control compuesto</span><span class="sxs-lookup"><span data-stu-id="24b7b-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="24b7b-154">El control de reloj <xref:System.Windows.Forms.Label> ahora <xref:System.Windows.Forms.Timer> encapsula un control y un componente, cada uno con su propio conjunto de propiedades inherentes.</span><span class="sxs-lookup"><span data-stu-id="24b7b-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="24b7b-155">Aunque las propiedades individuales de estos controles no resultarán accesibles a los usuarios posteriores del control, puede crear y exponer propiedades personalizadas escribiendo los bloques de código adecuados.</span><span class="sxs-lookup"><span data-stu-id="24b7b-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="24b7b-156">En el siguiente procedimiento, agregará al control propiedades que permiten al usuario cambiar el color de fondo y del texto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="24b7b-157">Para agregar una propiedad al control compuesto</span><span class="sxs-lookup"><span data-stu-id="24b7b-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="24b7b-158">En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClock.cs**y, a continuación, haga clic en Ver **código**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="24b7b-159">Se abre el **Editor de código** del control.</span><span class="sxs-lookup"><span data-stu-id="24b7b-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="24b7b-160">Busque la instrucción `public partial class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="24b7b-161">Bajo la llave de apertura (`{)`, escriba el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="24b7b-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="24b7b-162">Estas instrucciones crean las variables privadas que usará para almacenar los valores de las propiedades que va a crear.</span><span class="sxs-lookup"><span data-stu-id="24b7b-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="24b7b-163">Escriba o pegue el siguiente código debajo de las declaraciones de variables del paso 2.</span><span class="sxs-lookup"><span data-stu-id="24b7b-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="24b7b-164">El código anterior crea dos propiedades personalizadas, `ClockForeColor` y `ClockBackColor`, que estarán disponibles para posteriores usuarios de este control.</span><span class="sxs-lookup"><span data-stu-id="24b7b-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="24b7b-165">Las instrucciones `get` y `set` permiten almacenar y recuperar el valor de propiedad, además de proporcionar código para implementar funcionalidad adecuada para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="24b7b-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="24b7b-166">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="24b7b-167">Probar el control</span><span class="sxs-lookup"><span data-stu-id="24b7b-167">Test the Control</span></span>

<span data-ttu-id="24b7b-168">Los controles no son aplicaciones independientes; deben hospedarse en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="24b7b-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="24b7b-169">Pruebe el comportamiento en tiempo de ejecución del control y sus propiedades con **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="24b7b-170">Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="24b7b-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="24b7b-171">Para probar el control</span><span class="sxs-lookup"><span data-stu-id="24b7b-171">To test your control</span></span>

1. <span data-ttu-id="24b7b-172">Presione **F5** para compilar el proyecto y ejecutar el control en el contenedor de **pruebas UserControl**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="24b7b-173">En la cuadrícula de propiedades del contenedor de prueba, busque la propiedad `ClockBackColor` y selecciónela para mostrar la paleta de colores.</span><span class="sxs-lookup"><span data-stu-id="24b7b-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="24b7b-174">Haga clic en un color para elegirlo.</span><span class="sxs-lookup"><span data-stu-id="24b7b-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="24b7b-175">El color de fondo del control cambia al color seleccionado.</span><span class="sxs-lookup"><span data-stu-id="24b7b-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="24b7b-176">Use una secuencia similar de eventos para comprobar que la propiedad `ClockForeColor` funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="24b7b-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="24b7b-177">En esta sección y en las anteriores, ha visto cómo se pueden combinar componentes y controles de Windows con código y empaquetado para ofrecer funcionalidad personalizada en forma de control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="24b7b-178">Ha aprendido a exponer propiedades en el control compuesto y a probar el control una vez completado.</span><span class="sxs-lookup"><span data-stu-id="24b7b-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="24b7b-179">En la siguiente sección, aprenderá a crear un control compuesto heredado utilizando `ctlClock` como base.</span><span class="sxs-lookup"><span data-stu-id="24b7b-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="24b7b-180">Heredar de un control compuesto</span><span class="sxs-lookup"><span data-stu-id="24b7b-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="24b7b-181">En las secciones anteriores, ha aprendido a combinar controles de Windows, componentes y código en controles compuestos reutilizables.</span><span class="sxs-lookup"><span data-stu-id="24b7b-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="24b7b-182">Ahora puede utilizar su control compuesto como base sobre la que crear otros controles.</span><span class="sxs-lookup"><span data-stu-id="24b7b-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="24b7b-183">El proceso de derivar una clase a partir de una clase base se denomina *herencia*.</span><span class="sxs-lookup"><span data-stu-id="24b7b-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="24b7b-184">En esta sección, creará un control de usuario denominado `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="24b7b-185">Este control se derivará de su control primario, `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="24b7b-186">Aprenderá a extender la funcionalidad de `ctlClock` reemplazando los métodos primarios y agregando nuevos métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="24b7b-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="24b7b-187">El primer paso para crear un control heredado es derivarlo de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="24b7b-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="24b7b-188">Esta acción crea un control que tiene todas las propiedades, los métodos y las características gráficas del control primario, pero que también puede servir de base para agregar funcionalidad nueva o modificada.</span><span class="sxs-lookup"><span data-stu-id="24b7b-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="24b7b-189">Para crear el control heredado</span><span class="sxs-lookup"><span data-stu-id="24b7b-189">To create the inherited control</span></span>

1. <span data-ttu-id="24b7b-190">En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClockLib**, seleccione **Agregar**y, a continuación, haga clic en Control **de usuario**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="24b7b-191">Se abre el cuadro de diálogo **Agregar nuevo elemento** .</span><span class="sxs-lookup"><span data-stu-id="24b7b-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="24b7b-192">Seleccione la plantilla **Control de usuario heredado**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="24b7b-193">En el cuadro **Nombre**, escriba `ctlAlarmClock.cs` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="24b7b-194">Aparece el cuadro de diálogo **Selector de herencia**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="24b7b-195">En **Nombre de componente**, haga doble clic en **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="24b7b-196">En el Explorador de **soluciones**, examine los proyectos actuales.</span><span class="sxs-lookup"><span data-stu-id="24b7b-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24b7b-197">Se ha agregado un archivo denominado **ctlAlarmClock.cs** al proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="24b7b-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="24b7b-198">Añadir las propiedades de alarma</span><span class="sxs-lookup"><span data-stu-id="24b7b-198">Add the Alarm Properties</span></span>

<span data-ttu-id="24b7b-199">Las propiedades se agregan a un control heredado de la misma forma que si fuera un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="24b7b-200">Ahora utilizará la sintaxis de declaración de propiedades para agregar dos propiedades al control: `AlarmTime`, que almacenará el valor de la fecha y la hora en que debe activarse la alarma, y `AlarmSet`, que indicará si la alarma está definida.</span><span class="sxs-lookup"><span data-stu-id="24b7b-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="24b7b-201">Para agregar propiedades al control compuesto</span><span class="sxs-lookup"><span data-stu-id="24b7b-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="24b7b-202">En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlAlarmClock**y, a continuación, haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="24b7b-203">Busque la instrucción `public class`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-203">Locate the `public class` statement.</span></span> <span data-ttu-id="24b7b-204">Tenga en cuenta que el control hereda de `ctlClockLib.ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="24b7b-205">Bajo la instrucción con la llave de apertura (`{)`, escriba el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="24b7b-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="24b7b-206">Añadir a la interfaz gráfica del control</span><span class="sxs-lookup"><span data-stu-id="24b7b-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="24b7b-207">El control heredado tiene una interfaz visual que es idéntica a la del control del que hereda.</span><span class="sxs-lookup"><span data-stu-id="24b7b-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="24b7b-208">Posee los mismos controles constituyentes que su control primario, pero las propiedades de estos no estarán disponibles a menos que se expusieran específicamente.</span><span class="sxs-lookup"><span data-stu-id="24b7b-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="24b7b-209">Puede agregar a la interfaz gráfica de un control compuesto heredado del mismo modo que agregaría a cualquier control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="24b7b-210">Para seguir agregando a la interfaz visual de su reloj despertador, agregará un control de etiqueta que parpadeará cuando suene la alarma.</span><span class="sxs-lookup"><span data-stu-id="24b7b-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="24b7b-211">Para agregar el control de etiqueta</span><span class="sxs-lookup"><span data-stu-id="24b7b-211">To add the label control</span></span>

1. <span data-ttu-id="24b7b-212">En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlAlarmClock**y, a continuación, haga clic en Diseñador de **vistas**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="24b7b-213">Se abre el diseñador para `ctlAlarmClock` en la ventana principal.</span><span class="sxs-lookup"><span data-stu-id="24b7b-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="24b7b-214">Haga clic en la parte de presentación del control y observe la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="24b7b-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24b7b-215">Aunque se muestran todas las propiedades, están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="24b7b-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="24b7b-216">Esto indica que estas propiedades son nativas de `lblDisplay` y no se pueden modificar ni se puede acceder a ellas en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="24b7b-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="24b7b-217">De forma predeterminada, los controles contenidos en un control compuesto son `private`, y sus propiedades no son accesibles por ningún medio.</span><span class="sxs-lookup"><span data-stu-id="24b7b-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24b7b-218">Si desea que los posteriores usuarios de su control compuesto tengan acceso a sus controles internos, declárelos como `public` o `protected`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="24b7b-219">Esto le permitirá establecer y modificar las propiedades de los controles contenidos en el control compuesto mediante el código adecuado.</span><span class="sxs-lookup"><span data-stu-id="24b7b-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="24b7b-220">Agregue <xref:System.Windows.Forms.Label> un control al control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="24b7b-221">Con el ratón, <xref:System.Windows.Forms.Label> arrastre el control inmediatamente debajo del cuadro de visualización.</span><span class="sxs-lookup"><span data-stu-id="24b7b-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="24b7b-222">En la ventana Propiedades, establezca las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="24b7b-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="24b7b-223">Propiedad</span><span class="sxs-lookup"><span data-stu-id="24b7b-223">Property</span></span>|<span data-ttu-id="24b7b-224">Configuración</span><span class="sxs-lookup"><span data-stu-id="24b7b-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="24b7b-225">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="24b7b-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="24b7b-226">**Texto**</span><span class="sxs-lookup"><span data-stu-id="24b7b-226">**Text**</span></span>|<span data-ttu-id="24b7b-227">**¡Alarma!**</span><span class="sxs-lookup"><span data-stu-id="24b7b-227">**Alarm!**</span></span>|
    |<span data-ttu-id="24b7b-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="24b7b-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="24b7b-229">**Visible**</span><span class="sxs-lookup"><span data-stu-id="24b7b-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="24b7b-230">Añadir la funcionalidad de alarma</span><span class="sxs-lookup"><span data-stu-id="24b7b-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="24b7b-231">En los procedimientos anteriores, agregó propiedades y un control que habilitará la funcionalidad de alarma en el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="24b7b-232">En este procedimiento, agregará código para comparar la hora actual con la hora de la alarma y, si son iguales, hacer que parpadee una alarma.</span><span class="sxs-lookup"><span data-stu-id="24b7b-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="24b7b-233">Al reemplazar el método `timer1_Tick` de `ctlClock` y agregarle código adicional, extenderá la funcionalidad de `ctlAlarmClock` al mismo tiempo que conserva toda la funcionalidad inherente de `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="24b7b-234">Para reemplazar el método timer1_Tick de ctlClock</span><span class="sxs-lookup"><span data-stu-id="24b7b-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="24b7b-235">En el **Editor de código**, busque la instrucción `private bool blnAlarmSet;`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="24b7b-236">Justo debajo de ella, agregue la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="24b7b-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="24b7b-237">En el **Editor de código**, busque la llave de cierre (`})` al final de la clase.</span><span class="sxs-lookup"><span data-stu-id="24b7b-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="24b7b-238">Justo antes de la llave, agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="24b7b-238">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="24b7b-239">Con la adición de este código, se llevan a cabo varias tareas.</span><span class="sxs-lookup"><span data-stu-id="24b7b-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="24b7b-240">La instrucción `override` indica al control que utilice este método en lugar del que heredó del control base.</span><span class="sxs-lookup"><span data-stu-id="24b7b-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="24b7b-241">Cuando se llama a este método, llama al método que reemplaza invocando la instrucción `base.timer1_Tick`, lo que garantiza que toda la funcionalidad incorporada en el control original se reproduzca en este control.</span><span class="sxs-lookup"><span data-stu-id="24b7b-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="24b7b-242">A continuación, ejecuta código adicional para incorporar la funcionalidad de alarma.</span><span class="sxs-lookup"><span data-stu-id="24b7b-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="24b7b-243">Aparecerá un control de etiqueta parpadeante cuando se active la alarma.</span><span class="sxs-lookup"><span data-stu-id="24b7b-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="24b7b-244">El control de reloj despertador está casi completado.</span><span class="sxs-lookup"><span data-stu-id="24b7b-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="24b7b-245">Lo único que queda es implementar una forma de desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="24b7b-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="24b7b-246">Para ello, agregará código al método `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="24b7b-247">Para implementar el método de apagado</span><span class="sxs-lookup"><span data-stu-id="24b7b-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="24b7b-248">En el Explorador de **soluciones**, haga clic **con el**botón secundario en ctlAlarmClock.cs y, a continuación, haga clic en Diseñador **de vistas**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="24b7b-249">Se abre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="24b7b-249">The designer opens.</span></span>

2. <span data-ttu-id="24b7b-250">Agregue un botón al control.</span><span class="sxs-lookup"><span data-stu-id="24b7b-250">Add a button to the control.</span></span> <span data-ttu-id="24b7b-251">Establezca las propiedades del botón de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="24b7b-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="24b7b-252">Propiedad</span><span class="sxs-lookup"><span data-stu-id="24b7b-252">Property</span></span>|<span data-ttu-id="24b7b-253">Value</span><span class="sxs-lookup"><span data-stu-id="24b7b-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="24b7b-254">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="24b7b-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="24b7b-255">**Texto**</span><span class="sxs-lookup"><span data-stu-id="24b7b-255">**Text**</span></span>|<span data-ttu-id="24b7b-256">**Deshabilitar alarma**</span><span class="sxs-lookup"><span data-stu-id="24b7b-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="24b7b-257">En el diseñador, haga doble clic en **btnAlarmOff**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="24b7b-258">Se abre el **Editor de código** en la línea `private void btnAlarmOff_Click`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="24b7b-259">Modifique este método para que se parezca al siguiente código.</span><span class="sxs-lookup"><span data-stu-id="24b7b-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="24b7b-260">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="24b7b-261">Use el Control Heredado en un Formulario</span><span class="sxs-lookup"><span data-stu-id="24b7b-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="24b7b-262">Puede probar el control heredado de la misma manera `ctlClock`que probó el control de clase base: presione **F5** para compilar el proyecto y ejecutar el control en el contenedor de **pruebas UserControl**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="24b7b-263">Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="24b7b-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="24b7b-264">Para utilizar el control, debe hospedarlo en un formulario.</span><span class="sxs-lookup"><span data-stu-id="24b7b-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="24b7b-265">Al igual que con los controles compuestos estándar, los controles compuestos heredados no son independientes y deben hospedarse en un formulario o en otro contenedor.</span><span class="sxs-lookup"><span data-stu-id="24b7b-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="24b7b-266">Puesto que `ctlAlarmClock` tiene un mayor grado de funcionalidad, se necesita código adicional para probarlo.</span><span class="sxs-lookup"><span data-stu-id="24b7b-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="24b7b-267">En este procedimiento, escribirá un programa sencillo para probar la funcionalidad de `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="24b7b-268">Escribirá código para establecer y mostrar la propiedad `AlarmTime` de `ctlAlarmClock` y probar sus funciones inherentes.</span><span class="sxs-lookup"><span data-stu-id="24b7b-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="24b7b-269">Para compilar y agregar el control a un formulario de prueba</span><span class="sxs-lookup"><span data-stu-id="24b7b-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="24b7b-270">En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClockLib**y, a continuación, haga clic en **Generar**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="24b7b-271">Agregue un nuevo proyecto de aplicación de **windows Forms** a la solución y asíse como **Prueba**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-271">Add a new **Windows Forms Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="24b7b-272">En el Explorador de **soluciones**, haga clic con el botón secundario en el nodo **Referencias** del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="24b7b-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="24b7b-273">Haga clic en **Agregar referencia** para mostrar el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="24b7b-274">Haga clic en la pestaña etiquetada como **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="24b7b-275">El proyecto `ctlClockLib` aparecerá bajo **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="24b7b-276">Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="24b7b-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="24b7b-277">En **el Explorador**de soluciones , haga clic con el botón secundario en **Probar**y, a continuación, haga clic en **Generar**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="24b7b-278">En el **cuadro de herramientas**, expanda el nodo **Componentes de ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="24b7b-279">Haga doble clic en **ctlAlarmClock** para agregar una copia de `ctlAlarmClock` al formulario.</span><span class="sxs-lookup"><span data-stu-id="24b7b-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="24b7b-280">En el cuadro de **herramientas**, busque y <xref:System.Windows.Forms.DateTimePicker> haga doble clic en <xref:System.Windows.Forms.Label> **DateTimePicker** para agregar un control al formulario y, a continuación, agregue un control haciendo doble clic en **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="24b7b-281">Use el mouse para colocar los controles en un lugar adecuado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="24b7b-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="24b7b-282">Establezca las propiedades de estos controles de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="24b7b-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="24b7b-283">Control</span><span class="sxs-lookup"><span data-stu-id="24b7b-283">Control</span></span>|<span data-ttu-id="24b7b-284">Propiedad</span><span class="sxs-lookup"><span data-stu-id="24b7b-284">Property</span></span>|<span data-ttu-id="24b7b-285">Value</span><span class="sxs-lookup"><span data-stu-id="24b7b-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="24b7b-286">**Texto**</span><span class="sxs-lookup"><span data-stu-id="24b7b-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="24b7b-287">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="24b7b-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="24b7b-288">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="24b7b-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="24b7b-289">**Formato**</span><span class="sxs-lookup"><span data-stu-id="24b7b-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="24b7b-290">En el diseñador, haga doble clic en **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="24b7b-291">Se abre el **Editor de código** en `private void dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="24b7b-292">Modifique el código para que se parezca al siguiente.</span><span class="sxs-lookup"><span data-stu-id="24b7b-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="24b7b-293">En **el Explorador**de soluciones , haga clic con el botón secundario en **Probar**y, a continuación, haga clic en Establecer como proyecto **de inicio**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="24b7b-294">En el menú **Depurar** , haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="24b7b-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="24b7b-295">Se inicia el programa de prueba.</span><span class="sxs-lookup"><span data-stu-id="24b7b-295">The test program starts.</span></span> <span data-ttu-id="24b7b-296">Tenga en cuenta que la `ctlAlarmClock` hora actual se actualiza en <xref:System.Windows.Forms.DateTimePicker> el control y que la hora de inicio se muestra en el control.</span><span class="sxs-lookup"><span data-stu-id="24b7b-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="24b7b-297">Haga <xref:System.Windows.Forms.DateTimePicker> clic en el lugar donde se muestran los minutos de la hora.</span><span class="sxs-lookup"><span data-stu-id="24b7b-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="24b7b-298">Use el teclado para establecer el valor de los minutos en un minuto más tarde que la hora actual mostrada por `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="24b7b-299">La hora para la configuración de alarma se muestra en `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="24b7b-300">Espere a que la hora mostrada llegue a la hora de la configuración de alarma.</span><span class="sxs-lookup"><span data-stu-id="24b7b-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="24b7b-301">Cuando la hora que se muestra llegue a la hora en que está puesta la alarma, `lblAlarm` parpadeará.</span><span class="sxs-lookup"><span data-stu-id="24b7b-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="24b7b-302">Para desactivar la alarma, haga clic en `btnAlarmOff`.</span><span class="sxs-lookup"><span data-stu-id="24b7b-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="24b7b-303">Ahora puede restablecer la alarma.</span><span class="sxs-lookup"><span data-stu-id="24b7b-303">You may now reset the alarm.</span></span>

<span data-ttu-id="24b7b-304">Este artículo ha cubierto una serie de conceptos clave.</span><span class="sxs-lookup"><span data-stu-id="24b7b-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="24b7b-305">Ha aprendido a crear un control compuesto mediante la combinación de controles y componentes en un contenedor de control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24b7b-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="24b7b-306">Ha aprendido a agregar propiedades al control y a escribir código para implementar funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="24b7b-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="24b7b-307">En la última sección, ha aprendido a extender la funcionalidad de un control compuesto determinado mediante herencia y a modificar la funcionalidad de los métodos de host reemplazando estos últimos.</span><span class="sxs-lookup"><span data-stu-id="24b7b-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="24b7b-308">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24b7b-308">See also</span></span>

- [<span data-ttu-id="24b7b-309">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="24b7b-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="24b7b-310">Cómo: Mostrar un control en el cuadro de diálogo Seleccionar elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="24b7b-310">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="24b7b-311">Tutorial: Heredar de un control de formularios Windows Forms con Visual C#</span><span class="sxs-lookup"><span data-stu-id="24b7b-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
