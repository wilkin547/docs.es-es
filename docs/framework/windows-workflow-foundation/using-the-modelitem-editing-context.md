---
title: Utilizar el contexto de edición de ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a2628bbbf2f6684e5d484b05cd5a2ac622f3b664
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296896"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="07d2b-102">Utilizar el contexto de edición de ModelItem</span><span class="sxs-lookup"><span data-stu-id="07d2b-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="07d2b-103">El contexto de edición de <xref:System.Activities.Presentation.Model.ModelItem> es el objeto que la aplicación host usa para comunicarse con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="07d2b-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <xref:System.Activities.Presentation.EditingContext> <span data-ttu-id="07d2b-104">expone dos métodos, <xref:System.Activities.Presentation.EditingContext.Items%2A> y <xref:System.Activities.Presentation.EditingContext.Services%2A>, que se puede usar</span><span class="sxs-lookup"><span data-stu-id="07d2b-104">exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="07d2b-105">La colección Items</span><span class="sxs-lookup"><span data-stu-id="07d2b-105">The Items collection</span></span>  
 <span data-ttu-id="07d2b-106">La colección <xref:System.Activities.Presentation.EditingContext.Items%2A> se utiliza para tener acceso a los datos que se comparten entre el host y el diseñador, o a los datos disponibles para todos los diseñadores.</span><span class="sxs-lookup"><span data-stu-id="07d2b-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="07d2b-107">Esta colección tiene las siguientes capacidades, cuyo acceso se obtiene a través de la clase <xref:System.Activities.Presentation.ContextItemManager>:</span><span class="sxs-lookup"><span data-stu-id="07d2b-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="07d2b-108">La colección Services</span><span class="sxs-lookup"><span data-stu-id="07d2b-108">The Services collection</span></span>  
 <span data-ttu-id="07d2b-109">La colección <xref:System.Activities.Presentation.EditingContext.Services%2A> se utiliza para tener acceso a los servicios que el diseñador utiliza para interactuar con el host, o a los servicios que todos los diseñadores utilizan.</span><span class="sxs-lookup"><span data-stu-id="07d2b-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="07d2b-110">Esta colección tiene los siguientes métodos reseñables:</span><span class="sxs-lookup"><span data-stu-id="07d2b-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="07d2b-111">Asignar una actividad a un diseñador</span><span class="sxs-lookup"><span data-stu-id="07d2b-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="07d2b-112">Para especificar qué diseñador utiliza una actividad, se usa el atributo Designer.</span><span class="sxs-lookup"><span data-stu-id="07d2b-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="07d2b-113">Crear un servicio</span><span class="sxs-lookup"><span data-stu-id="07d2b-113">Creating a service</span></span>  
 <span data-ttu-id="07d2b-114">Para crear un servicio que actúa como conducto de información entre el diseñador y el host, se deben crear una interfaz y una implementación.</span><span class="sxs-lookup"><span data-stu-id="07d2b-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="07d2b-115">La interfaz la utiliza el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A> para definir los miembros del servicio y la implementación contiene la lógica para el servicio.</span><span class="sxs-lookup"><span data-stu-id="07d2b-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="07d2b-116">En el ejemplo de código siguiente, se crean una interfaz y una implementación de servicio.</span><span class="sxs-lookup"><span data-stu-id="07d2b-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
```  
  
## <a name="publishing-a-service"></a><span data-ttu-id="07d2b-117">Publicar un servicio</span><span class="sxs-lookup"><span data-stu-id="07d2b-117">Publishing a service</span></span>  
 <span data-ttu-id="07d2b-118">Para que un diseñador utilice un servicio, primero debe ser publicado por el host mediante el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d2b-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="07d2b-119">Suscribirse a un servicio</span><span class="sxs-lookup"><span data-stu-id="07d2b-119">Subscribing to a service</span></span>  
 <span data-ttu-id="07d2b-120">El diseñador obtiene acceso al servicio utilizando el método <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> en el método <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d2b-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="07d2b-121">El fragmento de código siguiente muestra cómo suscribirse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="07d2b-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
```  
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="07d2b-122">Compartir datos utilizando la colección Items</span><span class="sxs-lookup"><span data-stu-id="07d2b-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="07d2b-123">El uso de la colección Items es similar al de la colección Services, salvo que se usa <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> en lugar de Publish.</span><span class="sxs-lookup"><span data-stu-id="07d2b-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="07d2b-124">Esta colección es más adecuada para compartir datos simples entre los diseñadores y el host, en lugar de una funcionalidad compleja.</span><span class="sxs-lookup"><span data-stu-id="07d2b-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="07d2b-125">Servicios y elementos host de EditingContext</span><span class="sxs-lookup"><span data-stu-id="07d2b-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="07d2b-126">.NET Framework proporciona un número de elementos integrados y los servicios que se tiene acceso mediante el contexto de edición.</span><span class="sxs-lookup"><span data-stu-id="07d2b-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="07d2b-127">Elementos:</span><span class="sxs-lookup"><span data-stu-id="07d2b-127">Items:</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem><span data-ttu-id="07d2b-128">: Administra la lista de ensamblados locales que se hace referencia que se usará en el flujo de trabajo para los controles (por ejemplo, el editor de expresiones).</span><span class="sxs-lookup"><span data-stu-id="07d2b-128">: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState><span data-ttu-id="07d2b-129">: Indica si el diseñador está en un estado de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="07d2b-129">: Indicates whether the designer is in a read-only state.</span></span>  
  
