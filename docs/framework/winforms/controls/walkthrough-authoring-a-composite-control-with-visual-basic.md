---
title: 'Tutorial: Crear un control compuesto con Visual Basic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: cb54ef372e6da551b95f1edf61e3844b9dcba4c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950043"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="dd819-102">Tutorial: Crear un control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd819-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="dd819-103">Los controles compuestos proporcionan una forma de crear y reutilizar interfaces gráficas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="dd819-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="dd819-104">Un control compuesto es esencialmente un componente con una representación visual.</span><span class="sxs-lookup"><span data-stu-id="dd819-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="dd819-105">Como tal, puede constar de uno o varios controles de Windows Forms, componentes o bloques de código que pueden extender funcionalidad al validar la entrada del usuario, modificar propiedades de presentación o realizar otras tareas requeridas por el autor.</span><span class="sxs-lookup"><span data-stu-id="dd819-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="dd819-106">Los controles compuestos se pueden colocar en Windows Forms de la misma manera que otros controles.</span><span class="sxs-lookup"><span data-stu-id="dd819-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="dd819-107">En la primera parte de este tutorial, creará un control compuesto simple denominado `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="dd819-108">En la segunda parte, extenderá la funcionalidad de `ctlClock` mediante herencia.</span><span class="sxs-lookup"><span data-stu-id="dd819-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="dd819-109">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="dd819-109">Creating the Project</span></span>
 <span data-ttu-id="dd819-110">Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y asegúrese de que el componente predeterminado estará en el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="dd819-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="dd819-111">Para crear la biblioteca de controles ctlClockLib y el control ctlClock</span><span class="sxs-lookup"><span data-stu-id="dd819-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="dd819-112">En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="dd819-112">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="dd819-113">En la lista de proyectos de Visual Basic, seleccione la plantilla de proyecto Biblioteca de controles `ctlClockLib` de **Windows** , escriba en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dd819-113">From the list of Visual Basic projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>

     <span data-ttu-id="dd819-114">El nombre del proyecto, `ctlClockLib` también se asigna de forma predeterminada al espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="dd819-114">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="dd819-115">El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dd819-115">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="dd819-116">Por ejemplo, si dos ensamblados proporcionan componentes denominados `ctlClock`, puede especificar su componente `ctlClock` mediante `ctlClockLib.ctlClock.`</span><span class="sxs-lookup"><span data-stu-id="dd819-116">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

3. <span data-ttu-id="dd819-117">En el Explorador de soluciones, haga clic con el botón derecho en **UserControl1.vb** y haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="dd819-117">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="dd819-118">Cambie el nombre del archivo a `ctlClock.vb`.</span><span class="sxs-lookup"><span data-stu-id="dd819-118">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="dd819-119">Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="dd819-119">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd819-120">De forma predeterminada, un control compuesto hereda de la <xref:System.Windows.Forms.UserControl> clase proporcionada por el sistema.</span><span class="sxs-lookup"><span data-stu-id="dd819-120">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="dd819-121">La <xref:System.Windows.Forms.UserControl> clase proporciona la funcionalidad requerida por todos los controles compuestos e implementa métodos y propiedades estándar.</span><span class="sxs-lookup"><span data-stu-id="dd819-121">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

