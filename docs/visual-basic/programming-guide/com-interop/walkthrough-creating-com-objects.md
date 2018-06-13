---
title: 'Tutorial: Crear objetos COM con Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: caf0a071d65746f1027052e648ade538d62dc4bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643866"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="22a5d-102">Tutorial: Crear objetos COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22a5d-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="22a5d-103">Al crear nuevas aplicaciones o componentes, es mejor crear ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22a5d-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="22a5d-104">Sin embargo, Visual Basic facilita también la exposición de un componente de .NET Framework a COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="22a5d-105">Esto le permite proporcionar nuevos componentes para conjuntos de aplicaciones anteriores que requieren componentes COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="22a5d-106">Este tutorial muestra cómo usar Visual Basic para exponer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objetos como objetos COM, con y sin la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-106">This walkthrough demonstrates how to use Visual Basic to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="22a5d-107">Es la manera más fácil de exponer objetos COM mediante la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="22a5d-108">La plantilla de clase COM crea una nueva clase y, a continuación, configura el proyecto para generar el nivel de clase e interoperabilidad como un objeto COM y registrarlo con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="22a5d-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22a5d-109">Aunque también puede exponer una clase creada en Visual Basic como un objeto COM para código no administrado, no es un objeto COM es true y no se puede usar Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="22a5d-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="22a5d-110">Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="22a5d-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="22a5d-111">Para crear un objeto COM mediante la plantilla de clase COM</span><span class="sxs-lookup"><span data-stu-id="22a5d-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="22a5d-112">Abra un nuevo proyecto de aplicación para Windows desde el **archivo** menú haciendo clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="22a5d-113">En el **nuevo proyecto** cuadro de diálogo en el **tipos de proyecto** , a continuación, compruebe que Windows está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="22a5d-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="22a5d-114">Seleccione **biblioteca de clases** desde el **plantillas** lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="22a5d-115">Se muestra el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="22a5d-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="22a5d-116">Seleccione **Agregar nuevo elemento** desde el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="22a5d-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="22a5d-117">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="22a5d-118">Seleccione **clase COM** desde el **plantillas** lista y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="22a5d-119">Visual Basic agrega una nueva clase y configura el nuevo proyecto para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="22a5d-120">Agregue código como propiedades, métodos y eventos a la clase COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="22a5d-121">Seleccione **generar ClassLibrary1** desde el **generar** menú.</span><span class="sxs-lookup"><span data-stu-id="22a5d-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="22a5d-122">Visual Basic genera el ensamblado y registra el objeto COM con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="22a5d-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="22a5d-123">Crear objetos COM sin la plantilla de clase COM</span><span class="sxs-lookup"><span data-stu-id="22a5d-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="22a5d-124">También puede crear una clase COM manualmente en lugar de usar la plantilla de clase COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="22a5d-125">Este procedimiento es útil cuando se trabaja desde la línea de comandos o cuando desee más control sobre cómo se definen los objetos COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="22a5d-126">Para configurar el proyecto para generar un objeto COM</span><span class="sxs-lookup"><span data-stu-id="22a5d-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="22a5d-127">Abra un nuevo proyecto de aplicación para Windows desde el **archivo** menú haciendo clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="22a5d-128">En el **nuevo proyecto** cuadro de diálogo en el **tipos de proyecto** , a continuación, compruebe que Windows está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="22a5d-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="22a5d-129">Seleccione **biblioteca de clases** desde el **plantillas** lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="22a5d-130">Se muestra el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="22a5d-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="22a5d-131">En **el Explorador de soluciones**, haga clic en el proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="22a5d-132">El **Diseñador de proyectos** se muestra.</span><span class="sxs-lookup"><span data-stu-id="22a5d-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="22a5d-133">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="22a5d-134">Seleccione el **registrar para interoperabilidad COM** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="22a5d-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="22a5d-135">Para configurar el código de la clase para crear un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="22a5d-136">En **el Explorador de soluciones**, haga doble clic en **Class1.vb** para mostrar su código.</span><span class="sxs-lookup"><span data-stu-id="22a5d-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="22a5d-137">Cambie el nombre de la clase a `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="22a5d-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="22a5d-138">Agregue las siguientes constantes a `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="22a5d-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="22a5d-139">Almacenará las constantes de identificador único global (GUID) que los objetos COM se deben tener.</span><span class="sxs-lookup"><span data-stu-id="22a5d-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  <span data-ttu-id="22a5d-140">En el menú **Herramientas**, haga clic en **Crear GUID**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="22a5d-141">En el cuadro de diálogo **Crear GUID**, haga clic en **Formato de Registro** y luego en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="22a5d-142">Haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="22a5d-142">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="22a5d-143">Reemplace la cadena vacía para el `ClassId` con el GUID, las llaves quitando las iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="22a5d-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="22a5d-144">Por ejemplo, si el GUID proporcionado por Guidgen es `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , a continuación, el código debe aparecer como sigue.</span><span class="sxs-lookup"><span data-stu-id="22a5d-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  <span data-ttu-id="22a5d-145">Repita los pasos anteriores para la `InterfaceId` y `EventsId` constantes, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="22a5d-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="22a5d-146">Asegúrese de que los GUID son nuevos y únicos; en caso contrario, el componente COM podría entrar en conflicto con otros componentes COM.</span><span class="sxs-lookup"><span data-stu-id="22a5d-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="22a5d-147">Agregar el `ComClass` atribuir a `ComClass1`, especificando los GUID para el Id. de clase, el identificador de interfaz y el identificador de eventos como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22a5d-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  <span data-ttu-id="22a5d-148">Clases COM deben tener un sin parámetros `Public Sub New()` constructor o la clase no se registrará correctamente.</span><span class="sxs-lookup"><span data-stu-id="22a5d-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="22a5d-149">Agregue un constructor sin parámetros a la clase:</span><span class="sxs-lookup"><span data-stu-id="22a5d-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. <span data-ttu-id="22a5d-150">Agregue propiedades, métodos y eventos a la clase, finalizando con un `End Class` instrucción.</span><span class="sxs-lookup"><span data-stu-id="22a5d-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="22a5d-151">Seleccione **generar solución** desde el **generar** menú.</span><span class="sxs-lookup"><span data-stu-id="22a5d-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="22a5d-152">Visual Basic genera el ensamblado y registra el objeto COM con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="22a5d-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22a5d-153">Los objetos COM que genere con Visual Basic no se puede usar para otras aplicaciones de Visual Basic porque no son objetos COM es true.</span><span class="sxs-lookup"><span data-stu-id="22a5d-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="22a5d-154">Si intenta agregar referencias a estos objetos COM, producirá un error.</span><span class="sxs-lookup"><span data-stu-id="22a5d-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="22a5d-155">Para obtener más información, consulte [interoperabilidad COM en aplicaciones de .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="22a5d-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a5d-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="22a5d-156">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [<span data-ttu-id="22a5d-157">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="22a5d-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="22a5d-158">Tutorial: Implementación de la herencia mediante objetos COM</span><span class="sxs-lookup"><span data-stu-id="22a5d-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="22a5d-159">#Region (directiva)</span><span class="sxs-lookup"><span data-stu-id="22a5d-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="22a5d-160">Interoperabilidad COM en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="22a5d-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="22a5d-161">Solución de problemas de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="22a5d-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
