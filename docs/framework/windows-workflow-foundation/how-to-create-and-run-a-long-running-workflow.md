---
title: "How to: Create and Run a Long Running Workflow | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# How to: Create and Run a Long Running Workflow
Una de las características principales de [!INCLUDE[wf](../../../includes/wf-md.md)] es la capacidad del tiempo de ejecución de conservar y descargar flujos de trabajo inactivos en una base de datos. Los pasos de [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) muestra los aspectos básicos de hospedaje de flujo de trabajo mediante una aplicación de consola. Se mostraron ejemplos de cómo iniciar flujos de trabajo, de los controladores de ciclo de vida de los flujos de trabajo y de los marcadores de reanudación. Para demostrar la persistencia del flujo de trabajo con efectividad, es necesario un host de flujo de trabajo más complejo que admita el inicio y la reanudación de varias instancias de flujo de trabajo. En este paso del tutorial se muestra cómo crear una aplicación host de Windows Forms que admita iniciar y reanudar varias instancias de flujo de trabajo o la persistencia del flujo de trabajo, y que proporcione una base para características avanzadas como el seguimiento y el control de versiones mostrado en los siguientes pasos del tutorial.  
  
> [!NOTE]
>  Este paso del tutorial y los pasos siguientes utilizan los tres tipos de flujo de trabajo de [Cómo: crear un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow.md). Si no completó los tres tipos puede descargar una versión completa de los pasos de [Windows Workflow Foundation (WF45): Tutorial de introducción](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
> [!NOTE]
>  Para descargar una versión completada o ver un tutorial en vídeo del tutorial, consulte [Windows Workflow Foundation (WF45): Tutorial de introducción](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
## <a name="in-this-topic"></a>En este tema  
  
-   [Para crear la base de datos de persistencia](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_CreatePersistenceDatabase)  
  
-   [Para agregar la referencia a los ensamblados de DurableInstancing](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_AddReference)  
  
-   [Para crear el formulario de host de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_CreateForm)  
  
-   [Para agregar las propiedades y métodos auxiliares del formulario](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods)  
  
-   [Para configurar el almacén de instancias, controladores de ciclo de vida de flujo de trabajo y extensiones](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_ConfigureWorkflowApplication)  
  
-   [Para habilitar el inicio y reanudación de varios tipos de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_WorkflowVersionMap)  
  
-   [Para iniciar un nuevo flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_StartWorkflow)  
  
-   [Para reanudar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_ResumeWorkflow)  
  
-   [Para finalizar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_TerminateWorkflow)  
  
-   [Para compilar y ejecutar la aplicación](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_BuildAndRun)  
  
###  <a name="a-namebkmkcreatepersistencedatabasea-to-create-the-persistence-database"></a><a name="BKMK_CreatePersistenceDatabase"></a> Para crear la base de datos de persistencia  
  
1.  Abra SQL Server Management Studio y conéctese al servidor local, por ejemplo **. \SQLEXPRESS**. Haga clic en el **bases de datos** nodo en el servidor local y seleccione **nueva base de datos**. El nombre de la nueva base de datos **WF45GettingStartedTutorial**, acepte los demás valores y seleccione **Aceptar**.  
  
    > [!NOTE]
    >  Asegúrese de que tiene **Create Database** permiso en el servidor local antes de crear la base de datos.  
  
2.  Elija **abiertos**, **archivo** desde el **archivo** menú. Busque la siguiente carpeta: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`  
  
     Seleccione los dos archivos siguientes y haga clic en **Abrir**.  
  
    -   SqlWorkflowInstanceStoreLogic.sql  
  
    -   SqlWorkflowInstanceStoreSchema.sql  
  
3.  Elija **SqlWorkflowInstanceStoreSchema.sql** desde el **ventana** menú. Asegúrese de que **WF45GettingStartedTutorial** está seleccionado en el **bases de datos disponibles** desplegable y elija **Execute** desde el **consulta** menú.  
  
4.  Elija **SqlWorkflowInstanceStoreLogic.sql** desde el **ventana** menú. Asegúrese de que **WF45GettingStartedTutorial** está seleccionado en el **bases de datos disponibles** desplegable y elija **Execute** desde el **consulta** menú.  
  
    > [!WARNING]
    >  Es importante realizar los dos pasos anteriores en el orden correcto. Si las consultas se ejecutan de manera desordenada, aparecerán errores y la base de datos de persistencia no se configurará correctamente.  
  
###  <a name="a-namebkmkaddreferencea-to-add-the-reference-to-the-durableinstancing-assemblies"></a><a name="BKMK_AddReference"></a> Para agregar la referencia a los ensamblados de DurableInstancing  
  
1.  Haga clic en **NumberGuessWorkflowHost** en **el Explorador de soluciones** y seleccione **Agregar referencia**.  
  
2.  Seleccione **ensamblados** desde el **Agregar referencia** lista y escriba `DurableInstancing` en la **buscar ensamblados** cuadro. Esto filtrará los ensamblados y simplificará la selección de las referencias deseadas.  
  
3.  Active la casilla situada junto a **System.Activities.DurableInstancing** y **System.Runtime.DurableInstancing** desde el **resultados de la búsqueda** y haga clic en **Aceptar**.  
  
###  <a name="a-namebkmkcreateforma-to-create-the-workflow-host-form"></a><a name="BKMK_CreateForm"></a> Para crear el formulario de host de flujo de trabajo  
  
> [!NOTE]
>  Los pasos de este procedimiento describen cómo agregar y configurar el formulario manualmente. Si lo desea, puede descargar los archivos de solución para el tutorial y agregar el formulario completo al proyecto. Para descargar los archivos del tutorial, consulte [Windows Workflow Foundation (WF45): Tutorial de introducción](http://go.microsoft.com/fwlink/?LinkID=248976). Una vez que se descargan los archivos, haga clic en **NumberGuessWorkflowHost** y elija **Agregar referencia**. Agregue una referencia a **System.Windows.Forms** y **System.Drawing**. Estas referencias se agregan automáticamente si agrega un nuevo formulario desde el **Agregar**, **nuevo elemento** menú, pero deben agregarse manualmente al importar un formulario. Una vez que se agregan las referencias, haga clic en **NumberGuessWorkflowHost** en **el Explorador de soluciones** y elija **Agregar**, **elemento existente**. Vaya a la `Form` carpeta en los archivos de proyecto, seleccione **WorkflowHostForm.cs** (o **WorkflowHostForm.vb**) y haga clic en **Agregar**. Si elige importar el formulario, puede saltar a la siguiente sección, [para agregar las propiedades y métodos auxiliares del formulario](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods).  
  
1.  Haga clic en **NumberGuessWorkflowHost** en **el Explorador de soluciones** y elija **Agregar**, **nuevo elemento**.  
  
2.  En el **instalado** plantillas, elija **Windows Form**, tipo `WorkflowHostForm` en el **nombre** cuadro y haga clic en **Agregar**.  
  
3.  Configure las siguientes propiedades en el formulario.  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |FormBorderStyle|FixedSingle|  
    |MaximizeBox|False|  
    |Tamaño|400, 420|  
  
4.  Agregue los siguientes controles al formulario en el orden especificado y configure las propiedades como dirigidas.  
  
    |Control|Propiedad: valor|  
    |-------------|---------------------|  
    |**Botón**|Nombre: NewGame<br /><br /> Ubicación: 13, 13<br /><br /> Tamaño: 75, 23<br /><br /> Texto: Nuevo juego|  
    |**Etiqueta**|Ubicación: 94, 18<br /><br /> Texto: Adivinar un número del 1 al|  
    |**Cuadro combinado**|Nombre: NumberRange<br /><br /> DropDownStyle: DropDownList<br /><br /> Elementos: los 10, 100, 1000<br /><br /> Ubicación: 228, 12<br /><br /> Tamaño: 143, 21|  
    |**Etiqueta**|Ubicación: 13, 43<br /><br /> Texto: Tipo de flujo de trabajo|  
    |**Cuadro combinado**|Nombre: WorkflowType<br /><br /> DropDownStyle: DropDownList<br /><br /> Elementos: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow<br /><br /> Ubicación: 94, 40<br /><br /> Tamaño: 277, 21|  
    |**Etiqueta**|Nombre: WorkflowVersion<br /><br /> Ubicación: 13, 362<br /><br /> Texto: Versión de flujo de trabajo|  
    |**GroupBox**|Ubicación: 13, 67<br /><br /> Tamaño: 358, 287<br /><br /> Texto: juego|  
  
    > [!NOTE]
    >  Al agregar los siguientes controles, colocarlos en el cuadro de grupo.  
  
    |Control|Propiedad: valor|  
    |-------------|---------------------|  
    |**Etiqueta**|Ubicación: 7, 20<br /><br /> Texto: Id. de instancia de flujo de trabajo|  
    |**Cuadro combinado**|Nombre: InstanceId<br /><br /> DropDownStyle: DropDownList<br /><br /> Ubicación: 121, 17<br /><br /> Tamaño: 227, 21|  
    |**Etiqueta**|Ubicación: 7, 47<br /><br /> Texto: adivinar|  
    |**Cuadro de texto**|Nombre: adivinar<br /><br /> Ubicación: 50, 44<br /><br /> Tamaño: 65, 20|  
    |**Botón**|Nombre: EnterGuess<br /><br /> Ubicación: 121, 42<br /><br /> Tamaño: 75, 23<br /><br /> Texto: Escriba intento|  
    |**Botón**|Nombre: QuitGame<br /><br /> Ubicación: 274, 42<br /><br /> Tamaño: 75, 23<br /><br /> Texto: salir|  
    |**Cuadro de texto**|Nombre: WorkflowStatus<br /><br /> Ubicación: 10, 73<br /><br /> Multiline: True<br /><br /> ReadOnly: True<br /><br /> Barras de desplazamiento: Vertical<br /><br /> Tamaño: 338, 208|  
  
5.  Establecer el **AcceptButton** propiedad del formulario para **EnterGuess**.  
  
 En el siguiente ejemplo se muestra el formulario completado.  
  
 ![Formulario de host de flujo de trabajo del tutorial de introducción de WF45](../../../docs/framework/windows-workflow-foundation//media/wf45gettingstartedtutorialworkflowhostform.png "WF45GettingStartedTutorialWorkflowHostForm")  
  
###  <a name="a-namebkmkaddhelpermethodsa-to-add-the-properties-and-helper-methods-of-the-form"></a><a name="BKMK_AddHelperMethods"></a> Para agregar las propiedades y métodos auxiliares del formulario  
 Los pasos de esta sección agregan propiedades y métodos auxiliares a la clase de formulario que configuran la interfaz de usuario del formulario para que se admita la ejecución y la reanudación de flujos de trabajo de acierto de números.  
  
1.  Haga clic en **WorkflowHostForm** en **el Explorador de soluciones** y elija **Ver código**.  
  
2.  Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).  
  
    ```vb  
    Imports System.Windows.Forms  
    Imports System.Activities.DurableInstancing  
    Imports System.Activities  
    Imports System.Data.SqlClient  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    using System.Activities.DurableInstancing;  
    using System.Activities;  
    using System.Data.SqlClient;  
    using System.IO;  
    ```  
  
3.  Agregue las siguientes declaraciones de miembro para el **WorkflowHostForm** clase.  
  
    ```vb  
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"  
    Dim store As SqlWorkflowInstanceStore  
    Dim WorkflowStarting As Boolean  
    ```  
  
    ```csharp  
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";  
    SqlWorkflowInstanceStore store;  
    bool WorkflowStarting;  
    ```  
  
    > [!NOTE]
    >  Si la cadena de conexión es diferente, actualice `connectionString` para consultar la base de datos.  
  
4.  Agregue una propiedad `WorkflowInstanceId` a la clase `WorkflowFormHost`.  
  
    ```vb  
    Public ReadOnly Property WorkflowInstanceId() As Guid  
        Get  
            If InstanceId.SelectedIndex = -1 Then  
                Return Guid.Empty  
            Else  
                Return New Guid(InstanceId.SelectedItem.ToString())  
            End If  
        End Get  
    End Property  
    ```  
  
    ```csharp  
    public Guid WorkflowInstanceId  
    {  
        get  
        {  
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;  
        }  
    }  
    ```  
  
     El `InstanceId` cuadro combinado muestra una lista de identificadores de instancia de flujo de trabajo persistentes y `WorkflowInstanceId` propiedad devuelve el flujo de trabajo seleccionado actualmente.  
  
5.  Agregue un controlador para el evento del formulario `Load`. Para agregar el controlador, cambie a **vista Diseño** para el formulario, haga clic en el **eventos** situado en la parte superior de la **propiedades** ventana y haga doble clic en **carga**.  
  
    ```vb  
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load  
  
    End Sub  
    ```  
  
    ```csharp  
    private void WorkflowHostForm_Load(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
6.  Agregue el código siguiente a `WorkflowHostForm_Load`.  
  
    ```vb  
    'Initialize the store and configure it so that it can be used for  
    'multiple WorkflowApplication instances.  
    store = New SqlWorkflowInstanceStore(connectionString)  
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)  
  
    'Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0  
    WorkflowType.SelectedIndex = 0  
  
    ListPersistedWorkflows()  
    ```  
  
    ```csharp  
    // Initialize the store and configure it so that it can be used for  
    // multiple WorkflowApplication instances.  
    store = new SqlWorkflowInstanceStore(connectionString);  
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);  
  
    // Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0;  
    WorkflowType.SelectedIndex = 0;  
  
    ListPersistedWorkflows();  
    ```  
  
     Cuando el formulario se carga, se configura `SqlWorkflowInstanceStore`, los intervalos y los cuadros combinados de tipo de flujo de trabajo se establecen en valores predeterminados y las instancias de flujo de trabajo persistentes se agregan al cuadro combinado `InstanceId`.  
  
7.  Agregue un controlador `SelectedIndexChanged` para `InstanceId`. Para agregar el controlador, cambie a **vista Diseño** para el formulario, seleccione la `InstanceId` cuadro combinado, haga clic en el **eventos** situado en la parte superior de la **propiedades** ventana y haga doble clic en **SelectedIndexChanged**.  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
8.  Agregue el código siguiente a `InstanceId_SelectedIndexChanged`. Siempre que el usuario selecciona un flujo de trabajo mediante el cuadro combinado, este controlador actualiza la ventana de estado.  
  
    ```vb  
    If InstanceId.SelectedIndex = -1 Then  
        Return  
    End If  
  
    'Clear the status window.  
    WorkflowStatus.Clear()  
  
    'Get the workflow version and display it.  
    'If the workflow is just starting then this info will not  
    'be available in the persistence store so do not try and retrieve it.  
    If Not WorkflowStarting Then  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        WorkflowVersion.Text = _  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
        'Unload the instance.  
        instance.Abandon()  
    End If  
    ```  
  
    ```csharp  
    if (InstanceId.SelectedIndex == -1)  
    {  
        return;  
    }  
  
    // Clear the status window.  
    WorkflowStatus.Clear();  
  
    // Get the workflow version and display it.  
    // If the workflow is just starting then this info will not  
    // be available in the persistence store so do not try and retrieve it.  
    if (!WorkflowStarting)  
    {  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
        WorkflowVersion.Text =  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
        // Unload the instance.  
        instance.Abandon();  
    }  
    ```  
  
9. Agregue el siguiente método `ListPersistedWorkflows` a la clase de formulario.  
  
    ```vb  
    Private Sub ListPersistedWorkflows()  
        Using localCon As New SqlConnection(connectionString)  
            Dim localCmd As String = _  
                "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]"  
  
            Dim cmd As SqlCommand = localCon.CreateCommand()  
            cmd.CommandText = localCmd  
            localCon.Open()  
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
  
                While (reader.Read())  
                    'Get the InstanceId of the persisted Workflow.  
                    Dim id As Guid = Guid.Parse(reader(0).ToString())  
                    InstanceId.Items.Add(id)  
                End While  
            End Using  
        End Using  
    End Sub  
    ```  
  
    ```csharp  
    using (SqlConnection localCon = new SqlConnection(connectionString))  
    {  
        string localCmd =  
            "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]";  
  
        SqlCommand cmd = localCon.CreateCommand();  
        cmd.CommandText = localCmd;  
        localCon.Open();  
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))  
        {  
            while (reader.Read())  
            {  
                // Get the InstanceId of the persisted Workflow  
                Guid id = Guid.Parse(reader[0].ToString());  
                InstanceId.Items.Add(id);  
            }  
        }  
    }  
    ```  
  
     `ListPersistedWorkflows` consulta el almacén de instancias con respecto a las instancias de flujo de trabajo persistentes y agrega los identificadores de instancia al cuadro combinado `cboInstanceId`.  
  
10. Agregue el siguiente método `UpdateStatus` y el delegado correspondiente a la clase de formulario. Este método actualiza la ventana de estado en el formulario con el estado del flujo de trabajo en funcionamiento.  
  
    ```vb  
    Private Delegate Sub UpdateStatusDelegate(msg As String)  
    Public Sub UpdateStatus(msg As String)  
        'We may be on a different thread so we need to  
        'make this call using BeginInvoke.  
        If InvokeRequired Then  
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)  
        Else  
            If Not msg.EndsWith(vbCrLf) Then  
                msg = msg & vbCrLf  
            End If  
  
            WorkflowStatus.AppendText(msg)  
  
            'Ensure that the newly added status is visible.  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length  
            WorkflowStatus.ScrollToCaret()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void UpdateStatusDelegate(string msg);  
    public void UpdateStatus(string msg)  
    {  
        // We may be on a different thread so we need to  
        // make this call using BeginInvoke.  
        if (InvokeRequired)  
        {  
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);  
        }  
        else  
        {  
            if (!msg.EndsWith("\r\n"))  
            {  
                msg += "\r\n";  
            }  
            WorkflowStatus.AppendText(msg);  
  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;  
            WorkflowStatus.ScrollToCaret();  
        }  
    }  
    ```  
  
11. Agregue el siguiente método `GameOver` y el delegado correspondiente a la clase de formulario. Cuando finaliza un flujo de trabajo, este método actualiza el interfaz de Usuario del formulario quitando el identificador de instancia de flujo de trabajo completado de la **InstanceId** cuadro combinado.  
  
    ```vb  
    Private Delegate Sub GameOverDelegate()  
    Private Sub GameOver()  
        If InvokeRequired Then  
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))  
        Else  
            'Remove this instance from the InstanceId combo box.  
            InstanceId.Items.Remove(InstanceId.SelectedItem)  
            InstanceId.SelectedIndex = -1  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void GameOverDelegate();  
    private void GameOver()  
    {  
        if (InvokeRequired)  
        {  
            BeginInvoke(new GameOverDelegate(GameOver));  
        }  
        else  
        {  
            // Remove this instance from the combo box  
            InstanceId.Items.Remove(InstanceId.SelectedItem);  
            InstanceId.SelectedIndex = -1;  
        }  
    }  
    ```  
  
###  <a name="a-namebkmkconfigureworkflowapplicationa-to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a><a name="BKMK_ConfigureWorkflowApplication"></a> Para configurar el almacén de instancias, controladores de ciclo de vida de flujo de trabajo y extensiones  
  
1.  Agregue un método `ConfigureWorkflowApplication` a la clase de formulario.  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {      
    }  
    ```  
  
     Este método configura `WorkflowApplication`, agrega las extensiones deseadas y agrega los controladores para los eventos de ciclo de vida de flujo de trabajo.  
  
2.  En `ConfigureWorkflowApplication`, especifique `SqlWorkflowInstanceStore` para la `WorkflowApplication`.  
  
    ```vb  
    'Configure the persistence store.  
    wfApp.InstanceStore = store  
    ```  
  
    ```csharp  
    // Configure the persistence store.  
    wfApp.InstanceStore = store;  
    ```  
  
3.  A continuación, cree una instancia `StringWriter` y agréguela a la colección `Extensions` de `WorkflowApplication`. Cuando un `StringWriter` se agrega a las extensiones, captura todos los `WriteLine` salida de la actividad. Cuando el flujo de trabajo se vuelve inactivo, el resultado de `WriteLine` puede extraerse desde `StringWriter` y mostrarse en el formulario.  
  
    ```vb  
    'Add a StringWriter to the extensions. This captures the output  
    'from the WriteLine activities so we can display it in the form.  
    Dim sw As New StringWriter()  
    wfApp.Extensions.Add(sw)  
    ```  
  
    ```csharp  
    // Add a StringWriter to the extensions. This captures the output  
    // from the WriteLine activities so we can display it in the form.  
    StringWriter sw = new StringWriter();  
    wfApp.Extensions.Add(sw);  
    ```  
  
4.  Agregue el controlador siguiente para el evento `Completed`. Cuando un flujo de trabajo se ha completado con éxito, el número de intentos que han sido necesarios para acertar el número se muestra en la ventana de estado. Si el flujo de trabajo finaliza, se muestra la información de excepción que ha provocado la finalización. Al final del controlador se llama al método `GameOver`, que quita el flujo de trabajo completado de la lista de flujos de trabajo.  
  
    ```vb  
    wfApp.Completed = _  
        Sub(e As WorkflowApplicationCompletedEventArgs)  
            If e.CompletionState = ActivityInstanceState.Faulted Then  
                UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                    e.TerminationException.GetType().FullName, _  
                    e.TerminationException.Message))  
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                UpdateStatus("Workflow Canceled.")  
            Else  
                Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
            End If  
            GameOver()  
        End Sub  
    ```  
  
    ```csharp  
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
    {  
        if (e.CompletionState == ActivityInstanceState.Faulted)  
        {  
            UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                e.TerminationException.GetType().FullName,  
                e.TerminationException.Message));  
        }  
        else if (e.CompletionState == ActivityInstanceState.Canceled)  
        {  
            UpdateStatus("Workflow Canceled.");  
        }  
        else  
        {  
            int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
            UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
        }  
        GameOver();  
    };  
    ```  
  
5.  Agregue los siguientes controladores `Aborted` y `OnUnhandledException`. No se llama al método de `GameOver` desde el controlador `Aborted` porque cuando una instancia de flujo de trabajo se anula, no se finaliza y es posible reanudar la instancia posteriormente.  
  
    ```vb  
    wfApp.Aborted = _  
        Sub(e As WorkflowApplicationAbortedEventArgs)  
            UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                e.Reason.GetType().FullName, _  
                e.Reason.Message))  
        End Sub  
  
    wfApp.OnUnhandledException = _  
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
            UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                e.UnhandledException.GetType().FullName, _  
                e.UnhandledException.Message))  
            GameOver()  
            Return UnhandledExceptionAction.Terminate  
        End Function  
    ```  
  
    ```csharp  
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
    {  
        UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                e.Reason.GetType().FullName,  
                e.Reason.Message));  
    };  
  
    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
    {  
        UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                e.UnhandledException.GetType().FullName,  
                e.UnhandledException.Message));  
        GameOver();  
        return UnhandledExceptionAction.Terminate;  
    };  
    ```  
  
6.  Agregue el siguiente controlador `PersistableIdle`. Este controlador recupera la extensión `StringWriter` que se había agregado, extrae la salida de las actividades de `WriteLine` y la muestra en la ventana de estado.  
  
    ```vb  
    wfApp.PersistableIdle = _  
        Function(e As WorkflowApplicationIdleEventArgs)  
            'Send the current WriteLine outputs to the status window.  
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
            For Each writer In writers  
                UpdateStatus(writer.ToString())  
            Next  
            Return PersistableIdleAction.Unload  
        End Function  
    ```  
  
    ```csharp  
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
    {  
        // Send the current WriteLine outputs to the status window.  
        var writers = e.GetInstanceExtensions<StringWriter>();  
        foreach (var writer in writers)  
        {  
            UpdateStatus(writer.ToString());  
        }  
        return PersistableIdleAction.Unload;  
    };  
    ```  
  
     El <xref:System.Activities.PersistableIdleAction> enumeración tiene tres valores: <xref:System.Activities.PersistableIdleAction>, <xref:System.Activities.PersistableIdleAction>, y <xref:System.Activities.PersistableIdleAction>. <xref:System.Activities.PersistableIdleAction> causas para conservar el flujo de trabajo pero no hace que el flujo de trabajo descargar. <xref:System.Activities.PersistableIdleAction> hace que el flujo de trabajo persistente y se descargue.  
  
     El siguiente ejemplo es el método `ConfigureWorkflowApplication` completado.  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        wfApp.Completed = _  
            Sub(e As WorkflowApplicationCompletedEventArgs)  
                If e.CompletionState = ActivityInstanceState.Faulted Then  
                    UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                        e.TerminationException.GetType().FullName, _  
                        e.TerminationException.Message))  
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                    UpdateStatus("Workflow Canceled.")  
                Else  
                    Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                    UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
                End If  
                GameOver()  
            End Sub  
  
        wfApp.Aborted = _  
            Sub(e As WorkflowApplicationAbortedEventArgs)  
                UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                    e.Reason.GetType().FullName, _  
                    e.Reason.Message))  
            End Sub  
  
        wfApp.OnUnhandledException = _  
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
                UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                    e.UnhandledException.GetType().FullName, _  
                    e.UnhandledException.Message))  
                GameOver()  
                Return UnhandledExceptionAction.Terminate  
            End Function  
  
        wfApp.PersistableIdle = _  
            Function(e As WorkflowApplicationIdleEventArgs)  
                'Send the current WriteLine outputs to the status window.  
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
                For Each writer In writers  
                    UpdateStatus(writer.ToString())  
                Next  
                Return PersistableIdleAction.Unload  
            End Function  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
        {  
            if (e.CompletionState == ActivityInstanceState.Faulted)  
            {  
                UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                    e.TerminationException.GetType().FullName,  
                    e.TerminationException.Message));  
            }  
            else if (e.CompletionState == ActivityInstanceState.Canceled)  
            {  
                UpdateStatus("Workflow Canceled.");  
            }  
            else  
            {  
                int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
                UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
            }  
            GameOver();  
        };  
  
        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
        {  
            UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                    e.Reason.GetType().FullName,  
                    e.Reason.Message));  
        };  
  
        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                    e.UnhandledException.GetType().FullName,  
                    e.UnhandledException.Message));  
            GameOver();  
            return UnhandledExceptionAction.Terminate;  
        };  
  
        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
        {  
            // Send the current WriteLine outputs to the status window.  
            var writers = e.GetInstanceExtensions<StringWriter>();  
            foreach (var writer in writers)  
            {  
                UpdateStatus(writer.ToString());  
            }  
            return PersistableIdleAction.Unload;  
        };  
    }  
    ```  
  
