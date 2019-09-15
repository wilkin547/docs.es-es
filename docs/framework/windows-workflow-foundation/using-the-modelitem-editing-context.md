---
title: Utilizar el contexto de edición de ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a47cb53e50d221c0ae07cf0841688fe4f8ced7d4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988920"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="b90f7-102">Utilizar el contexto de edición de ModelItem</span><span class="sxs-lookup"><span data-stu-id="b90f7-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="b90f7-103">El contexto de edición de <xref:System.Activities.Presentation.Model.ModelItem> es el objeto que la aplicación host usa para comunicarse con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="b90f7-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <span data-ttu-id="b90f7-104"><xref:System.Activities.Presentation.EditingContext> expone dos métodos, <xref:System.Activities.Presentation.EditingContext.Items%2A> y <xref:System.Activities.Presentation.EditingContext.Services%2A>, que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="b90f7-104"><xref:System.Activities.Presentation.EditingContext> exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="b90f7-105">La colección Items</span><span class="sxs-lookup"><span data-stu-id="b90f7-105">The Items collection</span></span>  
 <span data-ttu-id="b90f7-106">La colección <xref:System.Activities.Presentation.EditingContext.Items%2A> se utiliza para tener acceso a los datos que se comparten entre el host y el diseñador, o a los datos disponibles para todos los diseñadores.</span><span class="sxs-lookup"><span data-stu-id="b90f7-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="b90f7-107">Esta colección tiene las siguientes capacidades, cuyo acceso se obtiene a través de la clase <xref:System.Activities.Presentation.ContextItemManager>:</span><span class="sxs-lookup"><span data-stu-id="b90f7-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="b90f7-108">La colección Services</span><span class="sxs-lookup"><span data-stu-id="b90f7-108">The Services collection</span></span>  
 <span data-ttu-id="b90f7-109">La colección <xref:System.Activities.Presentation.EditingContext.Services%2A> se utiliza para tener acceso a los servicios que el diseñador utiliza para interactuar con el host, o a los servicios que todos los diseñadores utilizan.</span><span class="sxs-lookup"><span data-stu-id="b90f7-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="b90f7-110">Esta colección tiene los siguientes métodos reseñables:</span><span class="sxs-lookup"><span data-stu-id="b90f7-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="b90f7-111">Asignar una actividad a un diseñador</span><span class="sxs-lookup"><span data-stu-id="b90f7-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="b90f7-112">Para especificar qué diseñador utiliza una actividad, se usa el atributo Designer.</span><span class="sxs-lookup"><span data-stu-id="b90f7-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="b90f7-113">Crear un servicio</span><span class="sxs-lookup"><span data-stu-id="b90f7-113">Creating a service</span></span>  
 <span data-ttu-id="b90f7-114">Para crear un servicio que actúa como conducto de información entre el diseñador y el host, se deben crear una interfaz y una implementación.</span><span class="sxs-lookup"><span data-stu-id="b90f7-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="b90f7-115">La interfaz la utiliza el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A> para definir los miembros del servicio y la implementación contiene la lógica para el servicio.</span><span class="sxs-lookup"><span data-stu-id="b90f7-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="b90f7-116">En el ejemplo de código siguiente, se crean una interfaz y una implementación de servicio.</span><span class="sxs-lookup"><span data-stu-id="b90f7-116">In the following code example, a service interface and implementation are created.</span></span>  
  
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
  
## <a name="publishing-a-service"></a><span data-ttu-id="b90f7-117">Publicar un servicio</span><span class="sxs-lookup"><span data-stu-id="b90f7-117">Publishing a service</span></span>  
 <span data-ttu-id="b90f7-118">Para que un diseñador utilice un servicio, primero debe ser publicado por el host mediante el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.</span><span class="sxs-lookup"><span data-stu-id="b90f7-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="b90f7-119">Suscribirse a un servicio</span><span class="sxs-lookup"><span data-stu-id="b90f7-119">Subscribing to a service</span></span>  
 <span data-ttu-id="b90f7-120">El diseñador obtiene acceso al servicio utilizando el método <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> en el método <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="b90f7-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="b90f7-121">El fragmento de código siguiente muestra cómo suscribirse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="b90f7-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="b90f7-122">Compartir datos utilizando la colección Items</span><span class="sxs-lookup"><span data-stu-id="b90f7-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="b90f7-123">El uso de la colección Items es similar al de la colección Services, salvo que se usa <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> en lugar de Publish.</span><span class="sxs-lookup"><span data-stu-id="b90f7-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="b90f7-124">Esta colección es más adecuada para compartir datos simples entre los diseñadores y el host, en lugar de una funcionalidad compleja.</span><span class="sxs-lookup"><span data-stu-id="b90f7-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="b90f7-125">Servicios y elementos host de EditingContext</span><span class="sxs-lookup"><span data-stu-id="b90f7-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="b90f7-126">En el .NET Framework se proporciona una serie de elementos y servicios integrados a los que se tiene acceso a través del contexto de edición.</span><span class="sxs-lookup"><span data-stu-id="b90f7-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="b90f7-127">Elementos:</span><span class="sxs-lookup"><span data-stu-id="b90f7-127">Items:</span></span>  
  
- <span data-ttu-id="b90f7-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Administra la lista de ensamblados locales a los que se hace referencia que se usarán dentro del flujo de trabajo para los controles (como el editor de expresiones).</span><span class="sxs-lookup"><span data-stu-id="b90f7-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
- <span data-ttu-id="b90f7-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indica si el diseñador está en un estado de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b90f7-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indicates whether the designer is in a read-only state.</span></span>  
  
