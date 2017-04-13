---
title: "Uso de la actividad InvokePowerShell | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Uso de la actividad InvokePowerShell
En el ejemplo InvokePowerShell se muestra cómo invocar comandos de Windows PowerShell mediante la actividad `InvokePowerShell`.  
  
## Demostraciones  
  
-   Innovación simple de comandos de Windows PowerShell.  
  
-   Recuperar valores de la canalización de salida de Windows PowerShell y almacenarlos en variables de flujo de trabajo.  
  
-   Pasar datos a Windows PowerShell como canalización de entrada para un comando en ejecución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## Análisis  
 Este ejemplo contiene estos tres proyectos.  
  
|Nombre del proyecto|Descripción|Archivos principales|  
|-------------------------|-----------------|--------------------------|  
|CodedClient|Una aplicación cliente de ejemplo que utiliza la actividad de PowerShell.|-   **Program.cs**: crea un flujo de trabajo basado en secuencia mediante programación que llama a la actividad InvokePowerShell.|  
|DesignerClient|Un conjunto de actividades personalizadas que contiene la actividad personalizada `InvokePowerShell` y otras actividades personalizadas y un flujo de trabajo que los utiliza.|<ul><li>Actividades:<br /><br /> <ul><li>**PrintCollection.cs**: una actividad de aplicación auxiliar que imprime todos los elementos de una colección en la consola.</li><li>**ReadLine.cs**: una actividad de aplicación auxiliar para leer la entrada de la consola.</li></ul></li><li>Sistema de archivos:<br /><br /> <ul><li>**Copy.xaml**: una actividad que copia un archivo.</li><li>**CreateFile.xaml**: una actividad que crea un archivo.</li><li>**DeleteFile.xaml**: una actividad que elimina un archivo.</li><li>**MakeDir.xaml**: una actividad que crea un directorio.</li><li>**Move.xaml**: una actividad que mueve un archivo.</li><li>**ReadFile.xaml**: una actividad que lee un archivo y devuelve su contenido.</li><li>**TestPath.xaml**: una actividad que comprueba la existencia de una ruta de acceso.</li></ul></li><li>Proceso:<br /><br /> <ul><li>**GetProcess.xaml**: una actividad que obtiene una lista de procesos en ejecución.</li><li>**StopProcess.xaml**: una actividad que detiene un proceso concreto.</li></ul></li><li>**Program.cs**: llama al flujo de trabajo Sequence1.</li><li>**Sequence1.xaml**: un flujo de trabajo basado en secuencia.</li></ul>|  
|PowerShell|La actividad `InvokePowerShell` y sus diseñadores asociados.|Archivos de actividad<br /><br /> -   **ExecutePowerShell.cs**: la lógica de ejecución principal de la actividad.<br />-   **InvokePowerShell.cs**: el contenedor alrededor de la lógica de ejecución principal, que incluye una versión genérica \(valor devuelto\) y otra no genérica \(valor no devuelto\).Esta es la interfaz pública de la actividad.<br />-   **NoPersistZone.cs**: esta actividad evita la conservación de las actividades secundarias.Esta clase se utiliza dentro de la implementación de la actividad `InvokePowerShell` para evitar que la actividad se conserve en la mitad de la ejecución.<br /><br /> Archivos de diseñador:<br /><br /> 1.  **ArgumentDictionaryEditor.cs**: un diálogo de Windows que permite al usuario modificar los argumentos de la actividad `InvokePowerShell`.<br />2.  **GenericInvokePowerShellDesigner.xaml** y **GenericInvokePowerShellDesigner.xaml.cs**: define el aspecto de la actividad `InvokePowerShell` genérica en [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].<br />3.  **InvokePowerShellDesigner.xaml** e **InvokePowerShellDesigner.cs**: define el aspecto de actividad `InvokePowerShell` no genérica en [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].|  
  
 Primero se describen los proyectos de cliente, porque es más fácil entender la funcionalidad interna de la actividad de PowerShell una vez comprendido su uso.  
  
## Utilizar este ejemplo  
 En las siguientes secciones se describe cómo utilizar los tres proyectos del ejemplo.  
  
### Utilizar el proyecto de cliente codificado  
 El cliente del ejemplo crea mediante programación una actividad de secuencia, que contiene ejemplos de varios métodos diferentes de utilizar la actividad `InvokePowerShell`.La primera invocación inicia el Bloc de notas.  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
  
```  
  
 La segunda invocación obtiene una lista de los procesos que se están ejecutando en el equipo local.  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
  
```  
  
 `Output` es la variable utilizada para almacenar el resultado del comando.  
  
 La llamada siguiente muestra cómo ejecutar un paso de procesamiento posterior en cada salida individual de la invocación de PowerShell.`InitializationAction` se establece en la función que genera una representación de cadena de cada proceso.La colección de estas cadenas se devuelve en la variable `Output` por la actividad `InvokePowerShell<string>`.  
  
 Las llamadas `InvokePowerShell` subsiguientes muestran el paso de datos a la actividad y la obtención de resultados y errores.  
  
### Utilizar el proyecto de cliente de diseñador  
 El proyecto DesignerClient consta de un conjunto de actividades personalizadas, casi todas compiladas incluyendo la actividad `InvokePowerShell`.La mayoría de las actividades llaman a la versión no genérica de la actividad `InvokePowerShell` y no esperan un valor devuelto.Otras actividades utilizan la versión genérica de la actividad `InvokePowerShell` y utilizan el argumento `InitializationAction` para post\-procesar los resultados.  
  