4. <span data-ttu-id="dd819-122">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd819-122">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="dd819-123">Agregar componentes y controles de Windows al control compuesto</span><span class="sxs-lookup"><span data-stu-id="dd819-123">Adding Windows Controls and Components to the Composite Control</span></span>
 <span data-ttu-id="dd819-124">Una interfaz visual es una parte esencial de su control compuesto.</span><span class="sxs-lookup"><span data-stu-id="dd819-124">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="dd819-125">Esta interfaz visual se implementa agregando uno o más controles de Windows a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="dd819-125">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="dd819-126">En la demostración siguiente, incorporará controles de Windows al control compuesto y escribirá código para implementar funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="dd819-126">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="dd819-127">Para agregar una etiqueta y un temporizador al control compuesto</span><span class="sxs-lookup"><span data-stu-id="dd819-127">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="dd819-128">En el Explorador de soluciones, haga clic con el botón derecho en **ctlClock.vb** y haga clic en **Ver diseñador**.</span><span class="sxs-lookup"><span data-stu-id="dd819-128">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="dd819-129">En el cuadro de herramientas, expanda el nodo **Controles comunes** y haga doble clic en **Label**.</span><span class="sxs-lookup"><span data-stu-id="dd819-129">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="dd819-130">Un <xref:System.Windows.Forms.Label> control denominado `Label1` se agrega al control en la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="dd819-130">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="dd819-131">En el diseñador, haga clic en **label1**.</span><span class="sxs-lookup"><span data-stu-id="dd819-131">In the designer, click **Label1**.</span></span> <span data-ttu-id="dd819-132">En la ventana Propiedades, establezca las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="dd819-132">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="dd819-133">Property</span><span class="sxs-lookup"><span data-stu-id="dd819-133">Property</span></span>|<span data-ttu-id="dd819-134">Cambiar a</span><span class="sxs-lookup"><span data-stu-id="dd819-134">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="dd819-135">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dd819-135">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="dd819-136">**Texto**</span><span class="sxs-lookup"><span data-stu-id="dd819-136">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="dd819-137">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="dd819-137">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="dd819-138">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="dd819-138">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="dd819-139">En el **cuadro de herramientas**, expanda el nodo **Componentes** y haga doble clic en **Temporizador**.</span><span class="sxs-lookup"><span data-stu-id="dd819-139">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="dd819-140">Dado que <xref:System.Windows.Forms.Timer> es un componente de, no tiene ninguna representación visual en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd819-140">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="dd819-141">Por lo tanto, no aparece con los controles en la superficie del diseñador, sino en el Diseñador de componentes (una bandeja en la parte inferior de la superficie del diseñador).</span><span class="sxs-lookup"><span data-stu-id="dd819-141">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="dd819-142">En el diseñador de componentes, haga clic en **Timer1**y, <xref:System.Windows.Forms.Timer.Interval%2A> a continuación `1000` , establezca <xref:System.Windows.Forms.Timer.Enabled%2A> la propiedad `True`en y la propiedad en.</span><span class="sxs-lookup"><span data-stu-id="dd819-142">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>

     <span data-ttu-id="dd819-143">La <xref:System.Windows.Forms.Timer.Interval%2A> propiedad controla la frecuencia con la que se marca el componente de temporizador.</span><span class="sxs-lookup"><span data-stu-id="dd819-143">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="dd819-144">Cada vez que `Timer1` hace tic, se ejecuta el código en el evento `Timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="dd819-144">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="dd819-145">El intervalo representa el número de milisegundos entre tics.</span><span class="sxs-lookup"><span data-stu-id="dd819-145">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="dd819-146">En el Diseñador de componentes, haga doble clic en **Timer1** para ir al evento `Timer1_Tick` de `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-146">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="dd819-147">Modifique el código para que se parezca al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dd819-147">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="dd819-148">Asegúrese de cambiar el modificador de acceso de `Private` a `Protected`.</span><span class="sxs-lookup"><span data-stu-id="dd819-148">Be sure to change the access modifier from `Private` to `Protected`.</span></span>

    ```vb
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles Timer1.Tick
        ' Causes the label to display the current time.
        lblDisplay.Text = Format(Now, "hh:mm:ss")
    End Sub
    ```

     <span data-ttu-id="dd819-149">Este código hará que la hora actual se muestre en `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="dd819-149">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="dd819-150">Como el intervalo de `Timer1` se estableció en `1000`, este evento se producirá cada mil milisegundos, lo que actualiza la hora actual cada segundo.</span><span class="sxs-lookup"><span data-stu-id="dd819-150">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="dd819-151">Modifique el método para que se pueda invalidar.</span><span class="sxs-lookup"><span data-stu-id="dd819-151">Modify the method to be overridable.</span></span> <span data-ttu-id="dd819-152">Para más información, consulte la sección "Heredar de un control de usuario", más adelante.</span><span class="sxs-lookup"><span data-stu-id="dd819-152">For more information, see the "Inheriting from a User Control" section below.</span></span>

    ```vb
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _
        e As System.EventArgs) Handles Timer1.Tick
    ```

9. <span data-ttu-id="dd819-153">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd819-153">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="dd819-154">Agregar propiedades al control compuesto</span><span class="sxs-lookup"><span data-stu-id="dd819-154">Adding Properties to the Composite Control</span></span>
 <span data-ttu-id="dd819-155">El control de reloj encapsula ahora un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.Timer> componente, cada uno con su propio conjunto de propiedades inherentes.</span><span class="sxs-lookup"><span data-stu-id="dd819-155">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="dd819-156">Aunque las propiedades individuales de estos controles no resultarán accesibles a los usuarios posteriores del control, puede crear y exponer propiedades personalizadas escribiendo los bloques de código adecuados.</span><span class="sxs-lookup"><span data-stu-id="dd819-156">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="dd819-157">En el siguiente procedimiento, agregará al control propiedades que permiten al usuario cambiar el color de fondo y del texto.</span><span class="sxs-lookup"><span data-stu-id="dd819-157">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="dd819-158">Para agregar una propiedad al control compuesto</span><span class="sxs-lookup"><span data-stu-id="dd819-158">To add a property to your composite control</span></span>

1. <span data-ttu-id="dd819-159">En el Explorador de soluciones, haga clic con el botón derecho en **ctlClock.vb** y haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="dd819-159">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>

     <span data-ttu-id="dd819-160">Se abre el Editor de código del control.</span><span class="sxs-lookup"><span data-stu-id="dd819-160">The Code Editor for your control opens.</span></span>

2. <span data-ttu-id="dd819-161">Busque la instrucción `Public Class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-161">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="dd819-162">Debajo de ella, escriba el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="dd819-162">Beneath it, type the following code.</span></span>

    ```vb
    Private colFColor as Color
    Private colBColor as Color
    ```

     <span data-ttu-id="dd819-163">Estas instrucciones crean las variables privadas que usará para almacenar los valores de las propiedades que va a crear.</span><span class="sxs-lookup"><span data-stu-id="dd819-163">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="dd819-164">Inserte el código siguiente debajo de las declaraciones de variable del paso 2.</span><span class="sxs-lookup"><span data-stu-id="dd819-164">Insert the following code beneath the variable declarations from step 2.</span></span>

    ```vb
    ' Declares the name and type of the property.
    Property ClockBackColor() as Color
        ' Retrieves the value of the private variable colBColor.
        Get
            Return colBColor
        End Get
        ' Stores the selected value in the private variable colBColor, and
        ' updates the background color of the label control lblDisplay.
        Set(ByVal value as Color)
            colBColor = value
            lblDisplay.BackColor = colBColor
        End Set

    End Property
    ' Provides a similar set of instructions for the foreground color.
    Property ClockForeColor() as Color
        Get
            Return colFColor
        End Get
        Set(ByVal value as Color)
            colFColor = value
            lblDisplay.ForeColor = colFColor
        End Set
    End Property
    ```

     <span data-ttu-id="dd819-165">El código anterior crea dos propiedades personalizadas, `ClockForeColor` y `ClockBackColor`, que estarán disponibles para que posteriores usuarios de este control las invoquen mediante la instrucción `Property`.</span><span class="sxs-lookup"><span data-stu-id="dd819-165">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="dd819-166">Las instrucciones `Get` y `Set` permiten almacenar y recuperar el valor de propiedad, además de proporcionar código para implementar funcionalidad adecuada para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="dd819-166">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="dd819-167">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd819-167">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="testing-the-control"></a><span data-ttu-id="dd819-168">Probar el control</span><span class="sxs-lookup"><span data-stu-id="dd819-168">Testing the Control</span></span>
 <span data-ttu-id="dd819-169">Los controles no son proyectos independientes; deben hospedarse en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="dd819-169">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="dd819-170">Pruebe el comportamiento en tiempo de ejecución del control y sus propiedades con **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="dd819-170">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="dd819-171">Para obtener más información, vea [Cómo: Pruebe el comportamiento en tiempo de ejecución de un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)control UserControl.</span><span class="sxs-lookup"><span data-stu-id="dd819-171">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="dd819-172">Para probar el control</span><span class="sxs-lookup"><span data-stu-id="dd819-172">To test your control</span></span>

