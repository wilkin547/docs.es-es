---
title: "Usar el &#225;mbito de edici&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79306f9e-318b-4687-9863-8b93d1841716
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Usar el &#225;mbito de edici&#243;n
Este ejemplo muestra cómo procesar un conjunto de cambios por lotes para que se puedan deshacer en una unidad atómica única.De forma predeterminada, las acciones realizadas por un autor del diseñador de actividades se integran automáticamente en el sistema Deshacer\/rehacer.  
  
## Demostraciones  
 Editar el ámbito y Deshacer\/Rehacer.  
  
## Análisis  
 En este ejemplo se muestra cómo procesar por lotes un conjunto de cambios en el árbol de <xref:System.Activities.Presentation.Model.ModelItem> dentro de una unidad única de trabajo.Tenga en cuenta que al enlazar directamente con los valores <xref:System.Activities.Presentation.Model.ModelItem> desde un diseñador de WPF, los cambios se aplican automáticamente.En este ejemplo se muestra lo que se debe hacer cuando se realizan mediante código imperativo varias modificaciones que se van a procesar por lotes, en lugar de un único cambio.  
  
 En este ejemplo, se agregan tres actividades.Cuando comienza la edición, se llama a <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> en una instancia de <xref:System.Activities.Presentation.Model.ModelItem>.Los cambios realizados en el árbol de <xref:System.Activities.Presentation.Model.ModelItem> dentro de este ámbito de edición se procesan por lotes.El comando <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> devuelve una clase <xref:System.Activities.Presentation.Model.EditingScope>, que se puede utilizar para controlar esta instancia.Se puede llamar a los métodos <xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> o <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A> para confirmar o revertir el ámbito de edición.  
  
 También puede anidar objetos <xref:System.Activities.Presentation.Model.EditingScope>, lo que permite realizar el seguimiento de varios conjuntos de cambios como parte de un ámbito de edición mayor y se pueden controlar individualmente.Por ejemplo, esta característica se podría utiliza cuando se deben confirmar o revertir por separado cambios de varios cuadros de diálogo y todos los cambios se tratan como una única operación atómica.En este ejemplo, los ámbitos de edición se apilan mediante una clase <xref:System.Collections.ObjectModel.ObservableCollection%601> de tipo <xref:System.Activities.Presentation.Model.ModelEditingScope>.Se utiliza <xref:System.Collections.ObjectModel.ObservableCollection%601> para que la profundidad del anidamiento se pueda observar en la superficie del diseñador.  
  
## Para configurar, compilar y ejecutar el ejemplo  
  
1.  Compile y ejecute el ejemplo y, a continuación, utilice los botones de la izquierda para modificar el flujo de trabajo.  
  
2.  Haga clic en **Open Editing Scope**.  
  
    1.  Este comando llama al método <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, que crea un ámbito de edición y lo inserta en la pila de edición.  
  
    2.  A continuación, se agregan tres actividades a la clase <xref:System.Activities.Presentation.Model.ModelItem> seleccionada.Tenga en cuenta que si el ámbito de edición no se hubiera abierto con <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, las tres actividades aparecerían en el lienzo del diseñador.Dado que esta operación todavía está pendiente dentro de la clase <xref:System.Activities.Presentation.Model.EditingScope>, el diseñador todavía no se actualiza.  
  
3.  Presione **Close Editing Scope** para confirmar el ámbito de edición.Las tres actividades aparecen en el diseñador.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\UsingEditingScope`