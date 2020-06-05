---
title: 'Tutorial: Creación de objetos COM'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: bb312317b2bbcb77bed9e3966db6d9fd5db79e4c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396745"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="0ac25-102">Tutorial: Crear objetos COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ac25-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="0ac25-103">Al crear nuevas aplicaciones o componentes, es mejor crear ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ac25-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="0ac25-104">Sin embargo, Visual Basic también facilita la exposición de un componente de .NET Framework a COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="0ac25-105">Esto le permite proporcionar nuevos componentes para conjuntos de aplicaciones anteriores que requieren componentes COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="0ac25-106">En este tutorial se muestra cómo usar Visual Basic para exponer objetos .NET Framework como objetos COM, con y sin la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-106">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="0ac25-107">La forma más fácil de exponer objetos COM es usar la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="0ac25-108">La plantilla de clase COM crea una nueva clase y, a continuación, configura el proyecto para generar la clase y el nivel de interoperabilidad como un objeto COM y registrarlo en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0ac25-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ac25-109">Aunque también puede exponer una clase creada en Visual Basic como un objeto COM para el uso de código no administrado, no es un objeto COM verdadero y Visual Basic no puede usar.</span><span class="sxs-lookup"><span data-stu-id="0ac25-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="0ac25-110">Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0ac25-110">For more information, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="0ac25-111">Para crear un objeto COM mediante la plantilla de clase COM</span><span class="sxs-lookup"><span data-stu-id="0ac25-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="0ac25-112">Abra un nuevo proyecto de aplicación de Windows desde el menú **archivo** haciendo clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="0ac25-113">En el cuadro de diálogo **nuevo proyecto** , en el campo **tipos de proyecto** , compruebe que está seleccionada la opción Windows.</span><span class="sxs-lookup"><span data-stu-id="0ac25-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="0ac25-114">Seleccione **biblioteca de clases** en la lista **plantillas** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="0ac25-115">Se muestra el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ac25-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="0ac25-116">Seleccione **Agregar nuevo elemento** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="0ac25-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="0ac25-117">Se mostrará el cuadro de diálogo **Agregar nuevo elemento** .</span><span class="sxs-lookup"><span data-stu-id="0ac25-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="0ac25-118">Seleccione **clase com** en la lista de **plantillas** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="0ac25-119">Visual Basic agrega una nueva clase y configura el nuevo proyecto para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="0ac25-120">Agregue código como propiedades, métodos y eventos a la clase COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="0ac25-121">Seleccione **compilar ClassLibrary1** en el menú **compilar** .</span><span class="sxs-lookup"><span data-stu-id="0ac25-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="0ac25-122">Visual Basic crea el ensamblado y registra el objeto COM con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0ac25-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="0ac25-123">Crear objetos COM sin la plantilla de clase COM</span><span class="sxs-lookup"><span data-stu-id="0ac25-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="0ac25-124">También puede crear una clase COM manualmente en lugar de usar la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="0ac25-125">Este procedimiento es útil cuando se trabaja desde la línea de comandos o cuando se desea tener más control sobre cómo se definen los objetos COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="0ac25-126">Para configurar el proyecto para generar un objeto COM</span><span class="sxs-lookup"><span data-stu-id="0ac25-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="0ac25-127">Abra un nuevo proyecto de aplicación de Windows desde el menú **archivo** haciendo clic en **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="0ac25-128">En el cuadro de diálogo **nuevo proyecto** , en el campo **tipos de proyecto** , compruebe que está seleccionada la opción Windows.</span><span class="sxs-lookup"><span data-stu-id="0ac25-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="0ac25-129">Seleccione **biblioteca de clases** en la lista **plantillas** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="0ac25-130">Se muestra el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ac25-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="0ac25-131">En el **Explorador de soluciones**, haga clic con el botón derecho del mouse en su proyecto y después seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="0ac25-132">Se muestra el **Diseñador de proyectos** .</span><span class="sxs-lookup"><span data-stu-id="0ac25-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="0ac25-133">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="0ac25-134">Active la casilla **registrar para interoperabilidad com** .</span><span class="sxs-lookup"><span data-stu-id="0ac25-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="0ac25-135">Para configurar el código de la clase para crear un objeto COM</span><span class="sxs-lookup"><span data-stu-id="0ac25-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="0ac25-136">En **Explorador de soluciones**, haga doble clic en **Class1. VB** para mostrar su código.</span><span class="sxs-lookup"><span data-stu-id="0ac25-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="0ac25-137">Cambie el nombre de la clase a `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="0ac25-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="0ac25-138">Agregue las siguientes constantes a `ComClass1` .</span><span class="sxs-lookup"><span data-stu-id="0ac25-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="0ac25-139">Almacenarán las constantes de identificador único global (GUID) que los objetos COM deben tener.</span><span class="sxs-lookup"><span data-stu-id="0ac25-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="0ac25-140">En el menú **Herramientas**, haga clic en **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="0ac25-141">En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="0ac25-142">Haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="0ac25-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="0ac25-143">Reemplace la cadena vacía del `ClassId` con el GUID y quite las llaves iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="0ac25-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="0ac25-144">Por ejemplo, si el GUID proporcionado por Guidgen es `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , el código debe aparecer de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="0ac25-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="0ac25-145">Repita los pasos anteriores para las `InterfaceId` `EventsId` constantes y, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0ac25-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > <span data-ttu-id="0ac25-146">Asegúrese de que los GUID son nuevos y únicos; de lo contrario, el componente COM podría estar en conflicto con otros componentes COM.</span><span class="sxs-lookup"><span data-stu-id="0ac25-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="0ac25-147">Agregue el `ComClass` atributo a `ComClass1` , especificando los GUID para el identificador de clase, el identificador de interfaz y el identificador de eventos, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ac25-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="0ac25-148">Las clases COM deben tener un constructor sin parámetros `Public Sub New()` o la clase no se registrará correctamente.</span><span class="sxs-lookup"><span data-stu-id="0ac25-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="0ac25-149">Agregue un constructor sin parámetros a la clase:</span><span class="sxs-lookup"><span data-stu-id="0ac25-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="0ac25-150">Agregue propiedades, métodos y eventos a la clase, y finalice con una `End Class` instrucción.</span><span class="sxs-lookup"><span data-stu-id="0ac25-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="0ac25-151">Seleccione **compilar solución** en el menú **compilar** .</span><span class="sxs-lookup"><span data-stu-id="0ac25-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="0ac25-152">Visual Basic crea el ensamblado y registra el objeto COM con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0ac25-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0ac25-153">Los objetos COM generados con Visual Basic no pueden ser utilizados por otras aplicaciones Visual Basic porque no son objetos COM verdaderos.</span><span class="sxs-lookup"><span data-stu-id="0ac25-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="0ac25-154">Los intentos de agregar referencias a estos objetos COM producirán un error.</span><span class="sxs-lookup"><span data-stu-id="0ac25-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="0ac25-155">Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0ac25-155">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac25-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ac25-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="0ac25-157">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="0ac25-157">COM Interop</span></span>](index.md)
- [<span data-ttu-id="0ac25-158">Tutorial: Implementación de la herencia mediante objetos COM</span><span class="sxs-lookup"><span data-stu-id="0ac25-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="0ac25-159">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="0ac25-159">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="0ac25-160">Interoperabilidad COM en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0ac25-160">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="0ac25-161">Solución de problemas de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="0ac25-161">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