1. <span data-ttu-id="dd819-173">Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="dd819-173">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="dd819-174">En la cuadrícula de propiedades del contenedor de prueba, seleccione la propiedad `ClockBackColor` y haga clic en la flecha desplegable para mostrar la paleta de colores.</span><span class="sxs-lookup"><span data-stu-id="dd819-174">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>

3. <span data-ttu-id="dd819-175">Haga clic en un color para elegirlo.</span><span class="sxs-lookup"><span data-stu-id="dd819-175">Choose a color by clicking it.</span></span>

     <span data-ttu-id="dd819-176">El color de fondo del control cambia al color seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dd819-176">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="dd819-177">Use una secuencia similar de eventos para comprobar que la propiedad `ClockForeColor` funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="dd819-177">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

5. <span data-ttu-id="dd819-178">Haga clic en **Cerrar** para cerrar **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="dd819-178">Click **Close** to close the **UserControl Test Container**.</span></span>

     <span data-ttu-id="dd819-179">En esta sección y en las anteriores, ha visto cómo se pueden combinar componentes y controles de Windows con código y empaquetado para ofrecer funcionalidad personalizada en forma de control compuesto.</span><span class="sxs-lookup"><span data-stu-id="dd819-179">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="dd819-180">Ha aprendido a exponer propiedades en el control compuesto y a probar el control una vez completado.</span><span class="sxs-lookup"><span data-stu-id="dd819-180">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="dd819-181">En la siguiente sección, aprenderá a crear un control compuesto heredado utilizando `ctlClock` como base.</span><span class="sxs-lookup"><span data-stu-id="dd819-181">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="dd819-182">Heredar de un control compuesto</span><span class="sxs-lookup"><span data-stu-id="dd819-182">Inheriting from a Composite Control</span></span>
 <span data-ttu-id="dd819-183">En las secciones anteriores, ha aprendido a combinar controles de Windows, componentes y código en controles compuestos reutilizables.</span><span class="sxs-lookup"><span data-stu-id="dd819-183">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="dd819-184">Ahora puede utilizar su control compuesto como base sobre la que crear otros controles.</span><span class="sxs-lookup"><span data-stu-id="dd819-184">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="dd819-185">El proceso de derivar una clase a partir de una clase base se denomina *herencia*.</span><span class="sxs-lookup"><span data-stu-id="dd819-185">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="dd819-186">En esta sección, creará un control de usuario denominado `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-186">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="dd819-187">Este control se derivará de su control primario, `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-187">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="dd819-188">Aprenderá a extender la funcionalidad de `ctlClock` reemplazando los métodos primarios y agregando nuevos métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="dd819-188">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

 <span data-ttu-id="dd819-189">El primer paso para crear un control heredado es derivarlo de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="dd819-189">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="dd819-190">Esta acción crea un control que tiene todas las propiedades, los métodos y las características gráficas del control primario, pero que también puede servir de base para agregar funcionalidad nueva o modificada.</span><span class="sxs-lookup"><span data-stu-id="dd819-190">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="dd819-191">Para crear el control heredado</span><span class="sxs-lookup"><span data-stu-id="dd819-191">To create the inherited control</span></span>

