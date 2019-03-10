---
title: Procedimiento Hospedar varias versiones de un flujo de trabajo paralelo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 6cb552752c1693ce8008eb57e0703882b7281830
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705992"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a>Filtrar Hospedar varias versiones de un flujo de trabajo paralelo
`WorkflowIdentity` proporciona una manera para que los desarrolladores de aplicaciones de flujo de trabajo asocien un nombre y una versión con una definición de flujo de trabajo, y para que esta información se asocie a una instancia de flujo de trabajo persistente. Los desarrolladores de aplicaciones de flujo de trabajo pueden usar esta información de identidad para habilitar escenarios como la ejecución en paralelo de varias versiones de una definición de flujo de trabajo; además esta información proporciona la piedra angular para otras funcionalidades como la actualización dinámica. Este paso del tutorial demuestra cómo usar `WorkflowIdentity` para hospedar varias versiones de un flujo de trabajo simultáneamente.

> [!NOTE]
>  Para descargar una versión completada o ver un tutorial en vídeo del tutorial, vea [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
## <a name="in-this-topic"></a>En este tema  
 En este paso del tutorial, las actividades de `WriteLine` en el flujo de trabajo se modifican para proporcionar información adicional y se agrega una nueva actividad `WriteLine`. Una copia del ensamblado original de flujo de trabajo queda almacenada y la aplicación de host se actualiza de tal modo que puede ejecutar tanto el flujo de trabajo original como el actualizado al mismo tiempo.  
  
-   [Para realizar una copia del proyecto NumberGuessWorkflowActivities](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [Para actualizar los flujos de trabajo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [Para actualizar el flujo de trabajo StateMachine](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [Para actualizar el flujo de trabajo de diagrama de flujo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [Para actualizar el flujo de trabajo secuencial](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [Para actualizar WorkflowVersionMap para incluir las versiones anteriores del flujo de trabajo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [Para compilar y ejecutar la aplicación](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  Antes de seguir los pasos de este tema, ejecute la aplicación, inicie varios flujos de trabajo de cada tipo y realice uno o dos intentos con cada uno. Estos flujos de trabajo persistentes se usan en este paso y el paso siguiente, [Cómo: Actualizar la definición de una instancia de flujo de trabajo de ejecución](how-to-update-the-definition-of-a-running-workflow-instance.md).

> [!NOTE]
>  Cada paso del tutorial de introducción depende de los pasos anteriores. Si no completó los pasos anteriores, puede descargar una versión completada del tutorial de [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="BKMK_BackupCopy"></a> Para realizar una copia del proyecto NumberGuessWorkflowActivities  
  
1.  Abra el **WF45GettingStartedTutorial** solución en Visual Studio 2012, si no está abierto.  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Cerrar la **WF45GettingStartedTutorial** solución.  
  
4.  Abra el Explorador de Windows y navegue hasta la carpeta donde se encuentran el archivo de solución del tutorial y las carpetas de proyecto.  
  
5.  Cree una carpeta nueva denominada **PreviousVersions** en la misma carpeta que **NumberGuessWorkflowHost** y **NumberGuessWorkflowActivities**. Esta carpeta se usa para guardar los ensamblados que contienen las distintas versiones de los flujos de trabajo usados en los pasos de tutorial posteriores.  
  
6.  Navegue hasta la **NumberGuessWorkflowActivities\bin\debug** carpeta (o **bin\release** según la configuración del proyecto). Copia **NumberGuessWorkflowActivities.dll** y péguelo en el **PreviousVersions** carpeta.  
  
7.  Cambiar el nombre de **NumberGuessWorkflowActivities.dll** en el **PreviousVersions** carpeta **NumberGuessWorkflowActivities_v1.dll**.  
  
    > [!NOTE]
    >  En los pasos de este tema se muestra una manera de administrar los ensamblados usados para contener varias versiones de los flujos de trabajo. También se pueden usar otros métodos, como el nombre seguro de los ensamblados y su registro en la memoria caché global de ensamblados.

8.  Cree una carpeta nueva denominada **NumberGuessWorkflowActivities_du** en la misma carpeta que **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**y la recién agregar **PreviousVersions** carpeta y copie todos los archivos y subcarpetas de la **NumberGuessWorkflowActivities** carpeta en el nuevo  **NumberGuessWorkflowActivities_du** carpeta. Esta copia de seguridad del proyecto para la versión inicial de las actividades se usa en [Cómo: Actualizar la definición de una instancia de flujo de trabajo de ejecución](how-to-update-the-definition-of-a-running-workflow-instance.md).

9. Vuelva a abrir el **WF45GettingStartedTutorial** solución en Visual Studio 2012.

### <a name="BKMK_UpdateWorkflows"></a> Para actualizar los flujos de trabajo
 En esta sección, se actualizan las definiciones de flujo de trabajo. Se actualizan las dos actividades de `WriteLine` que proporcionan informes sobre los intentos del usuario, y se agrega una nueva actividad `WriteLine` que proporciona información adicional sobre el juego una vez se ha adivinado el número.

#### <a name="BKMK_UpdateStateMachine"></a> Para actualizar el flujo de trabajo StateMachine

1.  En **el Explorador de soluciones**, en el **NumberGuessWorkflowActivities** del proyecto, haga doble clic en **StateMachineNumberGuessWorkflow.xaml**.

2.  Haga doble clic en el **Guess Incorrect** transición en la máquina de Estados.

3.  Actualice `Text` de `WriteLine` del extremo izquierdo en la actividad `If`.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4.  Actualice `Text` de `WriteLine` del extremo derecho en la actividad `If`.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5.  Volver a general el estado de vista de la máquina en el Diseñador de flujo de trabajo haciendo clic en **StateMachine** en la ruta de navegación que se muestran en la parte superior del Diseñador de flujo de trabajo.

6.  Haga doble clic en el **Guess Correct** transición en la máquina de Estados.

7.  Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **coloque la actividad Action aquí** etiqueta de la transición.

8.  Escriba la siguiente expresión en el cuadro de propiedad `Text`.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateFlowchart"></a> Para actualizar el flujo de trabajo de diagrama de flujo

1.  En **el Explorador de soluciones**, en el **NumberGuessWorkflowActivities** del proyecto, haga doble clic en **FlowchartNumberGuessWorkflow.xaml**.

2.  Actualice `Text` de la actividad `WriteLine` del extremo izquierdo.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3.  Actualice `Text` de la actividad `WriteLine` del extremo derecho.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4.  Arrastrar un **WriteLine** actividad desde el **primitivas** sección de la **cuadro de herramientas** y colóquela en el punto de colocación de la `True` acción de la propiedad topmost `FlowDecision` . La actividad `WriteLine` se agrega al diagrama de flujo y se vincula a la acción `True` de `FlowDecision`.

5.  Escriba la siguiente expresión en el cuadro de propiedad `Text`.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateSequential"></a> Para actualizar el flujo de trabajo secuencial

1.  En **el Explorador de soluciones**, en el **NumberGuessWorkflowActivities** del proyecto, haga doble clic en **SequentialNumberGuessWorkflow.xaml**.

2.  Actualice `Text` de `WriteLine` del extremo izquierdo en la actividad `If`.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3.  Actualice `Text` de la actividad `WriteLine` del extremo derecho en la actividad `If`.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4.  Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela después de la **DoWhile** actividad para que el  **WriteLine** es la actividad final en la raíz `Sequence` actividad.

5.  Escriba la siguiente expresión en el cuadro de propiedad `Text`.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="BKMK_UpdateWorkflowVersionMap"></a> Para actualizar WorkflowVersionMap para incluir las versiones anteriores del flujo de trabajo

1.  Haga doble clic en **WorkflowVersionMap.cs** (o **WorkflowVersionMap.vb**) en el **NumberGuessWorkflowHost** proyecto para abrirlo.

2.  Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3.  Agregue tres nuevas identidades de flujo de trabajo justo debajo de las tres declaraciones de identidad de flujo de trabajo existentes. Estas nuevas identidades de flujo de trabajo de `v1` se usarán para proporcionar la definición de flujo de trabajo correcta a los flujos de trabajo iniciados antes de que se realizaran las actualizaciones.

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 Identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity
    ```

    ```csharp
    // Current version identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity;
    static public WorkflowIdentity FlowchartNumberGuessIdentity;
    static public WorkflowIdentity SequentialNumberGuessIdentity;

    // v1 identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;
    ```

4.  En el constructor `WorkflowVersionMap`, actualice la propiedad `Version` de las tres identidades de flujo de trabajo actuales a `2.0.0.0`.

    ```vb
    'Add the current workflow version identities.
    StateMachineNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    SequentialNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
    ```

    ```csharp
    // Add the current workflow version identities.
    StateMachineNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    SequentialNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
    ```

     El código que agrega las versiones actuales de los flujos de trabajo al diccionario usa las versiones actuales a las que se hace referencia en el proyecto, por lo que no es necesario actualizar el código que inicializa las definiciones de flujo de trabajo.

5.  Agregue el código siguiente en el constructor justo después del código que agrega las versiones actuales al diccionario.

    ```vb
    'Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }
    ```

    ```csharp
    // Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };
    ```

     Estas identidades de flujo de trabajo están asociadas a las versiones iniciales de las definiciones de flujo de trabajo correspondientes.

6.  A continuación, cargue el ensamblado que contiene la versión inicial de las definiciones de flujo de trabajo, y cree y agregue las definiciones de flujo de trabajo al diccionario.

    ```vb
    'Add the previous version workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v1 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Add the previous version workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v1 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     En el ejemplo siguiente se muestra la lista completa para la clase `WorkflowVersionMap` actualizada.

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 Identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())

            'Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            'Add the previous version workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v1 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        // v1 identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());

            // Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            // Add the previous version workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v1 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
        }
    }
    ```

### <a name="BKMK_BuildAndRun"></a> Para compilar y ejecutar la aplicación

1.  Presione CTRL+MAYÚS+B para compilar la aplicación y, a continuación, CTRL+F5 para iniciarla.

2.  Haga clic en iniciar un nuevo flujo de trabajo **nuevo juego**. La versión del flujo de trabajo se muestra debajo de la ventana de estado y refleja la versión actualizada del `WorkflowIdentity` asociado. Anote el valor de `InstanceId` para poder ver el archivo de seguimiento del flujo de trabajo cuando se complete y, a continuación, escriba números hasta que se termine el juego. Observe cómo el intento del usuario aparece en la información que se muestra en la ventana de estado en función de las actualizaciones de las actividades `WriteLine`.

 **Escriba un número entre 1 y 10**  
**5 es demasiado alto.**  
**Escriba un número entre 1 y 10**  
**3 es demasiado alto.**  
**Escriba un número entre 1 y 10**  
**1 es demasiado bajo.**  
**Escriba un número entre 1 y 10**  
**Enhorabuena, acertó el número en 4 intentos.**  

    > [!NOTE]
    >  Se muestra el texto actualizado de las actividades `WriteLine`, pero no se muestra el resultado de la actividad final `WriteLine` que se agregó en este tema. Esto se debe a que el controlador `PersistableIdle` actualiza la ventana de estado. Debido a que el flujo de trabajo se completa y no queda inactivo después de la actividad final, no se llama al controlador `PersistableIdle`. Sin embargo, el controlador `Completed` muestra un mensaje similar en la ventana de estado. Si se desea, se puede agregar un código al controlador `Completed` para extraer el texto de `StringWriter` y mostrarlo en la ventana de estado.

3.  Abra el Explorador de Windows y navegue hasta la **NumberGuessWorkflowHost\bin\debug** carpeta (o **bin\release** según la configuración del proyecto) y abra el archivo de seguimiento con el Bloc de notas que corresponde en el flujo de trabajo completado. Si no ha realizado una nota de la `InstanceId`, puede identificar el archivo correcto de seguimiento utilizando el **fecha de modificación** información en el Explorador de Windows.

 **Escriba un número entre 1 y 10**
**5 es demasiado alto.** 
 **Escriba un número entre 1 y 10**
**3 es demasiado alto.** 
 **Escriba un número entre 1 y 10**
**1 es demasiado bajo.** 
 **Escriba un número entre 1 y 10**
**2 es correcto. Lo acertó en 4 intentos.**      La salida de `WriteLine` actualizada se encuentra en el archivo de seguimiento, incluida la salida de `WriteLine` que se agregó en este tema.

4.  Vuelva a la aplicación para adivinar números y seleccione uno de los flujos de trabajo iniciado antes de que se realizaran las actualizaciones. Puede identificar la versión del flujo de trabajo seleccionado actualmente si examina la información de versión que aparece debajo de la ventana de estado. Escriba los números y observe que las actualizaciones de estado coinciden con el resultado de la actividad `WriteLine` de la versión anterior y no incluyen el intento del usuario. Esto se debe a que estos flujos de trabajo usan la definición de flujo de trabajo anterior que no tiene las actualizaciones `WriteLine`.

     En el paso siguiente, [Cómo: Actualizar la definición de una instancia de flujo de trabajo ejecuta](how-to-update-the-definition-of-a-running-workflow-instance.md), la ejecución `v1` las instancias de flujo de trabajo se actualizan para que contengan la nueva funcionalidad como la `v2` instancias.
