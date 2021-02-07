---
description: 'Más información sobre: creación de actividades de flujo de trabajo mediante la clase CodeActivity'
title: Crear actividad de flujo de trabajo mediante la clase CodeActivity
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 393b6c586a88e876484f6888441d5bb82b4c0dad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754919"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>Crear actividad de flujo de trabajo mediante la clase CodeActivity

Las actividades creadas al heredar de <xref:System.Activities.CodeActivity> pueden implementar el comportamiento imperativo básico al invalidar el método <xref:System.Activities.CodeActivity.Execute%2A>.

## <a name="using-codeactivitycontext"></a>Usar CodeActivityContext

 Se puede tener acceso a las características del tiempo de ejecución del flujo de trabajo desde dentro del método <xref:System.Activities.CodeActivity.Execute%2A> usando los miembros del parámetro `context`, del tipo <xref:System.Activities.CodeActivityContext>. Las características disponibles mediante <xref:System.Activities.CodeActivityContext> incluyen lo siguiente:

- Obtener y establecer los valores de variables y argumentos.

- Características de seguimiento personalizadas con <xref:System.Activities.CodeActivityContext.Track%2A>.

- Obtenga acceso a las propiedades de ejecución de la actividad con <xref:System.Activities.CodeActivityContext.GetProperty%2A>.

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>Para crear una actividad personalizada que herede de CodeActivity

1. Abra Visual Studio 2010.

2. Seleccione **archivo**, **nuevo** y **proyecto**. Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** . Seleccione **biblioteca de actividades** en la ventana **plantillas** . Dé al nuevo proyecto el nombre "HelloActivity".

3. Haga clic con el botón secundario en Activity1. XAML en el proyecto HelloActivity y seleccione **eliminar**.

4. Haga clic con el botón derecho en el proyecto HelloActivity, seleccione **Agregar** y, a continuación, **clase**. Dé a la nueva clase el nombre "HelloActivity.cs".

5. En el archivo HelloActivity.cs, agregue las siguientes directivas `using`.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. Haga que la nueva clase herede de <xref:System.Activities.CodeActivity> al agregar una clase base a la declaración de clase.

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. Agregue la funcionalidad a la clase agregando un método <xref:System.Activities.CodeActivity.Execute%2A>.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. Use <xref:System.Activities.CodeActivityContext> para crear un registro de seguimiento.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