###  <a name="a-namebkmkworkflowversionmapa-to-enable-starting-and-resuming-multiple-workflow-types"></a><a name="BKMK_WorkflowVersionMap"></a> Para habilitar el inicio y reanudación de varios tipos de flujo de trabajo  
 Para reanudar una instancia de flujo de trabajo, el host tiene que proporcionar la definición de flujo de trabajo. En este tutorial hay tres tipos de flujo de trabajo, y los pasos siguientes del tutorial presentan varias versiones de estos tipos. `WorkflowIdentity` proporciona una manera para que una aplicación de host asocie información de identificación con una instancia de flujo de trabajo persistente. Los pasos de esta sección muestran cómo crear una clase de utilidad para contribuir a la asignación de la identidad de flujo de trabajo desde una instancia de flujo de trabajo persistente a la definición de flujo de trabajo correspondiente. [!INCLUDE[crabout](../../../includes/crabout-md.md)]`WorkflowIdentity` y control de versiones, consulte [utilizando WorkflowIdentity y control de versiones](../../../docs/framework/windows-workflow-foundation//using-workflowidentity-and-versioning.md).  
  
1.  Haga clic en **NumberGuessWorkflowHost** en **el Explorador de soluciones** y elija **Agregar**, **clase**. Tipo de `WorkflowVersionMap` en el **nombre** y haga clic en **Agregar**.  
  
2.  Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` o `Imports`.  
  
    ```vb  
    Imports NumberGuessWorkflowActivities  
    Imports System.Activities  
    ```  
  
    ```csharp  
    using NumberGuessWorkflowActivities;  
    using System.Activities;  
    ```  
  
3.  Reemplace la declaración de clase `WorkflowVersionMap` por la declaración siguiente.  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
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
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
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
  
     `WorkflowVersionMap` contiene tres identidades de flujo de trabajo que se asignan a las tres definiciones de flujo de trabajo de este tutorial y se usan en las secciones siguientes al iniciar o al reanudar los flujos de trabajo.  
  
###  <a name="a-namebkmkstartworkflowa-to-start-a-new-workflow"></a><a name="BKMK_StartWorkflow"></a> Para iniciar un nuevo flujo de trabajo  
  
1.  Agregue un controlador `Click` para `NewGame`. Para agregar el controlador, cambie a **vista Diseño** para el formulario y haga doble clic en `NewGame`. Se agrega un controlador `NewGame_Click` y la vista cambia a vista de código para el formulario. Siempre que el usuario haga clic en este botón se inicia un nuevo flujo de trabajo.  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2.  Agregue el código siguiente al controlador de clic. Este código crea un diccionario de argumentos de entrada para el flujo de trabajo, por clave de nombre de argumento. Este diccionario tiene una entrada que contiene el intervalo del número generado aleatoriamente recuperado en el cuadro combinado del intervalo.  
  
    ```vb  
    Dim inputs As New Dictionary(Of String, Object)()  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
    ```  
  
    ```csharp  
    var inputs = new Dictionary<string, object>();  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
    ```  
  
3.  A continuación, agregue el siguiente código que inicia el flujo de trabajo. `WorkflowIdentity` y la definición de flujo de trabajo correspondiente al tipo de flujo de trabajo seleccionado se recuperan mediante la clase auxiliar `WorkflowVersionMap`. A continuación, se crea una nueva instancia de `WorkflowApplication` mediante la definición de flujo de trabajo, `WorkflowIdentity`, y el diccionario de argumentos de entrada.  
  
    ```vb  
    Dim identity As WorkflowIdentity = Nothing  
    Select Case WorkflowType.SelectedItem.ToString()  
        Case "SequentialNumberGuessWorkflow"  
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
        Case "StateMachineNumberGuessWorkflow"  
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
        Case "FlowchartNumberGuessWorkflow"  
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
    End Select  
  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
    Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
    ```  
  
    ```csharp  
    WorkflowIdentity identity = null;  
    switch (WorkflowType.SelectedItem.ToString())  
    {  
        case "SequentialNumberGuessWorkflow":  
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;  
            break;  
  
        case "StateMachineNumberGuessWorkflow":  
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;  
            break;  
  
        case "FlowchartNumberGuessWorkflow":  
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;  
            break;  
    };  
  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
    ```  
  
4.  A continuación, agregue el siguiente código que agrega el flujo de trabajo a la lista de flujos de trabajo y muestra la información de la versión del flujo de trabajo en el formulario.  
  
    ```vb  
    'Add the workflow to the list and display the version information.  
    WorkflowStarting = True  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
    WorkflowVersion.Text = identity.ToString()  
    WorkflowStarting = False  
    ```  
  
    ```csharp  
    // Add the workflow to the list and display the version information.  
    WorkflowStarting = true;  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
    WorkflowVersion.Text = identity.ToString();  
    WorkflowStarting = false;  
    ```  
  
5.  Llame a `ConfigureWorkflowApplication` para configurar el almacén de instancias, las extensiones y los controladores de ciclo de vida del flujo de trabajo para esta instancia `WorkflowApplication`.  
  
    ```vb  
    'Configure the instance store, extensions, and   
    'workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
    ```  
  
    ```csharp  
    // Configure the instance store, extensions, and   
    // workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp);  
    ```  
  
6.  Por último, llame a `Run`.  
  
    ```vb  
    'Start the workflow.  
    wfApp.Run()  
    ```  
  
    ```  
    // Start the workflow.  
    wfApp.Run();  
    ```  
  
     El siguiente ejemplo es el controlador `NewGame_Click` completado.  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
        'Start a new workflow.  
        Dim inputs As New Dictionary(Of String, Object)()  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
  
        Dim identity As WorkflowIdentity = Nothing  
        Select Case WorkflowType.SelectedItem.ToString()  
            Case "SequentialNumberGuessWorkflow"  
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
            Case "StateMachineNumberGuessWorkflow"  
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
            Case "FlowchartNumberGuessWorkflow"  
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
        End Select  
  
        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
        Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
  
        'Add the workflow to the list and display the version information.  
        WorkflowStarting = True  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
        WorkflowVersion.Text = identity.ToString()  
        WorkflowStarting = False  
  
        'Configure the instance store, extensions, and   
        'workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Start the workflow.  
        wfApp.Run()  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
        var inputs = new Dictionary<string, object>();  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
  
        WorkflowIdentity identity = null;  
        switch (WorkflowType.SelectedItem.ToString())  
        {  
            case "SequentialNumberGuessWorkflow":  
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;  
                break;  
  
            case "StateMachineNumberGuessWorkflow":  
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;  
                break;  
  
            case "FlowchartNumberGuessWorkflow":  
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;  
                break;  
        };  
  
        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
        WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
  
        // Add the workflow to the list and display the version information.  
        WorkflowStarting = true;  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
        WorkflowVersion.Text = identity.ToString();  
        WorkflowStarting = false;  
  
        // Configure the instance store, extensions, and   
        // workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Start the workflow.  
        wfApp.Run();  
    }  
    ```  
  
###  <a name="a-namebkmkresumeworkflowa-to-resume-a-workflow"></a><a name="BKMK_ResumeWorkflow"></a> Para reanudar un flujo de trabajo  
  
1.  Agregue un controlador `Click` para `EnterGuess`. Para agregar el controlador, cambie a **vista Diseño** para el formulario y haga doble clic en `EnterGuess`. Siempre que el usuario haga clic en este botón se reanudará un flujo de trabajo.  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2.  Agregue el código siguiente para asegurarse de que un flujo de trabajo está seleccionado en la lista de flujos de trabajo y de que el acierto del usuario es válido.  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim userGuess As Integer  
    If Not Int32.TryParse(Guess.Text, userGuess) Then  
        MessageBox.Show("Please enter an integer.")  
        Guess.SelectAll()  
        Guess.Focus()  
        Return  
    End If  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    int guess;  
    if (!Int32.TryParse(Guess.Text, out guess))  
    {  
        MessageBox.Show("Please enter an integer.");  
        Guess.SelectAll();  
        Guess.Focus();  
        return;  
    }  
    ```  
  
3.  A continuación, recupere `WorkflowApplicationInstance` de la instancia de flujo de trabajo persistente. `WorkflowApplicationInstance` representa una instancia de flujo de trabajo persistente que aún no se ha asociado a una definición de flujo de trabajo. `DefinitionIdentity` de `WorkflowApplicationInstance` contiene `WorkflowIdentity` de la instancia de flujo de trabajo persistente. En este tutorial, la clase de utilidad de `WorkflowVersionMap` se usa para asignar `WorkflowIdentity` a la definición de flujo de trabajo correcta. Una vez que se recupera la definición de flujo de trabajo, se crea `WorkflowApplication`, mediante la definición de flujo de trabajo correcta.  
  
    ```vb  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = _  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
    ```  
  
    ```csharp  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf =  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
    ```  
  
4.  Una vez que se ha creado `WorkflowApplication`, configure el almacén de instancias, los controladores de ciclo de vida del flujo de trabajo y las extensiones mediante una llamada a `ConfigureWorkflowApplication`. Deben llevarse a cabo estos pasos cada vez que se crea un nuevo objeto `WorkflowApplication` y antes de que se cargue la instancia de flujo de trabajo en `WorkflowApplication`. Cuando el flujo de trabajo ya está cargado, se reanuda con el intento del usuario.  
  
    ```vb  
    'Configure the extensions and lifecycle handlers.  
    'Do this before the instance is loaded. Once the instance is  
    'loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", userGuess)  
    ```  
  
    ```csharp  
    // Configure the extensions and lifecycle handlers.  
    // Do this before the instance is loaded. Once the instance is  
    // loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", guess);  
    ```  
  
5.  Finalmente, desactive el cuadro donde se indica el número y prepare el formulario para aceptar otro intento.  
  
    ```vb  
    'Clear the Guess textbox.  
    Guess.Clear()  
    Guess.Focus()  
    ```  
  
    ```csharp  
    // Clear the Guess textbox.  
    Guess.Clear();  
    Guess.Focus();  
    ```  
  
     El siguiente ejemplo es el controlador `EnterGuess_Click` completado.  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
        If WorkflowInstanceId = Guid.Empty Then  
            MessageBox.Show("Please select a workflow.")  
            Return  
        End If  
  
        Dim userGuess As Integer  
        If Not Int32.TryParse(Guess.Text, userGuess) Then  
            MessageBox.Show("Please enter an integer.")  
            Guess.SelectAll()  
            Guess.Focus()  
            Return  
        End If  
  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        'Use the persisted WorkflowIdentity to retrieve the correct workflow  
        'definition from the dictionary.  
        Dim wf As Activity = _  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
        'Associate the WorkflowApplication with the correct definition  
        Dim wfApp As WorkflowApplication = _  
            New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
        'Configure the extensions and lifecycle handlers.  
        'Do this before the instance is loaded. Once the instance is  
        'loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Load the workflow.  
        wfApp.Load(instance)  
  
        'Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", userGuess)  
  
        'Clear the Guess textbox.  
        Guess.Clear()  
        Guess.Focus()  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
        if (WorkflowInstanceId == Guid.Empty)  
        {  
            MessageBox.Show("Please select a workflow.");  
            return;  
        }  
  
        int guess;  
        if (!Int32.TryParse(Guess.Text, out guess))  
        {  
            MessageBox.Show("Please enter an integer.");  
            Guess.SelectAll();  
            Guess.Focus();  
            return;  
        }  
  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
        // Use the persisted WorkflowIdentity to retrieve the correct workflow  
        // definition from the dictionary.  
        Activity wf =  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
        // Associate the WorkflowApplication with the correct definition  
        WorkflowApplication wfApp =  
            new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
        // Configure the extensions and lifecycle handlers.  
        // Do this before the instance is loaded. Once the instance is  
        // loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Load the workflow.  
        wfApp.Load(instance);  
  
        // Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", guess);  
  
        // Clear the Guess textbox.  
        Guess.Clear();  
        Guess.Focus();  
    }  
    ```  
  
###  <a name="a-namebkmkterminateworkflowa-to-terminate-a-workflow"></a><a name="BKMK_TerminateWorkflow"></a> Para finalizar un flujo de trabajo  
  
1.  Agregue un controlador `Click` para `QuitGame`. Para agregar el controlador, cambie a **vista Diseño** para el formulario y haga doble clic en `QuitGame`. Siempre que el usuario haga clic en este botón se finalizará el flujo de trabajo seleccionado actualmente.  
  
    ```vb  
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void QuitGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2.  Agregue el código siguiente al controlador `QuitGame_Click`. Este código primero comprueba que un flujo de trabajo está seleccionado en la lista de flujos de trabajo. Después, carga la instancia persistente en `WorkflowApplicationInstance`, usa `DefinitionIdentity` para determinar la definición correcta de flujo de trabajo e inicializa `WorkflowApplication`. A continuación, las extensiones y los controladores de ciclo de vida de flujo de trabajo se configuran mediante una llamada a `ConfigureWorkflowApplication`. Una vez se ha configurado `WorkflowApplication`, se carga y, a continuación, `Terminate` recibe una llamada.  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition.  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
    'Configure the extensions and lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Terminate the workflow.  
    wfApp.Terminate("User resigns.")  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
    // Configure the extensions and lifecycle handlers  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Terminate the workflow.  
    wfApp.Terminate("User resigns.");  
    ```  
  
###  <a name="a-namebkmkbuildandruna-to-build-and-run-the-application"></a><a name="BKMK_BuildAndRun"></a> Para compilar y ejecutar la aplicación  
  
1.  Haga doble clic en **Program.cs** (o **Module1.vb**) en **el Explorador de soluciones** para mostrar el código.  
  
2.  Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).  
  
    ```vb  
    Imports System.Windows.Forms  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
3.  Elimine o comente el código de hospedaje de flujo de trabajo existente [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md), y reemplácelo por el código siguiente.  
  
    ```vb  
    Sub Main()  
        Application.EnableVisualStyles()  
        Application.Run(New WorkflowHostForm())  
    End Sub  
    ```  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        Application.EnableVisualStyles();  
        Application.Run(new WorkflowHostForm());  
    }  
    ```  
  