1. <span data-ttu-id="dd819-192">En el Explorador de soluciones, haga clic con el botón derecho en **ctlClockLib**, elija **Agregar** y haga clic en **Control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="dd819-192">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="dd819-193">Se abre el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="dd819-193">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="dd819-194">Seleccione la plantilla **Control de usuario heredado**.</span><span class="sxs-lookup"><span data-stu-id="dd819-194">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="dd819-195">En el cuadro **Nombre**, escriba `ctlAlarmClock.vb` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="dd819-195">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>

     <span data-ttu-id="dd819-196">Aparece el cuadro de diálogo **Selector de herencia**.</span><span class="sxs-lookup"><span data-stu-id="dd819-196">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="dd819-197">En **Nombre de componente**, haga doble clic en **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="dd819-197">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="dd819-198">En el Explorador de soluciones, examine los proyectos actuales.</span><span class="sxs-lookup"><span data-stu-id="dd819-198">In Solution Explorer, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd819-199">Se ha agregado un archivo denominado **ctlAlarmClock.vb** al proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="dd819-199">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>

### <a name="adding-the-alarm-properties"></a><span data-ttu-id="dd819-200">Agregar las propiedades de alarma</span><span class="sxs-lookup"><span data-stu-id="dd819-200">Adding the Alarm Properties</span></span>
 <span data-ttu-id="dd819-201">Las propiedades se agregan a un control heredado de la misma forma que si fuera un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="dd819-201">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="dd819-202">Ahora utilizará la sintaxis de declaración de propiedades para agregar dos propiedades al control: `AlarmTime`, que almacenará el valor de la fecha y la hora en que debe activarse la alarma, y `AlarmSet`, que indicará si la alarma está definida.</span><span class="sxs-lookup"><span data-stu-id="dd819-202">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="dd819-203">Para agregar propiedades al control compuesto</span><span class="sxs-lookup"><span data-stu-id="dd819-203">To add properties to your composite control</span></span>

