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
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a>Crear un servicio  

 Para crear un servicio que actúa como conducto de información entre el diseñador y el host, se deben crear una interfaz y una implementación. La interfaz la utiliza el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A> para definir los miembros del servicio y la implementación contiene la lógica para el servicio. En el ejemplo de código siguiente, se crean una interfaz y una implementación de servicio.  
  
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
  
## <a name="publishing-a-service"></a>Publicar un servicio  

 Para que un diseñador utilice un servicio, primero debe ser publicado por el host mediante el método <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.  
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Suscribirse a un servicio  

 El diseñador obtiene acceso al servicio utilizando el método <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> en el método <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>. El fragmento de código siguiente muestra cómo suscribirse a un servicio.  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a>Compartir datos utilizando la colección Items  

 El uso de la colección Items es similar al de la colección Services, salvo que se usa <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> en lugar de Publish. Esta colección es más adecuada para compartir datos simples entre los diseñadores y el host, en lugar de una funcionalidad compleja.  
  
## <a name="editingcontext-host-items-and-services"></a>Servicios y elementos host de EditingContext  

 En el .NET Framework se proporciona una serie de elementos y servicios integrados a los que se tiene acceso a través del contexto de edición.  
  
 Elementos:  
  
- <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: administra la lista de ensamblados locales a los que se hace referencia que se utilizarán en el flujo de trabajo para los controles (como el editor de expresiones).  
  
- <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: indica si el diseñador está en estado de solo lectura.  
  
- <xref:System.Activities.Presentation.View.Selection>: define la colección de objetos seleccionados actualmente.  
  
- <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
- <xref:System.Activities.Presentation.WorkflowFileItem>: proporciona información sobre el archivo en que se basa la sesión de edición actual.  
  
 Servicios:  
  
- <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: permite agregar propiedades a la instancia actual utilizando <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
- <xref:System.Activities.Presentation.View.DesignerView>: permite el acceso a las propiedades del lienzo del diseñador.  
  
- <xref:System.Activities.Presentation.IActivityToolboxService>: permite la actualización del contenido del cuadro de herramientas.  
  
- <xref:System.Activities.Presentation.Hosting.ICommandService>: se utiliza para integrar los comandos del diseñador (como el menú contextual) con implementaciones de servicio personalizadas.  
  
- <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: proporciona funcionalidad para el depurador del diseñador.  
  
- <xref:System.Activities.Presentation.View.IExpressionEditorService>: proporciona acceso al cuadro de diálogo Editor de expresiones.  
  
- <xref:System.Activities.Presentation.IIntegratedHelpService>: proporciona funcionalidad de ayuda integrada al diseñador.  
  
- <xref:System.Activities.Presentation.Validation.IValidationErrorService>: proporciona acceso a los errores de validación utilizando <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.  
  
- <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: proporciona un servicio interno para almacenar y recuperar datos. Este servicio lo usa internamente el .NET Framework y no está diseñado para uso externo.  
  
- <xref:System.Activities.Presentation.IXamlLoadErrorService>: proporciona acceso a la colección de errores de carga de XAML utilizando <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
- <xref:System.Activities.Presentation.Services.ModelService>: lo utiliza el diseñador para interactuar con el modelo del flujo de trabajo que se está editando.  
  
- <xref:System.Activities.Presentation.Model.ModelTreeManager>: proporciona acceso a la raíz del árbol de elementos de modelo utilizando <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
- <xref:System.Activities.Presentation.UndoEngine>: proporciona funcionalidad de deshacer y rehacer.  
  
- <xref:System.Activities.Presentation.Services.ViewService>: asigna elementos visuales a elementos de modelo subyacentes.  
  
- <xref:System.Activities.Presentation.View.ViewStateService>: almacena los estados de vista de los elementos de modelo.  
  
- <xref:System.Activities.Presentation.View.VirtualizedContainerService>: se usa para personalizar el comportamiento de la interfaz de usuario de contenedor virtual.  
  
- <xref:System.Activities.Presentation.Hosting.WindowHelperService>: se utiliza para registrar y eliminar del Registro los delegados para las notificaciones de eventos. También permite establecer el propietario de una ventana.