- <span data-ttu-id="b90f7-130"><xref:System.Activities.Presentation.View.Selection>: Define la colección de objetos seleccionados actualmente.</span><span class="sxs-lookup"><span data-stu-id="b90f7-130"><xref:System.Activities.Presentation.View.Selection>: Defines the collection of objects that are currently selected.</span></span>  
  
- <span data-ttu-id="b90f7-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span><span class="sxs-lookup"><span data-stu-id="b90f7-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span></span>  
  
- <span data-ttu-id="b90f7-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Proporciona información sobre el archivo en el que se basa la sesión de edición actual.</span><span class="sxs-lookup"><span data-stu-id="b90f7-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="b90f7-133">Servicios:</span><span class="sxs-lookup"><span data-stu-id="b90f7-133">Services:</span></span>  
  
- <span data-ttu-id="b90f7-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Permite agregar propiedades a la instancia actual, utilizando <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="b90f7-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
- <span data-ttu-id="b90f7-135"><xref:System.Activities.Presentation.View.DesignerView>: Permite el acceso a las propiedades del lienzo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="b90f7-135"><xref:System.Activities.Presentation.View.DesignerView>: Allows access to the properties of the designer canvas.</span></span>  
  
- <span data-ttu-id="b90f7-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Permite que el contenido del cuadro de herramientas se actualice.</span><span class="sxs-lookup"><span data-stu-id="b90f7-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Allows the contents of the toolbox to be updated.</span></span>  
  
- <span data-ttu-id="b90f7-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Se usa para integrar comandos del diseñador (como menú contextual) con implementaciones de servicio proporcionadas por el personalizado.</span><span class="sxs-lookup"><span data-stu-id="b90f7-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
- <span data-ttu-id="b90f7-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Proporciona funcionalidad para el depurador del diseñador.</span><span class="sxs-lookup"><span data-stu-id="b90f7-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Provides functionality for the designer debugger.</span></span>  
  
- <span data-ttu-id="b90f7-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Proporciona acceso al cuadro de diálogo Editor de expresiones.</span><span class="sxs-lookup"><span data-stu-id="b90f7-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Provides access to the Expression Editor dialog.</span></span>  
  
- <span data-ttu-id="b90f7-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Proporciona al diseñador funcionalidad de ayuda integrada.</span><span class="sxs-lookup"><span data-stu-id="b90f7-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Provides the designer with integrated help functionality.</span></span>  
  
- <span data-ttu-id="b90f7-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Proporciona acceso a los errores de <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>validación mediante.</span><span class="sxs-lookup"><span data-stu-id="b90f7-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
- <span data-ttu-id="b90f7-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Proporciona un servicio interno para almacenar y recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="b90f7-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="b90f7-143">Este servicio lo usa internamente el .NET Framework y no está diseñado para uso externo.</span><span class="sxs-lookup"><span data-stu-id="b90f7-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
- <span data-ttu-id="b90f7-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Proporciona acceso a la colección de errores de carga <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>de XAML mediante.</span><span class="sxs-lookup"><span data-stu-id="b90f7-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
- <span data-ttu-id="b90f7-145"><xref:System.Activities.Presentation.Services.ModelService>: Lo utiliza el diseñador para interactuar con el modelo del flujo de trabajo que se está editando.</span><span class="sxs-lookup"><span data-stu-id="b90f7-145"><xref:System.Activities.Presentation.Services.ModelService>: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
- <span data-ttu-id="b90f7-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Proporciona acceso a la raíz del árbol de elementos de modelo <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>mediante.</span><span class="sxs-lookup"><span data-stu-id="b90f7-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
- <span data-ttu-id="b90f7-147"><xref:System.Activities.Presentation.UndoEngine>: Proporciona la funcionalidad de deshacer y rehacer.</span><span class="sxs-lookup"><span data-stu-id="b90f7-147"><xref:System.Activities.Presentation.UndoEngine>: Provides undo and redo functionality.</span></span>  
  
- <span data-ttu-id="b90f7-148"><xref:System.Activities.Presentation.Services.ViewService>: Asigna elementos visuales a elementos de modelo subyacentes.</span><span class="sxs-lookup"><span data-stu-id="b90f7-148"><xref:System.Activities.Presentation.Services.ViewService>: Maps visual elements to underlying model items.</span></span>  
  
- <span data-ttu-id="b90f7-149"><xref:System.Activities.Presentation.View.ViewStateService>: Almacena los Estados de vista de los elementos de modelo.</span><span class="sxs-lookup"><span data-stu-id="b90f7-149"><xref:System.Activities.Presentation.View.ViewStateService>: Stores view states for model items.</span></span>  
  
- <span data-ttu-id="b90f7-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Se usa para personalizar el comportamiento de la interfaz de usuario del contenedor virtual.</span><span class="sxs-lookup"><span data-stu-id="b90f7-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Used to customize the virtual container UI behavior.</span></span>  
  
- <span data-ttu-id="b90f7-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Se usa para registrar y anular el registro de delegados para las notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="b90f7-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="b90f7-152">También permite establecer el propietario de una ventana.</span><span class="sxs-lookup"><span data-stu-id="b90f7-152">Also allows a window owner to be set.</span></span>