1. <span data-ttu-id="dd819-204">En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock** y haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="dd819-204">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="dd819-205">Busque la declaración de clase del control ctlAlarmClock, que aparece como `Public Class ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-205">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="dd819-206">Inserte el siguiente código en la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="dd819-206">In the class declaration, insert the following code.</span></span>

    ```vb
    Private dteAlarmTime As Date
    Private blnAlarmSet As Boolean
    ' These properties will be declared as Public to allow future
    ' developers to access them.
    Public Property AlarmTime() As Date
        Get
            Return dteAlarmTime
        End Get
        Set(ByVal value as Date)
            dteAlarmTime = value
        End Set
    End Property
    Public Property AlarmSet() As Boolean
        Get
            Return blnAlarmSet
        End Get
        Set(ByVal value as Boolean)
            blnAlarmSet = value
        End Set
    End Property
    ```

### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="dd819-207">Agregar a la interfaz gráfica del control</span><span class="sxs-lookup"><span data-stu-id="dd819-207">Adding to the Graphical Interface of the Control</span></span>
 <span data-ttu-id="dd819-208">El control heredado tiene una interfaz visual que es idéntica a la del control del que hereda.</span><span class="sxs-lookup"><span data-stu-id="dd819-208">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="dd819-209">Posee los mismos controles constituyentes que su control primario, pero las propiedades de estos no estarán disponibles a menos que se expusieran específicamente.</span><span class="sxs-lookup"><span data-stu-id="dd819-209">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="dd819-210">Puede agregar a la interfaz gráfica de un control compuesto heredado del mismo modo que agregaría a cualquier control compuesto.</span><span class="sxs-lookup"><span data-stu-id="dd819-210">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="dd819-211">Para seguir agregando a la interfaz visual de su reloj despertador, agregará un control de etiqueta que parpadeará cuando suene la alarma.</span><span class="sxs-lookup"><span data-stu-id="dd819-211">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="dd819-212">Para agregar el control de etiqueta</span><span class="sxs-lookup"><span data-stu-id="dd819-212">To add the label control</span></span>

1. <span data-ttu-id="dd819-213">En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock** y haga clic en **Ver diseñador**.</span><span class="sxs-lookup"><span data-stu-id="dd819-213">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>

     <span data-ttu-id="dd819-214">Se abre el diseñador para `ctlAlarmClock` en la ventana principal.</span><span class="sxs-lookup"><span data-stu-id="dd819-214">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="dd819-215">Haga clic en `lblDisplay` (la parte de visualización del control) y observe la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="dd819-215">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd819-216">Aunque se muestran todas las propiedades, están atenuadas.</span><span class="sxs-lookup"><span data-stu-id="dd819-216">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="dd819-217">Esto indica que estas propiedades son nativas de `lblDisplay` y no se pueden modificar ni se puede acceder a ellas en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="dd819-217">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="dd819-218">De forma predeterminada, los controles contenidos en un control compuesto son `Private`, y sus propiedades no son accesibles por ningún medio.</span><span class="sxs-lookup"><span data-stu-id="dd819-218">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd819-219">Si desea que los posteriores usuarios de su control compuesto tengan acceso a sus controles internos, declárelos como `Public` o `Protected`.</span><span class="sxs-lookup"><span data-stu-id="dd819-219">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="dd819-220">Esto le permitirá establecer y modificar las propiedades de los controles contenidos en el control compuesto mediante el código adecuado.</span><span class="sxs-lookup"><span data-stu-id="dd819-220">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="dd819-221">Agregue un <xref:System.Windows.Forms.Label> control al control compuesto.</span><span class="sxs-lookup"><span data-stu-id="dd819-221">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="dd819-222">Con el mouse, arrastre el <xref:System.Windows.Forms.Label> control inmediatamente debajo del cuadro de presentación.</span><span class="sxs-lookup"><span data-stu-id="dd819-222">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="dd819-223">En la ventana Propiedades, establezca las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="dd819-223">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="dd819-224">Property</span><span class="sxs-lookup"><span data-stu-id="dd819-224">Property</span></span>|<span data-ttu-id="dd819-225">Parámetro</span><span class="sxs-lookup"><span data-stu-id="dd819-225">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="dd819-226">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dd819-226">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="dd819-227">**Texto**</span><span class="sxs-lookup"><span data-stu-id="dd819-227">**Text**</span></span>|<span data-ttu-id="dd819-228">**¡Alarma!**</span><span class="sxs-lookup"><span data-stu-id="dd819-228">**Alarm!**</span></span>|
    |<span data-ttu-id="dd819-229">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="dd819-229">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="dd819-230">**Visible**</span><span class="sxs-lookup"><span data-stu-id="dd819-230">**Visible**</span></span>|`False`|

### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="dd819-231">Agregar la funcionalidad de alarma</span><span class="sxs-lookup"><span data-stu-id="dd819-231">Adding the Alarm Functionality</span></span>
 <span data-ttu-id="dd819-232">En los procedimientos anteriores, agregó propiedades y un control que habilitará la funcionalidad de alarma en el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="dd819-232">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="dd819-233">En este procedimiento, agregará código para comparar la hora actual con la hora de la alarma y, si son iguales, hacer que parpadee y suene una alarma.</span><span class="sxs-lookup"><span data-stu-id="dd819-233">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="dd819-234">Al reemplazar el método `Timer1_Tick` de `ctlClock` y agregarle código adicional, extenderá la funcionalidad de `ctlAlarmClock` al mismo tiempo que conserva toda la funcionalidad inherente de `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-234">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="dd819-235">Para reemplazar el método Timer1_Tick de ctlClock</span><span class="sxs-lookup"><span data-stu-id="dd819-235">To override the Timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="dd819-236">En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock.vb** y haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="dd819-236">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>

