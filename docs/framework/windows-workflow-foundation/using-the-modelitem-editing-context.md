---
title: Utilizar el contexto de edición de ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a2628bbbf2f6684e5d484b05cd5a2ac622f3b664
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296896"
---
# <a name="using-the-modelitem-editing-context"></a>Utilizar el contexto de edición de ModelItem
El contexto de edición de <xref:System.Activities.Presentation.Model.ModelItem> es el objeto que la aplicación host usa para comunicarse con el diseñador. <xref:System.Activities.Presentation.EditingContext> expone dos métodos, <xref:System.Activities.Presentation.EditingContext.Items%2A> y <xref:System.Activities.Presentation.EditingContext.Services%2A>, que se pueden usar.  
  
## <a name="the-items-collection"></a>La colección Items  
 La colección <xref:System.Activities.Presentation.EditingContext.Items%2A> se utiliza para tener acceso a los datos que se comparten entre el host y el diseñador, o a los datos disponibles para todos los diseñadores. Esta colección tiene las siguientes capacidades, cuyo acceso se obtiene a través de la clase <xref:System.Activities.Presentation.ContextItemManager>:  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a>La colección Services  
 La colección <xref:System.Activities.Presentation.EditingContext.Services%2A> se utiliza para tener acceso a los servicios que el diseñador utiliza para interactuar con el host, o a los servicios que todos los diseñadores utilizan. Esta colección tiene los siguientes métodos reseñables:  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a>Asignar una actividad a un diseñador  
 Para especificar qué diseñador utiliza una actividad, se usa el atributo Designer.  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a>Crear un servicio  
 Para crear un servicio que actúa como conducto de información entre el diseñador y el host, se deben crear una interfaz y una implementación. La interfaz la utiliza el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A> para definir los miembros del servicio y la implementación contiene la lógica para el servicio. En el ejemplo de código siguiente, se crean una interfaz y una implementación de servicio.  
  
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
  
## <a name="publishing-a-service"></a>Publicar un servicio  
 Para que un diseñador utilice un servicio, primero debe ser publicado por el host mediante el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Suscribirse a un servicio  
 El diseñador obtiene acceso al servicio utilizando el método <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> en el método <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>. El fragmento de código siguiente muestra cómo suscribirse a un servicio.  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a>Compartir datos utilizando la colección Items  
 El uso de la colección Items es similar al de la colección Services, salvo que se usa <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> en lugar de Publish. Esta colección es más adecuada para compartir datos simples entre los diseñadores y el host, en lugar de una funcionalidad compleja.  
  
## <a name="editingcontext-host-items-and-services"></a>Servicios y elementos host de EditingContext  
 .NET Framework proporciona un número de elementos integrados y los servicios que se tiene acceso mediante el contexto de edición.  
  
 Elementos:  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Administra la lista de ensamblados locales que se hace referencia que se usará en el flujo de trabajo para los controles (por ejemplo, el editor de expresiones).  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indica si el diseñador está en un estado de solo lectura.  
  
-   <xref:System.Activities.Presentation.View.Selection>: Define la colección de objetos que están seleccionados actualmente.  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem>: Proporciona información sobre el archivo que se basa la sesión de edición actual.  
  
 Servicios:  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Permite que las propiedades que se agregarán a la instancia actual, mediante <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
-   <xref:System.Activities.Presentation.View.DesignerView>: Permite el acceso a las propiedades del lienzo del diseñador.  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService>: Permite que el contenido del cuadro de herramientas se puede actualizar.  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService>: Usar para integrar los comandos del diseñador (por ejemplo, el menú contextual) con implementaciones de servicio personalizado.  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Proporciona funcionalidad para el depurador del diseñador.  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService>: Proporciona acceso al cuadro de diálogo Editor de expresiones.  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService>: Proporciona el diseñador con ayuda integrada.  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService>: Proporciona acceso a los errores de validación mediante <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Proporciona un servicio interno para almacenar y recuperar datos. Este servicio se usa internamente por .NET Framework y no está pensado para uso externo.  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService>: Proporciona acceso a XAML load error colección mediante <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
-   <xref:System.Activities.Presentation.Services.ModelService>: Usa el diseñador para interactuar con el modelo del flujo de trabajo que se está editando.  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager>: Proporciona acceso a la raíz del árbol de elementos de modelo utilizando <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
-   <xref:System.Activities.Presentation.UndoEngine>: Proporciona la fase de reversión y funcionalidad de puesta al día.  
  
-   <xref:System.Activities.Presentation.Services.ViewService>: Asigna elementos visuales a elementos del modelo subyacente.  
  
-   <xref:System.Activities.Presentation.View.ViewStateService>: Almacena los Estados de elementos de modelo de vista.  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService>: Se usa para personalizar el comportamiento de la interfaz de usuario de contenedor virtual.  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService>: Se usa para registrar y anular el registro de delegados para las notificaciones de eventos. También permite establecer el propietario de una ventana.