4.  Haga clic en **NumberGuessWorkflowHost** en **el Explorador de soluciones** y elija **propiedades**. En el **aplicación** especifique **aplicación de Windows** para el **tipo de salida**. Este paso es opcional, pero si no se realiza la ventana de la consola se muestra además del formulario.  
  
5.  Presione Ctrl+Mayús+B para compilar la aplicación.  
  
6.  Asegúrese de que **NumberGuessWorkflowHost** está establecido como la aplicación de inicio y presione Ctrl + F5 para iniciar la aplicación.  
  
7.  Seleccionar un intervalo para el juego de adivinanzas y el tipo de flujo de trabajo de inicio y haga clic en **New Game**. Escriba un intento en el **suposición** y haga clic en **vaya** para enviarlo. Observe que el resultado de las actividades `WriteLine` se muestra en el formulario.  
  
8.  Inicie varios flujos de trabajo mediante tipos de flujo de trabajo diferente e intervalos de números, escriba algunos números y cambiar entre los flujos de trabajo mediante la selección de la **Id. de instancia de flujo de trabajo** lista.  
  
     Observe que al cambiar a un nuevo flujo de trabajo, los intentos anteriores y el progreso del flujo de trabajo no aparecen en la ventana de estado. El estado no está disponible porque no se captura ni guarda en ningún lugar. En el siguiente paso del tutorial, [Cómo: crear un participante de seguimiento personalizado](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-tracking-participant.md), crear un participante de seguimiento personalizado que guarda esta información.