---
title: "Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de dise&#241;o | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], depurar"
  - "controles personalizados [Windows Forms], depurar"
  - "controles personalizados [Windows Forms], tutoriales"
  - "depurar [Visual Studio], tutoriales"
  - "depurar [Visual Studio], Windows Forms"
  - "diseñadores"
  - "depuración en tiempo de diseño"
  - "editores visuales"
  - "tutoriales [Windows Forms], depurar"
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de dise&#241;o
Cuando crea un control personalizado, con frecuencia encontrará necesario depurar su comportamiento en tiempo de diseño.  Esto es cierto si está creando un diseñador personalizado para su control personalizado.  Para obtener información detallada, vea [Tutorial: Crear un control de formularios Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
 Puede depurar sus controles personalizados mediante Visual Studio, al igual que depuraría cualquier otra clase de .NET Framework.  La diferencia es que depurará una instancia independiente de Visual Studio que está ejecutando código del control personalizado  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms para hospedar su control personalizado  
  
-   Crear un proyecto de Biblioteca de controles  
  
-   Agregar una propiedad al control personalizado  
  
-   Agregar el control personalizado al formulario de host  
  
-   Preparar el proyecto para la depuración en tiempo de diseño  
  
-   Depurar en tiempo de diseño el control personalizado  
  
 Cuando finalice, tendrá los conocimientos de las tareas necesarias para depurar el comportamiento en tiempo de diseño de un control personalizado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 El primer paso es crear el proyecto de aplicación.  Este proyecto se utilizará para compilar la aplicación que hospeda el control personalizado.  
  
#### Para crear el proyecto  
  
-   Cree un proyecto de aplicación para Windows denominado "DebuggingExample".  Para obtener información detallada, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## Crear un proyecto de Biblioteca de controles  
 El paso siguiente es crear el proyecto de Biblioteca de controles y configurar el control personalizado.  
  
#### Para crear el proyecto de Biblioteca de controles  
  
1.  Agregue un proyecto de **Biblioteca de controles de Windows** a la solución.  
  
2.  Agregue un nuevo elemento **UserControl** al proyecto DebugControlLibrary.  Para obtener información detallada, vea [NIB:How to: Add New Project Items](http://msdn.microsoft.com/es-es/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  Dé el nombre base de "DebugControl" al nuevo archivo de código fuente.  
  
3.  Con el **Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código con nombre base de "`UserControl1`".  Para obtener información detallada, vea [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/es-es/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
4.  Compile la solución.  
  
## Punto de control  
 Llegado a este punto, podrá ver su control personalizado en el **Cuadro de herramientas**.  
  
#### Para comprobar su progreso  
  
-   Busque la nueva ficha llamada **Componentes de DebugControlLibrary** y haga clic para seleccionarlo.  Cuando se abre, verá el control listado como **DebugControl** con el icono predeterminado junto a él.  
  
## Agregar una propiedad al control personalizado  
 Para mostrar que el código del control personalizado se está ejecutando en tiempo de diseño, agregue una propiedad y establezca un punto de interrupción en el código que implementa la propiedad.  
  
#### Para agregar una propiedad al control personalizado  
  
1.  Abra **DebugControl** en el **Editor de código**.  Agregue el código siguiente a la definición de clase:  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  Compile la solución.  
  
## Agregar el control personalizado al formulario de host  
 Para depurar el comportamiento en tiempo de diseño del control personalizado, coloque una instancia de la clase del control personalizado en un formulario de host.  
  
#### Para agregar el control personalizado al formulario de host  
  
1.  En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.  
  
2.  En el **Cuadro de herramientas**, abra la ficha **Componentes de DebugControlLibrary** y arrastre una instancia de **DebugControl** al formulario.  
  
3.  Busque la propiedad personalizada `DemoString` en la ventana **Propiedades**.  Observe que puede cambiar su valor cuando haría con cualquier otra propiedad.  También observe que cuando se selecciona la propiedad `DemoString`, la cadena de descripción de la propiedad aparece en la parte inferior de la ventana **Propiedades**.  
  
## Establecer el proyecto para depuración en tiempo de diseño  
 Para depurar el comportamiento en tiempo de diseño del control personalizado, depure una instancia independiente de Visual Studio que está ejecutando el código del control personalizado.  
  
#### Para configurar el proyecto para depuración en tiempo de diseño  
  
1.  Haga clic con el botón secundario del mouse en el proyecto **DebugControlLibrary** en el **Explorador de soluciones** y seleccione **Propiedades**.  
  
2.  En la hoja de propiedades de **DebugControlLibrary**, seleccione la ficha **Depurar**.  
  
     En la sección **Acción de inicio**, seleccione **Programa externo de inicio**.  Como está depurando una instancia independiente de Visual Studio, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) para buscar el IDE de Visual Studio.  El nombre del archivo ejecutable es **devenv.exe**, y si ha realizado la instalación en la ubicación predeterminada, la ruta de acceso será %Archivos de programa%\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe.  
  
3.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
4.  Haga clic con el botón secundario del mouse en el proyecto **DebugControlLibrary** y seleccione **Establecer como proyecto de inicio** para habilitar esta configuración de depuración.  
  
## Depurar el control personalizado en tiempo de diseño  
 Ahora ya puede depurar el control personalizado cuando se ejecuta en modo de diseño.  Cuando inicia la sesión de depuración, se creará una nueva instancia de Visual Studio, y podrá utilizarla para cargar la solución "DebuggingExample".  Cuando abre Form1 en el **Diseñador de formularios**, se creará una instancia del control personalizado y comenzará a ejecutarse.  
  
#### Para depurar en tiempo de diseño el control personalizado  
  
1.  Abra el archivo de código fuente de **DebugControl** en el **Editor de código** y coloque un punto de interrupción en el descriptor de acceso `Set` de la propiedad `DemoString`.  
  
2.  Presione F5 para iniciar la depuración.  Observe que se crea una nueva instancia de Visual Studio.  Hay dos maneras de distinguir entre las instancias:  
  
    -   La instancia de la depuración tiene la palabra **En ejecución** en su barra de título  
  
    -   La instancia de la depuración tiene el botón **Iniciar** en la barra de herramientas **Depuración** deshabilitado  
  
     El punto de interrupción se establece en la instancia de la depuración.  
  
3.  En la nueva instancia de Visual Studio, abra la solución "DebuggingExample".  Para encontrar con facilidad la solución, seleccione **Proyectos recientes** en el menú **Archivo**.  El archivo de solución "DebuggingExample.sln" se mostrará como el último archivo utilizado.  
  
4.  Abra Form1 en el **Diseñador de formularios** y seleccione el control **DebugControl**.  
  
5.  Cambie el valor de la propiedad `DemoString`.  Tenga en cuenta que cuando confirma el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción.  Puede recorrer paso paso el descriptor de acceso de la propiedad al igual que con cualquier otro código.  
  
6.  Cuando haya finalizado la sesión de depuración, puede salir descartando la instancia de host de Visual Studio o haciendo clic en el botón **Detener depuración** en la instancia de depuración.  
  
## Pasos siguientes  
 Ahora que puede depurar controles personalizados en tiempo de diseño, hay varias posibilidades de ampliar la interacción del control con el IDE de Visual Studio.  
  
-   Puede utilizar la propiedad <xref:System.ComponentModel.Component.DesignMode%2A> de la clase <xref:System.ComponentModel.Component> para escribir código que sólo se ejecutará en tiempo de diseño.  Para obtener información detallada, vea <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Puede aplicar varios atributos a las propiedades del control para manipular la interacción del control personalizado con el diseñador.  Puede encontrar estos atributos en el espacio de nombres <xref:System.ComponentModel?displayProperty=fullName>.  
  
-   Puede escribir un diseñador personalizado para el control personalizado.  Este procedimiento proporciona un control total sobre la experiencia de diseño mediante la infraestructura del diseñador extensible expuesta por Visual Studio.  Para obtener información detallada, vea [Tutorial: Crear un control de formularios Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
## Vea también  
 [Tutorial: Crear un control de formularios Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)   
 [How to: Access Design\-Time Services](../Topic/How%20to:%20Access%20Design-Time%20Services.md)   
 [How to: Access Design\-Time Support in Windows Forms](../Topic/How%20to:%20Access%20Design-Time%20Support%20in%20Windows%20Forms.md)