2. <span data-ttu-id="dd819-237">Busque la instrucción `Private blnAlarmSet As Boolean`.</span><span class="sxs-lookup"><span data-stu-id="dd819-237">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="dd819-238">Justo debajo de ella, agregue la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="dd819-238">Immediately beneath it, add the following statement.</span></span>

    ```vb
    Dim blnColorTicker as Boolean
    ```

3. <span data-ttu-id="dd819-239">Busque la instrucción `End Class` en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="dd819-239">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="dd819-240">Justo antes de la instrucción `End Class`, agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd819-240">Just before the `End Class` statement, add the following code.</span></span>

    ```vb
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _
        As System.EventArgs)
        ' Calls the Timer1_Tick method of ctlClock.
        MyBase.Timer1_Tick(sender, e)
        ' Checks to see if the Alarm is set.
        If AlarmSet = False Then
            Exit Sub
        End If
        ' If the date, hour, and minute of the alarm time are the same as
        ' now, flash and beep an alarm.
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _
            AlarmTime.Minute = Now.Minute Then
            ' Sounds an audible beep.
            Beep()
            ' Sets lblAlarmVisible to True, and changes the background color based on the
            ' value of blnColorTicker. The background color of the label will
            ' flash once per tick of the clock.
            lblAlarm.Visible = True
            If blnColorTicker = False Then
                lblAlarm.BackColor = Color.PeachPuff
                blnColorTicker = True
            Else
                lblAlarm.BackColor = Color.Plum
                blnColorTicker = False
            End If
        Else
            ' Once the alarm has sounded for a minute, the label is made
            ' invisible again.
            lblAlarm.Visible = False
        End If
    End Sub
    ```

     <span data-ttu-id="dd819-241">Con la adición de este código, se llevan a cabo varias tareas.</span><span class="sxs-lookup"><span data-stu-id="dd819-241">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="dd819-242">La instrucción `Overrides` indica al control que utilice este método en lugar del que heredó del control base.</span><span class="sxs-lookup"><span data-stu-id="dd819-242">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="dd819-243">Cuando se llama a este método, llama al método que reemplaza invocando la instrucción `MyBase.Timer1_Tick`, lo que garantiza que toda la funcionalidad incorporada en el control original se reproduzca en este control.</span><span class="sxs-lookup"><span data-stu-id="dd819-243">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="dd819-244">A continuación, ejecuta código adicional para incorporar la funcionalidad de alarma.</span><span class="sxs-lookup"><span data-stu-id="dd819-244">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="dd819-245">Aparecerá un control de etiqueta parpadeante cuando se active la alarma, y se oirá un pitido.</span><span class="sxs-lookup"><span data-stu-id="dd819-245">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd819-246">Dado que va a reemplazar un controlador de eventos heredado, no es necesario especificar el evento con la palabra clave `Handles`.</span><span class="sxs-lookup"><span data-stu-id="dd819-246">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="dd819-247">El evento ya está enlazado.</span><span class="sxs-lookup"><span data-stu-id="dd819-247">The event is already hooked up.</span></span> <span data-ttu-id="dd819-248">Lo que se va a reemplazar es la implementación del controlador.</span><span class="sxs-lookup"><span data-stu-id="dd819-248">All you are overriding is the implementation of the handler.</span></span>

     <span data-ttu-id="dd819-249">El control de reloj despertador está casi completado.</span><span class="sxs-lookup"><span data-stu-id="dd819-249">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="dd819-250">Lo único que queda es implementar una forma de desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="dd819-250">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="dd819-251">Para ello, agregará código al método `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="dd819-251">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="dd819-252">Para implementar el método de apagado</span><span class="sxs-lookup"><span data-stu-id="dd819-252">To implement the shutoff method</span></span>

1. <span data-ttu-id="dd819-253">En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock.vb** y haga clic en **Ver diseñador**.</span><span class="sxs-lookup"><span data-stu-id="dd819-253">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="dd819-254">En el diseñador, haga doble clic en **lblAlarm**.</span><span class="sxs-lookup"><span data-stu-id="dd819-254">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="dd819-255">Se abre el **Editor de código** en la línea `Private Sub lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="dd819-255">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>

