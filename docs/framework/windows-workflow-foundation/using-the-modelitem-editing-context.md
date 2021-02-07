---
description: 'Más información sobre: usar el contexto de edición de ModelItem'
title: Utilizar el contexto de edición de ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: 7b6b9015f250d0e52f15e574f62386fa94a68e11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755023"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="5a8ef-103">Utilizar el contexto de edición de ModelItem</span><span class="sxs-lookup"><span data-stu-id="5a8ef-103">Using the ModelItem Editing Context</span></span>

<span data-ttu-id="5a8ef-104">El contexto de edición de <xref:System.Activities.Presentation.Model.ModelItem> es el objeto que la aplicación host usa para comunicarse con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-104">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <span data-ttu-id="5a8ef-105"><xref:System.Activities.Presentation.EditingContext> expone dos métodos, <xref:System.Activities.Presentation.EditingContext.Items%2A> y <xref:System.Activities.Presentation.EditingContext.Services%2A>, que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-105"><xref:System.Activities.Presentation.EditingContext> exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="5a8ef-106">La colección Items</span><span class="sxs-lookup"><span data-stu-id="5a8ef-106">The Items collection</span></span>  

 <span data-ttu-id="5a8ef-107">La colección <xref:System.Activities.Presentation.EditingContext.Items%2A> se utiliza para tener acceso a los datos que se comparten entre el host y el diseñador, o a los datos disponibles para todos los diseñadores.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-107">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="5a8ef-108">Esta colección tiene las siguientes capacidades, cuyo acceso se obtiene a través de la clase <xref:System.Activities.Presentation.ContextItemManager>:</span><span class="sxs-lookup"><span data-stu-id="5a8ef-108">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="5a8ef-109">La colección Services</span><span class="sxs-lookup"><span data-stu-id="5a8ef-109">The Services collection</span></span>  

 <span data-ttu-id="5a8ef-110">La colección <xref:System.Activities.Presentation.EditingContext.Services%2A> se utiliza para tener acceso a los servicios que el diseñador utiliza para interactuar con el host, o a los servicios que todos los diseñadores utilizan.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-110">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="5a8ef-111">Esta colección tiene los siguientes métodos reseñables:</span><span class="sxs-lookup"><span data-stu-id="5a8ef-111">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="5a8ef-112">Asignar una actividad a un diseñador</span><span class="sxs-lookup"><span data-stu-id="5a8ef-112">Assigning a designer an activity</span></span>  

 <span data-ttu-id="5a8ef-113">Para especificar qué diseñador utiliza una actividad, se usa el atributo Designer.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-113">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="5a8ef-114">Crear un servicio</span><span class="sxs-lookup"><span data-stu-id="5a8ef-114">Creating a service</span></span>  

 <span data-ttu-id="5a8ef-115">Para crear un servicio que actúa como conducto de información entre el diseñador y el host, se deben crear una interfaz y una implementación.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-115">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="5a8ef-116">La interfaz la utiliza el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A> para definir los miembros del servicio y la implementación contiene la lógica para el servicio.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-116">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="5a8ef-117">En el ejemplo de código siguiente, se crean una interfaz y una implementación de servicio.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-117">In the following code example, a service interface and implementation are created.</span></span>  
  
```csharp  
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
  
## <a name="publishing-a-service"></a><span data-ttu-id="5a8ef-118">Publicar un servicio</span><span class="sxs-lookup"><span data-stu-id="5a8ef-118">Publishing a service</span></span>  

 <span data-ttu-id="5a8ef-119">Para que un diseñador utilice un servicio, primero debe ser publicado por el host mediante el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-119">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="5a8ef-120">Suscribirse a un servicio</span><span class="sxs-lookup"><span data-stu-id="5a8ef-120">Subscribing to a service</span></span>  

 <span data-ttu-id="5a8ef-121">El diseñador obtiene acceso al servicio utilizando el método <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> en el método <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-121">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="5a8ef-122">El fragmento de código siguiente muestra cómo suscribirse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-122">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```csharp  
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
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="5a8ef-123">Compartir datos utilizando la colección Items</span><span class="sxs-lookup"><span data-stu-id="5a8ef-123">Sharing data using the Items collection</span></span>  

 <span data-ttu-id="5a8ef-124">El uso de la colección Items es similar al de la colección Services, salvo que se usa <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> en lugar de Publish.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-124">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="5a8ef-125">Esta colección es más adecuada para compartir datos simples entre los diseñadores y el host, en lugar de una funcionalidad compleja.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-125">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="5a8ef-126">Servicios y elementos host de EditingContext</span><span class="sxs-lookup"><span data-stu-id="5a8ef-126">EditingContext host items and services</span></span>  

 <span data-ttu-id="5a8ef-127">En el .NET Framework se proporciona una serie de elementos y servicios integrados a los que se tiene acceso a través del contexto de edición.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-127">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="5a8ef-128">Elementos:</span><span class="sxs-lookup"><span data-stu-id="5a8ef-128">Items:</span></span>  
  
