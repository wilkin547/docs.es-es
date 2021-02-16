---
description: 'Más información sobre: Tutorial: crear objetos COM con Visual Basic'
title: 'Tutorial: Creación de objetos COM'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 469466189e264253f3588a0a2735afe651bbd36f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427276"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="ac94e-103">Tutorial: Crear objetos COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac94e-103">Walkthrough: Creating COM Objects with Visual Basic</span></span>

<span data-ttu-id="ac94e-104">Al crear nuevas aplicaciones o componentes, es mejor crear ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac94e-104">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="ac94e-105">Sin embargo, Visual Basic también facilita la exposición de un componente de .NET Framework a COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-105">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="ac94e-106">Esto le permite proporcionar nuevos componentes para conjuntos de aplicaciones anteriores que requieren componentes COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-106">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="ac94e-107">En este tutorial se muestra cómo usar Visual Basic para exponer objetos .NET Framework como objetos COM, con y sin la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-107">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="ac94e-108">La forma más fácil de exponer objetos COM es usar la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-108">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="ac94e-109">Esta plantilla crea una nueva clase y, a continuación, configura el proyecto para generar la clase con una capa de interoperabilidad como un objeto COM y registrarla en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ac94e-109">This template creates a new class, then configures your project to generate the class with an interoperability layer as a COM object, and register it with the operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac94e-110">Aunque también puede exponer una clase creada en Visual Basic como un objeto COM para el uso de código no administrado, no es un objeto COM verdadero y Visual Basic no puede usar.</span><span class="sxs-lookup"><span data-stu-id="ac94e-110">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="ac94e-111">Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ac94e-111">For more information, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="ac94e-112">Para crear un objeto COM mediante la plantilla de clase COM</span><span class="sxs-lookup"><span data-stu-id="ac94e-112">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="ac94e-113">Abra un nuevo proyecto de aplicación de Windows desde el menú **archivo** haciendo clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-113">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="ac94e-114">En el cuadro de diálogo **nuevo proyecto** , en el campo **tipos de proyecto** , compruebe que está seleccionada la opción Windows.</span><span class="sxs-lookup"><span data-stu-id="ac94e-114">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="ac94e-115">Seleccione **biblioteca de clases** en la lista **plantillas** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-115">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="ac94e-116">Se muestra el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="ac94e-116">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="ac94e-117">Seleccione **Agregar nuevo elemento** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="ac94e-117">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="ac94e-118">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-118">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="ac94e-119">Seleccione **clase com** en la lista de **plantillas** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-119">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="ac94e-120">Visual Basic agrega una nueva clase y configura el nuevo proyecto para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-120">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="ac94e-121">Agregue código como propiedades, métodos y eventos a la clase COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-121">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="ac94e-122">Seleccione **compilar ClassLibrary1** en el menú **compilar** .</span><span class="sxs-lookup"><span data-stu-id="ac94e-122">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="ac94e-123">Visual Basic crea el ensamblado y registra el objeto COM con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ac94e-123">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="ac94e-124">Crear objetos COM sin la plantilla de clase COM</span><span class="sxs-lookup"><span data-stu-id="ac94e-124">Creating COM Objects without the COM Class Template</span></span>  

 <span data-ttu-id="ac94e-125">También puede crear una clase COM manualmente en lugar de usar la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-125">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="ac94e-126">Este procedimiento es útil cuando se trabaja desde la línea de comandos o cuando se desea tener más control sobre cómo se definen los objetos COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-126">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="ac94e-127">Para configurar el proyecto para generar un objeto COM</span><span class="sxs-lookup"><span data-stu-id="ac94e-127">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="ac94e-128">Abra un nuevo proyecto de aplicación de Windows desde el menú **archivo** haciendo clic en **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-128">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="ac94e-129">En el cuadro de diálogo **nuevo proyecto** , en el campo **tipos de proyecto** , compruebe que está seleccionada la opción Windows.</span><span class="sxs-lookup"><span data-stu-id="ac94e-129">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="ac94e-130">Seleccione **biblioteca de clases** en la lista **plantillas** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-130">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="ac94e-131">Se muestra el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="ac94e-131">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="ac94e-132">En el **Explorador de soluciones**, haga clic con el botón derecho del mouse en su proyecto y después seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-132">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="ac94e-133">Se muestra el **Diseñador de proyectos** .</span><span class="sxs-lookup"><span data-stu-id="ac94e-133">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="ac94e-134">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-134">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="ac94e-135">Active la casilla **registrar para interoperabilidad com** .</span><span class="sxs-lookup"><span data-stu-id="ac94e-135">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="ac94e-136">Para configurar el código de la clase para crear un objeto COM</span><span class="sxs-lookup"><span data-stu-id="ac94e-136">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="ac94e-137">En **Explorador de soluciones**, haga doble clic en **Class1. VB** para mostrar su código.</span><span class="sxs-lookup"><span data-stu-id="ac94e-137">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="ac94e-138">Cambie el nombre de la clase a `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="ac94e-138">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="ac94e-139">Agregue las siguientes constantes a `ComClass1` .</span><span class="sxs-lookup"><span data-stu-id="ac94e-139">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="ac94e-140">Almacenarán las constantes de identificador único global (GUID) que los objetos COM deben tener.</span><span class="sxs-lookup"><span data-stu-id="ac94e-140">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="ac94e-141">En el menú **Herramientas**, haga clic en **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-141">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="ac94e-142">En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-142">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="ac94e-143">Haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="ac94e-143">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="ac94e-144">Reemplace la cadena vacía del `ClassId` con el GUID y quite las llaves iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="ac94e-144">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="ac94e-145">Por ejemplo, si el GUID proporcionado por Guidgen es `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , el código debe aparecer de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="ac94e-145">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="ac94e-146">Repita los pasos anteriores para las `InterfaceId` `EventsId` constantes y, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ac94e-146">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > <span data-ttu-id="ac94e-147">Asegúrese de que los GUID son nuevos y únicos; de lo contrario, el componente COM podría estar en conflicto con otros componentes COM.</span><span class="sxs-lookup"><span data-stu-id="ac94e-147">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="ac94e-148">Agregue el `ComClass` atributo a `ComClass1` , especificando los GUID para el identificador de clase, el identificador de interfaz y el identificador de eventos, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ac94e-148">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="ac94e-149">Las clases COM deben tener un constructor sin parámetros `Public Sub New()` o la clase no se registrará correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac94e-149">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="ac94e-150">Agregue un constructor sin parámetros a la clase:</span><span class="sxs-lookup"><span data-stu-id="ac94e-150">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="ac94e-151">Agregue propiedades, métodos y eventos a la clase, y finalice con una `End Class` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ac94e-151">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="ac94e-152">Seleccione **compilar solución** en el menú **compilar** .</span><span class="sxs-lookup"><span data-stu-id="ac94e-152">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="ac94e-153">Visual Basic crea el ensamblado y registra el objeto COM con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ac94e-153">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ac94e-154">Los objetos COM generados con Visual Basic no pueden ser utilizados por otras aplicaciones Visual Basic porque no son objetos COM verdaderos.</span><span class="sxs-lookup"><span data-stu-id="ac94e-154">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="ac94e-155">Los intentos de agregar referencias a estos objetos COM producirán un error.</span><span class="sxs-lookup"><span data-stu-id="ac94e-155">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="ac94e-156">Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ac94e-156">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac94e-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac94e-157">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="ac94e-158">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="ac94e-158">COM Interop</span></span>](index.md)
- [<span data-ttu-id="ac94e-159">Tutorial: Implementación de la herencia mediante objetos COM</span><span class="sxs-lookup"><span data-stu-id="ac94e-159">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="ac94e-160">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="ac94e-160">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="ac94e-161">Interoperabilidad COM en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ac94e-161">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="ac94e-162">Solución de problemas de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="ac94e-162">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