3. <span data-ttu-id="dd819-256">Modifique este método para que se parezca al siguiente código.</span><span class="sxs-lookup"><span data-stu-id="dd819-256">Modify this method so that it resembles the following code.</span></span>

    ```vb
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _
     System.EventArgs) Handles lblAlarm.Click
        ' Turns off the alarm.
        AlarmSet = False
        ' Hides the flashing label.
        lblAlarm.Visible = False
    End Sub
    ```

4. <span data-ttu-id="dd819-257">En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd819-257">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="dd819-258">Usar el control heredado en un formulario</span><span class="sxs-lookup"><span data-stu-id="dd819-258">Using the Inherited Control on a Form</span></span>
 <span data-ttu-id="dd819-259">Puede probar el control heredado de la misma manera que probó el control de clase `ctlClock`base,: Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="dd819-259">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="dd819-260">Para obtener más información, vea [Cómo: Pruebe el comportamiento en tiempo de ejecución de un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)control UserControl.</span><span class="sxs-lookup"><span data-stu-id="dd819-260">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

 <span data-ttu-id="dd819-261">Para utilizar el control, debe hospedarlo en un formulario.</span><span class="sxs-lookup"><span data-stu-id="dd819-261">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="dd819-262">Al igual que con los controles compuestos estándar, los controles compuestos heredados no son independientes y deben hospedarse en un formulario o en otro contenedor.</span><span class="sxs-lookup"><span data-stu-id="dd819-262">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="dd819-263">Puesto que `ctlAlarmClock` tiene un mayor grado de funcionalidad, se necesita código adicional para probarlo.</span><span class="sxs-lookup"><span data-stu-id="dd819-263">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="dd819-264">En este procedimiento, escribirá un programa sencillo para probar la funcionalidad de `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-264">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="dd819-265">Escribirá código para establecer y mostrar la propiedad `AlarmTime` de `ctlAlarmClock` y probar sus funciones inherentes.</span><span class="sxs-lookup"><span data-stu-id="dd819-265">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="dd819-266">Para compilar y agregar el control a un formulario de prueba</span><span class="sxs-lookup"><span data-stu-id="dd819-266">To build and add your control to a test form</span></span>

1. <span data-ttu-id="dd819-267">En el Explorador de soluciones, haga clic con el botón derecho en **ctlClockLib** y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="dd819-267">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="dd819-268">En el menú **Archivo** , apunte a **Agregar**y haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="dd819-268">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>

3. <span data-ttu-id="dd819-269">Agregue un nuevo proyecto **Aplicación Windows** a la solución y asígnele el nombre `Test`.</span><span class="sxs-lookup"><span data-stu-id="dd819-269">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>

     <span data-ttu-id="dd819-270">Se crea el proyecto **Test** y se agrega al Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="dd819-270">The **Test** project is added to Solution Explorer.</span></span>

4. <span data-ttu-id="dd819-271">En el Explorador de soluciones, haga clic con el botón derecho en el nodo de proyecto `Test` y, después, haga clic en **Agregar referencia** para mostrar el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="dd819-271">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="dd819-272">Haga clic en la pestaña etiquetada como **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="dd819-272">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="dd819-273">El proyecto **ctlClockLib** aparecerá en **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="dd819-273">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="dd819-274">Haga doble clic en **ctlClockLib** para agregar la referencia al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="dd819-274">Double-click **ctlClockLib** to add the reference to the test project.</span></span>

6. <span data-ttu-id="dd819-275">En el Explorador de soluciones, haga clic con el botón derecho en **Probar** y haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="dd819-275">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>

7. <span data-ttu-id="dd819-276">En el **cuadro de herramientas**, expanda el nodo **Componentes de ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="dd819-276">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

8. <span data-ttu-id="dd819-277">Haga doble clic en **ctlAlarmClock** para agregar una instancia de `ctlAlarmClock` al formulario.</span><span class="sxs-lookup"><span data-stu-id="dd819-277">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>

9. <span data-ttu-id="dd819-278">En el **cuadro de herramientas**, busque y haga doble clic en DateTimePicker <xref:System.Windows.Forms.DateTimePicker> para agregar un control al formulario y, a <xref:System.Windows.Forms.Label> continuación, haga doble clic en **etiqueta**para agregar un control.</span><span class="sxs-lookup"><span data-stu-id="dd819-278">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

10. <span data-ttu-id="dd819-279">Use el mouse para colocar los controles en un lugar adecuado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="dd819-279">Use the mouse to position the controls in a convenient place on the form.</span></span>

11. <span data-ttu-id="dd819-280">Establezca las propiedades de estos controles de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd819-280">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="dd819-281">Control</span><span class="sxs-lookup"><span data-stu-id="dd819-281">Control</span></span>|<span data-ttu-id="dd819-282">Propiedad</span><span class="sxs-lookup"><span data-stu-id="dd819-282">Property</span></span>|<span data-ttu-id="dd819-283">Valor</span><span class="sxs-lookup"><span data-stu-id="dd819-283">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="dd819-284">**Texto**</span><span class="sxs-lookup"><span data-stu-id="dd819-284">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="dd819-285">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dd819-285">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="dd819-286">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dd819-286">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="dd819-287">**Format**</span><span class="sxs-lookup"><span data-stu-id="dd819-287">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

12. <span data-ttu-id="dd819-288">En el diseñador, haga doble clic en **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="dd819-288">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="dd819-289">Se abre el **Editor de código** en `Private Sub dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="dd819-289">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>