- <span data-ttu-id="5a8ef-129"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: administra la lista de ensamblados locales a los que se hace referencia que se utilizarán en el flujo de trabajo para los controles (como el editor de expresiones).</span><span class="sxs-lookup"><span data-stu-id="5a8ef-129"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
- <span data-ttu-id="5a8ef-130"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: indica si el diseñador está en estado de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-130"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indicates whether the designer is in a read-only state.</span></span>  
  
- <span data-ttu-id="5a8ef-131"><xref:System.Activities.Presentation.View.Selection>: define la colección de objetos seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-131"><xref:System.Activities.Presentation.View.Selection>: Defines the collection of objects that are currently selected.</span></span>  
  
- <span data-ttu-id="5a8ef-132"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span><span class="sxs-lookup"><span data-stu-id="5a8ef-132"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span></span>  
  
- <span data-ttu-id="5a8ef-133"><xref:System.Activities.Presentation.WorkflowFileItem>: proporciona información sobre el archivo en que se basa la sesión de edición actual.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-133"><xref:System.Activities.Presentation.WorkflowFileItem>: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="5a8ef-134">Servicios:</span><span class="sxs-lookup"><span data-stu-id="5a8ef-134">Services:</span></span>  
  
- <span data-ttu-id="5a8ef-135"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: permite agregar propiedades a la instancia actual utilizando <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-135"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
- <span data-ttu-id="5a8ef-136"><xref:System.Activities.Presentation.View.DesignerView>: permite el acceso a las propiedades del lienzo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-136"><xref:System.Activities.Presentation.View.DesignerView>: Allows access to the properties of the designer canvas.</span></span>  
  
- <span data-ttu-id="5a8ef-137"><xref:System.Activities.Presentation.IActivityToolboxService>: permite la actualización del contenido del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-137"><xref:System.Activities.Presentation.IActivityToolboxService>: Allows the contents of the toolbox to be updated.</span></span>  
  
- <span data-ttu-id="5a8ef-138"><xref:System.Activities.Presentation.Hosting.ICommandService>: se utiliza para integrar los comandos del diseñador (como el menú contextual) con implementaciones de servicio personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-138"><xref:System.Activities.Presentation.Hosting.ICommandService>: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
- <span data-ttu-id="5a8ef-139"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: proporciona funcionalidad para el depurador del diseñador.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-139"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Provides functionality for the designer debugger.</span></span>  
  
- <span data-ttu-id="5a8ef-140"><xref:System.Activities.Presentation.View.IExpressionEditorService>: proporciona acceso al cuadro de diálogo Editor de expresiones.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-140"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Provides access to the Expression Editor dialog.</span></span>  
  
- <span data-ttu-id="5a8ef-141"><xref:System.Activities.Presentation.IIntegratedHelpService>: proporciona funcionalidad de ayuda integrada al diseñador.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-141"><xref:System.Activities.Presentation.IIntegratedHelpService>: Provides the designer with integrated help functionality.</span></span>  
  
- <span data-ttu-id="5a8ef-142"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: proporciona acceso a los errores de validación utilizando <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-142"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
- <span data-ttu-id="5a8ef-143"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: proporciona un servicio interno para almacenar y recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-143"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="5a8ef-144">Este servicio lo usa internamente el .NET Framework y no está diseñado para uso externo.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-144">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
- <span data-ttu-id="5a8ef-145"><xref:System.Activities.Presentation.IXamlLoadErrorService>: proporciona acceso a la colección de errores de carga de XAML utilizando <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-145"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
- <span data-ttu-id="5a8ef-146"><xref:System.Activities.Presentation.Services.ModelService>: lo utiliza el diseñador para interactuar con el modelo del flujo de trabajo que se está editando.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-146"><xref:System.Activities.Presentation.Services.ModelService>: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
- <span data-ttu-id="5a8ef-147"><xref:System.Activities.Presentation.Model.ModelTreeManager>: proporciona acceso a la raíz del árbol de elementos de modelo utilizando <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-147"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
- <span data-ttu-id="5a8ef-148"><xref:System.Activities.Presentation.UndoEngine>: proporciona funcionalidad de deshacer y rehacer.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-148"><xref:System.Activities.Presentation.UndoEngine>: Provides undo and redo functionality.</span></span>  
  
- <span data-ttu-id="5a8ef-149"><xref:System.Activities.Presentation.Services.ViewService>: asigna elementos visuales a elementos de modelo subyacentes.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-149"><xref:System.Activities.Presentation.Services.ViewService>: Maps visual elements to underlying model items.</span></span>  
  
- <span data-ttu-id="5a8ef-150"><xref:System.Activities.Presentation.View.ViewStateService>: almacena los estados de vista de los elementos de modelo.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-150"><xref:System.Activities.Presentation.View.ViewStateService>: Stores view states for model items.</span></span>  
  
- <span data-ttu-id="5a8ef-151"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: se usa para personalizar el comportamiento de la interfaz de usuario de contenedor virtual.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-151"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Used to customize the virtual container UI behavior.</span></span>  
  
- <span data-ttu-id="5a8ef-152"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: se utiliza para registrar y eliminar del Registro los delegados para las notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-152"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="5a8ef-153">También permite establecer el propietario de una ventana.</span><span class="sxs-lookup"><span data-stu-id="5a8ef-153">Also allows a window owner to be set.</span></span>