-   <xref:System.Activities.Presentation.View.Selection><span data-ttu-id="07d2b-130">: Define la colección de objetos que están seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="07d2b-130">: Defines the collection of objects that are currently selected.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem><span data-ttu-id="07d2b-131">:</span><span class="sxs-lookup"><span data-stu-id="07d2b-131">:</span></span>  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem><span data-ttu-id="07d2b-132">: Proporciona información sobre el archivo que se basa la sesión de edición actual.</span><span class="sxs-lookup"><span data-stu-id="07d2b-132">: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="07d2b-133">Servicios:</span><span class="sxs-lookup"><span data-stu-id="07d2b-133">Services:</span></span>  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService><span data-ttu-id="07d2b-134">: Permite que las propiedades que se agregarán a la instancia actual, mediante <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d2b-134">: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.View.DesignerView><span data-ttu-id="07d2b-135">: Permite el acceso a las propiedades del lienzo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="07d2b-135">: Allows access to the properties of the designer canvas.</span></span>  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService><span data-ttu-id="07d2b-136">: Permite que el contenido del cuadro de herramientas se puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="07d2b-136">: Allows the contents of the toolbox to be updated.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService><span data-ttu-id="07d2b-137">: Usar para integrar los comandos del diseñador (por ejemplo, el menú contextual) con implementaciones de servicio personalizado.</span><span class="sxs-lookup"><span data-stu-id="07d2b-137">: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView><span data-ttu-id="07d2b-138">: Proporciona funcionalidad para el depurador del diseñador.</span><span class="sxs-lookup"><span data-stu-id="07d2b-138">: Provides functionality for the designer debugger.</span></span>  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService><span data-ttu-id="07d2b-139">: Proporciona acceso al cuadro de diálogo Editor de expresiones.</span><span class="sxs-lookup"><span data-stu-id="07d2b-139">: Provides access to the Expression Editor dialog.</span></span>  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService><span data-ttu-id="07d2b-140">: Proporciona el diseñador con ayuda integrada.</span><span class="sxs-lookup"><span data-stu-id="07d2b-140">: Provides the designer with integrated help functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService><span data-ttu-id="07d2b-141">: Proporciona acceso a los errores de validación mediante <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d2b-141">: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService><span data-ttu-id="07d2b-142">: Proporciona un servicio interno para almacenar y recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="07d2b-142">: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="07d2b-143">Este servicio se usa internamente por .NET Framework y no está pensado para uso externo.</span><span class="sxs-lookup"><span data-stu-id="07d2b-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService><span data-ttu-id="07d2b-144">: Proporciona acceso a XAML load error colección mediante <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d2b-144">: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ModelService><span data-ttu-id="07d2b-145">: Usa el diseñador para interactuar con el modelo del flujo de trabajo que se está editando.</span><span class="sxs-lookup"><span data-stu-id="07d2b-145">: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager><span data-ttu-id="07d2b-146">: Proporciona acceso a la raíz del árbol de elementos de modelo utilizando <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d2b-146">: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.UndoEngine><span data-ttu-id="07d2b-147">: Proporciona la fase de reversión y funcionalidad de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="07d2b-147">: Provides undo and redo functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ViewService><span data-ttu-id="07d2b-148">: Asigna elementos visuales a elementos del modelo subyacente.</span><span class="sxs-lookup"><span data-stu-id="07d2b-148">: Maps visual elements to underlying model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.ViewStateService><span data-ttu-id="07d2b-149">: Almacena los Estados de elementos de modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="07d2b-149">: Stores view states for model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService><span data-ttu-id="07d2b-150">: Se usa para personalizar el comportamiento de la interfaz de usuario de contenedor virtual.</span><span class="sxs-lookup"><span data-stu-id="07d2b-150">: Used to customize the virtual container UI behavior.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService><span data-ttu-id="07d2b-151">: Se usa para registrar y anular el registro de delegados para las notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="07d2b-151">: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="07d2b-152">También permite establecer el propietario de una ventana.</span><span class="sxs-lookup"><span data-stu-id="07d2b-152">Also allows a window owner to be set.</span></span>