## Utilizar el proyecto PowerShell  
 La acción principal de la actividad tiene lugar en la clase `ExecutePowerShell`.Dado que la ejecución de los comandos de PowerShell no debe bloquear el subproceso del flujo de trabajo principal, la actividad se crea como actividad asincrónica que hereda de la clase <xref:System.Activities.AsyncCodeActivity>.  
  
 El tiempo de ejecución del flujo de trabajo llama al método <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> para empezar a ejecutar la actividad.Se inicia llamando a PowerShell API para crear una canalización de PowerShell.  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
  
```  
  
 A continuación, crea un comando de PowerShell y lo rellena con parámetros y variables.  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
  
```  
  
 Las entradas canalizadas también se envían en este momento a la canalización.Por último, la canalización se ajusta en un objeto `PipelineInvokerAsyncResult` y se devuelve.El objeto `PipelineInvokerAsyncResult` registra un agente de escucha e invoca la canalización.  
  
```  
pipeline.InvokeAsync();  
  
```  
  
 Cuando finaliza la ejecución, los resultados y los errores se almacenan dentro del mismo objeto `PipelineInvokerAsyncResult` y el control se devuelve al tiempo de ejecución del flujo de trabajo llamando al método de devolución de llamada pasado originalmente a <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.  
  
 Al final de la ejecución del método, el tiempo de ejecución del flujo de trabajo llama al método <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> de la actividad.  
  
 La clase `InvokePowerShell` ajusta la clase `ExecutePowerShellCommand` y crea dos versiones de la actividad; una versión genérica y otra no genérica.La versión no genérica devuelve el resultado de la ejecución de PowerShell directamente, mientras que la versión genérica transforma los resultados individuales al tipo genérico.  
  
 La versión genérica de la actividad se implementa como un flujo de trabajo secuencial que llama a `ExecutePowerShellCommand` y post\-procesa sus resultados.Para cada elemento de la colección de resultados, el paso de procesamiento posterior llama a `InitializationAction` si se ha establecido.De lo contrario, realiza una conversión de tipos simple.  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
  
```  
  
 Se creó un diseñador para cada una de las dos actividades `InvokePowerShell` \(genérica y no genérica\).InvokePowerShellDesigner.xaml y su archivo .cs asociado definen el aspecto en [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] para la versión no genérica de la actividad `InvokePowerShell`.Dentro de InvokePowerShellDesigner.xaml, <xref:System.Windows.Controls.DockPanel> se utiliza para representar la interfaz gráfica.  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
  
```  
  
 Observe que la propiedad `Text` del cuadro de texto es un enlace bidireccional que garantiza que el valor de la propiedad `CommandText` de la actividad es equivalente al valor introducido en el diseñador.  
  
 GenericInvokePowerShellDesigner.xaml y su archivo .cs asociado definen la interfaz gráfica de la actividad `InvokePowerShell` genérica.El diseñador es ligeramente más complicado, porque permite a los usuarios establecer una acción `InitializationAction`.El elemento clave es el uso de <xref:System.Activities.Presentation.WorkflowItemPresenter> para permitir arrastrar y colocar las actividades secundarias en la superficie del diseñador de `InvokePowerShell`.  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
  
```  
  
 La personalización del diseñador no se detiene con los archivos .xaml que definen el aspecto de la actividad en el lienzo del diseño.Los cuadros de diálogo utilizados para mostrar los parámetros de la actividad también se pueden personalizar.Estos parámetros y las variables de PowerShell afectan al comportamiento de los comandos de PowerShell.La actividad los expone como tipos <xref:System.Collections.Generic.Dictionary%601>.ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml y PropertyEditorResources.cs definen el cuadro de diálogo que permite modificar estos tipos.  
  
## Para configurar, compilar y ejecutar el ejemplo  
 Debe instalar Windows PowerShell para ejecutar este ejemplo.Windows PowerShell se puede instalar desde esta ubicación: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).  
  
#### Para ejecutar el cliente codificado  
  
1.  Abra PowerShell.sln mediante [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Haga clic con el botón secundario en la solución y compílela.  
  
3.  Haga clic con el botón secundario en el proyecto **CodedClient** y seleccione **Establecer como proyecto de inicio**.  
  
4.  Presione CTRL\+F5 para ejecutar la aplicación.  
  
#### Para ejecutar el cliente del diseñador  
  
1.  Abra PowerShell.sln mediante [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Haga clic con el botón secundario en la solución y compílela.  
  
3.  Haga clic con el botón secundario en el proyecto **DesignerClient** y seleccione **Establecer como proyecto de inicio**.  
  
4.  Presione CTRL\+F5 para ejecutar la aplicación.  
  
## Problemas conocidos  
  
1.  Si se hace referencia al ensamblado de actividad o proyecto `InvokePowerShell` desde otro proyecto, se produce un error de compilación; es posible que necesite agregar manualmente el elemento `<SpecificVersion>True</SpecificVersion>` al archivo .csproj del nuevo proyecto bajo la línea que hace referencia a `InvokePowerShell`.  
  
2.  Si Windows PowerShell no está instalado, se mostrará el siguiente mensaje de error en Visual Studio cuando se agregue una actividad `InvokePowerShell` un flujo de trabajo: `Problemas del Diseñador de flujo de trabajo con el documento. No pudo cargar el archivo ni ensamblado 'System.Management.Automation'... o uno de sus dependencias. El sistema no puede encontrar el archivo especificado.`  
  
3.  En Windows PowerShell 2.0, al llamar mediante programación a los errores y scripts de `$input.MoveNext()` utilizando `$input.MoveNext()`, se generan errores y resultados imprevistos.Para evitar este problema, considere la utilización del verbo de PowerShell `foreach` en lugar de llamar a `MoveNext()` al recorrer en iteración una matriz.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## Vea también