13. <span data-ttu-id="dd819-290">Modifique el código para que se parezca al siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd819-290">Modify the code so that it resembles the following.</span></span>

    ```vb
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles dtpTest.ValueChanged
        ctlAlarmClock1.AlarmTime = dtpTest.Value
        ctlAlarmClock1.AlarmSet = True
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _
            "hh:mm")
    End Sub
    ```

14. <span data-ttu-id="dd819-291">En el Explorador de soluciones, haga clic con el botón derecho en **Probar** y haga clic en **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="dd819-291">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

15. <span data-ttu-id="dd819-292">En el menú **Depurar**, haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="dd819-292">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="dd819-293">Se inicia el programa de prueba.</span><span class="sxs-lookup"><span data-stu-id="dd819-293">The test program starts.</span></span> <span data-ttu-id="dd819-294">Tenga en cuenta que la hora actual se actualiza `ctlAlarmClock` en el control y que la hora de inicio se muestra <xref:System.Windows.Forms.DateTimePicker> en el control.</span><span class="sxs-lookup"><span data-stu-id="dd819-294">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

16. <span data-ttu-id="dd819-295">Haga clic <xref:System.Windows.Forms.DateTimePicker> en el lugar en el que se muestran los minutos de la hora.</span><span class="sxs-lookup"><span data-stu-id="dd819-295">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

17. <span data-ttu-id="dd819-296">Use el teclado para establecer el valor de los minutos en un minuto más tarde que la hora actual mostrada por `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="dd819-296">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="dd819-297">La hora para la configuración de alarma se muestra en `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="dd819-297">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="dd819-298">Espere a que la hora mostrada llegue a la hora de la alarma configurada.</span><span class="sxs-lookup"><span data-stu-id="dd819-298">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="dd819-299">Cuando la hora que se muestra llegue a la hora en que está puesta la alarma, se oirá un pitido y `lblAlarm` parpadeará.</span><span class="sxs-lookup"><span data-stu-id="dd819-299">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>

18. <span data-ttu-id="dd819-300">Para desactivar la alarma, haga clic en `lblAlarm`.</span><span class="sxs-lookup"><span data-stu-id="dd819-300">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="dd819-301">Ahora puede restablecer la alarma.</span><span class="sxs-lookup"><span data-stu-id="dd819-301">You may now reset the alarm.</span></span>

     <span data-ttu-id="dd819-302">En este tutorial se han tratado varios conceptos clave.</span><span class="sxs-lookup"><span data-stu-id="dd819-302">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="dd819-303">Ha aprendido a crear un control compuesto mediante la combinación de controles y componentes en un contenedor de control compuesto.</span><span class="sxs-lookup"><span data-stu-id="dd819-303">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="dd819-304">Ha aprendido a agregar propiedades al control y a escribir código para implementar funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="dd819-304">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="dd819-305">En la última sección, ha aprendido a extender la funcionalidad de un control compuesto determinado mediante herencia y a modificar la funcionalidad de los métodos de host reemplazando estos últimos.</span><span class="sxs-lookup"><span data-stu-id="dd819-305">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd819-306">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd819-306">See also</span></span>

- [<span data-ttu-id="dd819-307">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="dd819-307">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="dd819-308">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="dd819-308">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="dd819-309">Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="dd819-309">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
