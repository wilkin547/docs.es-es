---
title: Clase base NativeActivity
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: d875f62dacadb2baf6b5d7e93ddb2933aed9cdb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274964"
---
# <a name="nativeactivity-base-class"></a>Clase base NativeActivity

<xref:System.Activities.NativeActivity> es una clase abstracta con un constructor protegido. Al igual que ocurre con <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> se usa para escribir el comportamiento imperativo al implementar un método <xref:System.Activities.NativeActivity.Execute%2A>. A diferencia de <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> tiene acceso a todas las características expuestas del tiempo de ejecución del flujo de trabajo a través del objeto <xref:System.Activities.NativeActivityContext> pasado al método <xref:System.Activities.NativeActivity.Execute%2A>.

## <a name="using-nativeactivitycontext"></a>Usar NativeActivityContext

 Se puede tener acceso a las características del tiempo de ejecución del flujo de trabajo desde dentro del método <xref:System.Activities.NativeActivity.Execute%2A> usando los miembros del parámetro `context`, del tipo <xref:System.Activities.NativeActivityContext>. Las características disponibles mediante <xref:System.Activities.NativeActivityContext> incluyen lo siguiente:

- Obtener y definir los argumentos y variables.

- Programar las actividades secundarias con <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>

- Anular la ejecución de la actividad con <xref:System.Activities.NativeActivityContext.Abort%2A>.

- Cancelar la ejecución secundaria con <xref:System.Activities.NativeActivityContext.CancelChild%2A> y <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.

- Obtener acceso a los marcadores de actividad usando dichos métodos como <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> y <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.

- Características de seguimiento personalizadas con <xref:System.Activities.CodeActivityContext.Track%2A>.

- Acceso a las propiedades de ejecución de la actividad y a las propiedades de los valores con <xref:System.Activities.CodeActivityContext.GetProperty%2A> y <xref:System.Activities.NativeActivityContext.GetValue%2A>.

- Programar las acciones de la actividad y las funciones mediante <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> y <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a>Para crear una actividad personalizada que herede de NativeActivity

1. OpenVisual Studio 2010.

2. Seleccione **archivo**, **nuevo** y **proyecto**. Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** . Seleccione **biblioteca de actividades** en la ventana **plantillas** . Dé al nuevo proyecto el nombre "HelloActivity".

3. Haga clic con el botón secundario en Activity1. XAML en el proyecto HelloActivity y seleccione **eliminar**.

4. Haga clic con el botón derecho en el proyecto HelloActivity, seleccione **Agregar** y, a continuación, **clase**. Dé a la nueva clase el nombre "HelloActivity.cs".

5. En el archivo HelloActivity.cs, agregue las siguientes directivas `using`.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. Haga que la nueva clase herede de <xref:System.Activities.NativeActivity> al agregar una clase base a la declaración de clase.

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. Agregue la funcionalidad a la clase agregando un método <xref:System.Activities.NativeActivity.Execute%2A>.

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. Invalide el método <xref:System.Activities.NativeActivity.CacheMetadata%2A> y llame al método Add adecuado para que el tiempo de ejecución del flujo de trabajo conozca las variables, los argumentos, los elementos secundarios y los delegados personalizados de la actividad. Para obtener más información, vea la clase <xref:System.Activities.NativeActivityMetadata>.

9. Utilice el objeto <xref:System.Activities.NativeActivityContext> para programar un marcador. Vea <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> para obtener detalles sobre cómo crear, programar y reanudar un marcador.

    ```csharp
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
