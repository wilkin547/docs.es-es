---
title: "Clase base NativeActivity | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Clase base NativeActivity
<xref:System.Activities.NativeActivity> es una clase abstracta con un constructor protegido.Al igual que ocurre con <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> se usa para escribir el comportamiento imperativo al implementar un método <xref:System.Activities.NativeActivity.Execute%2A>.A diferencia de <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> tiene acceso a todas las características expuestas del tiempo de ejecución del flujo de trabajo a través del objeto <xref:System.Activities.NativeActivityContext> pasado al método <xref:System.Activities.NativeActivity.Execute%2A>.  
  
## Usar NativeActivityContext  
 Se puede tener acceso a las características del tiempo de ejecución del flujo de trabajo desde dentro del método <xref:System.Activities.NativeActivity.Execute%2A> usando los miembros del parámetro `context`, del tipo <xref:System.Activities.NativeActivityContext>.Las características disponibles mediante <xref:System.Activities.NativeActivityContext> incluyen lo siguiente:  
  
-   Obtener y definir los argumentos y variables.  
  
-   Programar las actividades secundarias con <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>  
  
-   Anular la ejecución de la actividad con <xref:System.Activities.NativeActivityContext.Abort%2A>.  
  
-   Cancelar la ejecución secundaria con <xref:System.Activities.NativeActivityContext.CancelChild%2A> y <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.  
  
-   Obtener acceso a los marcadores de actividad usando dichos métodos como <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> y <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.  
  
-   Características de seguimiento personalizadas con <xref:System.Activities.CodeActivityContext.Track%2A>.  
  
-   Acceso a las propiedades de ejecución de la actividad y a las propiedades de los valores con <xref:System.Activities.CodeActivityContext.GetProperty%2A> y <xref:System.Activities.NativeActivityContext.GetValue%2A>.  
  
-   Programar las acciones de la actividad y las funciones mediante <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> y <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.  
  
#### Para crear una actividad personalizada que herede de NativeActivity  
  
1.  Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Seleccione **Archivo**, **Nuevo** y, a continuación, **Proyecto**.Seleccione **Workflow 4.0** debajo de **Visual C\#** en la ventana **Tipos de proyecto** y seleccione el nodo **v2010**.Seleccione **Biblioteca de actividad** en la ventana **Plantillas**.Dé al nuevo proyecto el nombre "HelloActivity".  
  
3.  Haga clic con el botón secundario en Activity.xaml en el proyecto HelloActivity y seleccione **Eliminar**.  
  
4.  Haga clic con el botón secundario en el proyecto HelloActivity y seleccione **Agregar** y después **Clase**.Dé a la nueva clase el nombre "HelloActivity.cs".  
  
5.  En el archivo HelloActivity.cs, agregue las siguientes directivas `using`.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  Haga que la nueva clase herede de <xref:System.Activities.NativeActivity> al agregar una clase base a la declaración de clase.  
  
    ```csharp  
    class HelloActivity : NativeActivity  
    ```  
  
7.  Agregue funcionalidad a la clase agregando un método <xref:System.Activities.NativeActivity.Execute%2A>.  
  
    ```csharp  
    protected override void Execute(NativeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  Invalide el método <xref:System.Activities.NativeActivity.CacheMetadata%2A> y llame al método Add adecuado para que el runtime del flujo de trabajo conozca las variables, los argumentos, los elementos secundarios y los delegados personalizados de la actividad.Para obtener más información, vea la clase <xref:System.Activities.NativeActivityMetadata>.  
  
9. Utilice el objeto <xref:System.Activities.NativeActivityContext> para programar un marcador.Vea <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> para obtener detalles sobre cómo crear, programar y reanudar un marcador.  
  
    ```  
    protected override void Execute(NativeActivityContext context)  
        {  
            // Create a Bookmark and wait for it to be resumed.  
            context.CreateBookmark(BookmarkName.Get(context),   
                new BookmarkCallback(OnResumeBookmark));  
        }  
  
    ```