---
title: "Tutorial: Crear un control de formularios Windows Forms que aproveche las caracter&#237;sticas en tiempo de dise&#241;o de Visual Studio | Microsoft Docs"
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
  - "funcionalidad en tiempo de diseño, Windows Forms"
  - "DocumentDesigner (clase) [formularios Windows Forms]"
  - "tutoriales [Windows Forms], controles"
  - "controles de Windows Forms, crear"
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: 46
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 46
---
# Tutorial: Crear un control de formularios Windows Forms que aproveche las caracter&#237;sticas en tiempo de dise&#241;o de Visual Studio
Se puede mejorar la experiencia en tiempo de diseño para un control personalizado creando un diseñador personalizado asociado.  
  
 En este tutorial se muestra cómo crear a un diseñador personalizado para un control personalizado.  Implementará un tipo `MarqueeControl` y una clase de diseñador asociada, denominada `MarqueeControlRootDesigner`.  
  
 El tipo `MarqueeControl` implementa una presentación similar a una marquesina de teatro, con luces animadas y el texto parpadeante.  
  
 El diseñador para este control interactúa con el entorno de diseño para proporcionar una experiencia en tiempo de diseño personalizada.  Con el diseñador personalizado, se puede ensamblar una implementación de `MarqueeControl` personalizada con luces animadas y texto parpadeante en muchas combinaciones.  Se puede utilizar el control ensamblado en un formulario como cualquier otro control de formularios Windows Forms.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto  
  
-   Crear un proyecto de Biblioteca de controles  
  
-   Hacer referencia al proyecto de Biblioteca de controles  
  
-   Definir un control personalizado y su diseñador personalizado  
  
-   Crear una instancia del control personalizado  
  
-   Establecer el proyecto para depuración en tiempo de diseño  
  
-   Implementar el control personalizado  
  
-   Crear un control secundario para el control personalizado  
  
-   Crear el control MarqueeBorder secundario  
  
-   Crear un diseñador personalizado para sombrear y filtrar propiedades  
  
-   Controlar los cambios de componente  
  
-   Agregar verbos del diseñador al diseñador personalizado  
  
-   Crear un UITypeEditor personalizado  
  
-   Probar el control personalizado en el diseñador  
  
 Cuando termine, el control personalizado tendrá el siguiente aspecto:  
  
 ![Posible organización de MarqueeControl](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")  
  
 Para obtener la lista de código completa, vea [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde esté instalado Visual Studio.  
  
## Crear el proyecto  
 El primer paso es crear el proyecto de aplicación.  Este proyecto se utilizará para compilar la aplicación que hospeda el control personalizado.  
  
#### Para crear el proyecto  
  
-   Cree un proyecto de aplicación de Windows Forms llamado "MarqueeControlTest". Para obtener más información, consulte [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## Crear un proyecto de Biblioteca de controles  
 El paso siguiente es crear el proyecto de Biblioteca de controles.  Creará a un nuevo control personalizado y su diseñador personalizado correspondiente.  
  
#### Para crear el proyecto de Biblioteca de controles  
  
1.  Agregue un proyecto de Biblioteca de controles de Windows Forms a la solución.  Dé al proyecto el nombre de "MarqueeControlLibrary".  
  
2.  Con el **Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código fuente denominado "UserControl1.cs" o "UserControl1.vb", dependiendo del lenguaje elegido.  Para obtener más información, vea [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/es-es/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Agregue un nuevo elemento <xref:System.Windows.Forms.UserControl> al proyecto `MarqueeControlLibrary`.  Dé el nombre base de "MarqueeControl" al nuevo archivo de código fuente.  
  
4.  Con el **Explorador de soluciones**, cree una nueva carpeta en el proyecto `MarqueeControlLibrary`.  Para obtener más información, vea [NIB:How to: Add New Project Items](http://msdn.microsoft.com/es-es/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  Denomine "Diseño" a la nueva carpeta.  
  
5.  Haga clic con el botón secundario del mouse en la carpeta **Diseño** y agregue una nueva clase.  Dé el nombre base de "MarqueeControlRootDesigner" al archivo de código fuente.  
  
6.  Necesitará utilizar los tipos del ensamblado System.Design, así que agregue esta referencia al proyecto `MarqueeControlLibrary`.  
  
    > [!NOTE]
    >  Para usar el ensamblado System.Design, el proyecto debe tener como destino la versión completa de .NET Framework, no .NET Framework Client Profile.  Para cambiar la versión de .NET Framework de destino, vea [Cómo: Usar como destino una versión de .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
## Hacer referencia al proyecto de Biblioteca de controles  
 Utilizará el proyecto `MarqueeControlTest` para probar el control personalizado.  El proyecto de prueba se dará cuenta del control personalizado cuando agregue una referencia de proyecto al ensamblado `MarqueeControlLibrary`.  
  
#### Para hacer referencia al proyecto de control personalizado  
  
-   En el proyecto `MarqueeControlTest`, agregue una referencia de proyecto al ensamblado `MarqueeControlLibrary`.  Asegúrese de utilizar la ficha **Proyectos** en el cuadro de diálogo **Agregar referencia** en lugar de hacer referencia directamente al ensamblado `MarqueeControlLibrary`.  
  
## Definir un control personalizado y su diseñador personalizado  
 Su control personalizado derivará de la clase <xref:System.Windows.Forms.UserControl>.  Esta opción permite al control contener otros controles y da una gran funcionalidad predeterminada al control.  
  
 El control personalizado tendrá un diseñador personalizado asociado.  Esto le permite crear una experiencia del diseño única, personalizada específicamente para su control personalizado.  
  
 Asocie el control a su diseñador utilizando la clase <xref:System.ComponentModel.DesignerAttribute>.  Como está desarrollando el comportamiento en tiempo de diseño completo del control personalizado, el diseñador personalizado implementará la interfaz <xref:System.ComponentModel.Design.IRootDesigner>.  
  
#### Para definir un control personalizado y su diseñador personalizado  
  
1.  Abra el archivo de código fuente `MarqueeControl` en el **Editor de código**.  En la parte superior del archivo, importe los espacios de nombres siguientes:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  Agregue <xref:System.ComponentModel.DesignerAttribute> a la declaración de clase `MarqueeControl`.  Esta opción asocia el control personalizado a su diseñador.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  Abra el archivo de código fuente `MarqueeControlRootDesigner` en el **Editor de código**.  En la parte superior del archivo, importe los espacios de nombres siguientes:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  Cambie la declaración de `MarqueeControlRootDesigner` para heredar de la clase <xref:System.Windows.Forms.Design.DocumentDesigner>.  Aplique <xref:System.ComponentModel.ToolboxItemFilterAttribute> para especificar la interacción del diseñador con el **Cuadro de herramientas**.  
  
     **Nota** La definición de la clase `MarqueeControlRootDesigner` se ha incluido en el espacio de nombres "MarqueeControlLibrary.Design". Esta declaración coloca el diseñador en un espacio de nombres especial reservado para los tipos relacionados con el diseño.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  Defina el constructor para la clase `MarqueeControlRootDesigner`.  Inserte una instrucción <xref:System.Diagnostics.Trace.WriteLine%2A> en el cuerpo del constructor.  Esta opción es útil con fines de depuración.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## Crear una instancia del control personalizado  
 Para observar el comportamiento en tiempo de diseño personalizado del control, colocará una instancia de su control en el formulario en el proyecto `MarqueeControlTest`.  
  
#### Para crear una instancia de su control personalizado  
  
1.  Agregue un nuevo elemento <xref:System.Windows.Forms.UserControl> al proyecto `MarqueeControlTest`.  Dé el nombre base de "DemoMarqueeControl" al nuevo archivo de código fuente.  
  
2.  Abra el archivo `DemoMarqueeControl` en el **Editor de código**.  En la parte superior del archivo, importe el espacio de nombres `MarqueeControlLibrary`:  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  Cambie la declaración de `DemoMarqueeControl` para heredar de la clase `MarqueeControl`.  
  
2.  Compile el proyecto.  
  
3.  Abra `Form1` en el Diseñador de Windows Forms.  
  
4.  Busque la ficha **Componentes de MarqueeControlTest** en el **Cuadro de herramientas** y ábrala.  Arrastre un `DemoMarqueeControl` desde el **Cuadro de herramientas** al formulario.  
  
5.  Compile el proyecto.  
  
## Establecer el proyecto para depuración en tiempo de diseño  
 Cuando está desarrollando una experiencia en tiempo de diseño personalizada, será necesario depurar los controles y componentes.  Hay un modo muy sencillo de configurar el proyecto para permitir la depuración en tiempo de diseño.  Para obtener más información, vea [Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
#### Para configurar el proyecto para depuración en tiempo de diseño  
  
1.  Haga clic con el botón secundario del mouse en el proyecto `MarqueeControlLibrary` y seleccione **Propiedades**.  
  
2.  En el cuadro de diálogo "Páginas de propiedades de MarqueeControlLibrary", seleccione la página **Depurar**.  
  
3.  En la sección **Acción de inicio**, seleccione **Programa externo de inicio**.  Como está depurando una instancia independiente de Visual Studio, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) para buscar el IDE de Visual Studio.  El nombre del archivo ejecutable es devenv.exe, y si ha realizado la instalación en la ubicación predeterminada, la ruta de acceso será %Archivos de programa%\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe.  
  
4.  Haga clic en Aceptar para cerrar el cuadro de diálogo.  
  
5.  Haga clic con el botón secundario del mouse en el proyecto `MarqueeControlLibrary` y seleccione "Establecer como proyecto de inicio" para habilitar esta configuración de depuración.  
  
## Punto de control  
 Ahora está listo para depurar el comportamiento en tiempo de diseño de su control personalizado.  Una vez determinado que el entorno de depuración está configurado correctamente, probará la asociación entre el control personalizado y el diseñador personalizado.  
  
#### Para probar el entorno de depuración y la asociación del diseñador  
  
1.  Abra el archivo de código fuente `MarqueeControlRootDesigner` en el **Editor de código** y coloque un punto de interrupción en la instrucción <xref:System.Diagnostics.Trace.WriteLine%2A>.  
  
2.  Presione F5 para iniciar la depuración.  Observe que se crea una nueva instancia de Visual Studio.  
  
3.  En la nueva instancia de Visual Studio, abra la solución "MarqueeControlTest".  Para encontrar con facilidad la solución, seleccione **Proyectos recientes** en el menú **Archivo**.  El archivo de solución "MarqueeControlTest.sln" se mostrará como el último archivo utilizado.  
  
4.  Abra `DemoMarqueeControl` en el diseñador.  Observe que la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en su punto de interrupción.  Presione F5 para continuar la sesión de depuración.  
  
 En este punto, todo está listo para desarrollar y depurar el control personalizado y su diseñador personalizado asociado.  El resto de este tutorial se concentrará en los detalles de implementación de las características del control y el diseñador.  
  
## Implementar el control personalizado  
 `MarqueeControl` es un <xref:System.Windows.Forms.UserControl> con algo de personalización.  Expone dos métodos: `Start`, que inicia la animación de la marquesina, y `Stop`, que detiene la animación.  Como `MarqueeControl` contiene controles secundarios que implementan la interfaz `IMarqueeWidget`, `Start` y `Stop` enumeran cada control secundario y llaman a los métodos `StartMarquee` y `StopMarquee`, respectivamente, en cada control secundario que implementa `IMarqueeWidget`.  
  
 La apariencia de los controles `MarqueeBorder` y `MarqueeText` depende del diseño, por tanto `MarqueeControl` reemplaza el método <xref:System.Windows.Forms.Control.OnLayout%2A> y llama al método <xref:System.Windows.Forms.Control.PerformLayout%2A> en los controles secundarios de este tipo.  
  
 Ésta es la extensión de las personalizaciones de `MarqueeControl`.  Los controles `MarqueeBorder` y `MarqueeText` implementan las características en tiempo de ejecución y las clases `MarqueeBorderDesigner` y `MarqueeControlRootDesigner` implementan las características en tiempo de diseño.  
  
#### Para implementar el control personalizado  
  
1.  Abra el archivo de código fuente `MarqueeControl` en el **Editor de código**.  Implemente los métodos `Start` y `Stop`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  Reemplace el método <xref:System.Windows.Forms.Control.OnLayout%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## Crear un control secundario para el control personalizado  
 `MarqueeControl` hospedará dos tipos de control secundario: el control `MarqueeBorder` y el control `MarqueeText`.  
  
-   `MarqueeBorder`: Este control representa un borde de "luces" alrededor de los bordes.  Las luces parpadean en forma secuencial, por lo que parece que se mueven alrededor del borde.  La velocidad de parpadeo de las luces está controlada por una propiedad llamada `UpdatePeriod`.  Varias propiedades personalizadas determinan otros aspectos de la apariencia del control.  Dos métodos, llamados `StartMarquee` y `StopMarquee`, controlan cuándo se inicia o se detiene la animación.  
  
-   `MarqueeText`: Este control representa una cadena parpadeante.  Al igual que el control `MarqueeBorder`, la velocidad en la que el texto parpadea está controlada por la propiedad `UpdatePeriod`.  El control `MarqueeText` también tiene en común los métodos `StartMarquee` y `StopMarquee` con el control `MarqueeBorder`.  
  
 En tiempo de diseño, `MarqueeControlRootDesigner` permite agregar estos dos tipos de control a `MarqueeControl` en cualquier combinación.  
  
 Las características comunes de los dos controles se factorizan en una interfaz llamada `IMarqueeWidget`.  Esto permite a `MarqueeControl` detectar los controles secundarios relacionados con la marquesina y darles un tratamiento especial.  
  
 Para implementar la característica de animación periódica, utilizará los objetos <xref:System.ComponentModel.BackgroundWorker> del espacio de nombres <xref:System.ComponentModel?displayProperty=fullName>.  Podría utilizar los objetos <xref:System.Windows.Forms.Timer>, pero cuando hay presentes varios objetos `IMarqueeWidget`, es posible que el único subproceso de la interfaz de usuario no pueda mantener la animación.  
  
#### Para crear un control secundario para su control personalizado  
  
1.  Agregue un nuevo elemento de clase al proyecto `MarqueeControlLibrary`.  Dé el nombre base de "IMarqueeWidget" al nuevo archivo de código fuente.  
  
2.  Abra el archivo de código fuente `IMarqueeWidget` en el **Editor de código** y cambie la declaración de `class` a `interface`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  Agregue el código siguiente a la interfaz `IMarqueeWidget` para exponer dos métodos y una propiedad que manipulan la animación de la marquesina:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  Agregue un nuevo elemento **Control personalizado** al proyecto `MarqueeControlLibrary`.  Dé el nombre base de "MarqueeText" al nuevo archivo de código fuente.  
  
5.  Arrastre un componente <xref:System.ComponentModel.BackgroundWorker> desde el **Cuadro de herramientas** hasta el control `MarqueeText`.  Este componente permitirá al control `MarqueeText` actualizarse de forma asincrónica.  
  
6.  En la ventana Propiedades, establezca las propiedades `WorkerReportsProgess` y <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente <xref:System.ComponentModel.BackgroundWorker> en `true`.  Esta configuración permite al componente <xref:System.ComponentModel.BackgroundWorker> provocar periódicamente el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y cancelar las actualizaciones asincrónicas.  Para obtener más información, vea [BackgroundWorker \(Componente\)](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
7.  Abra el archivo de código fuente `MarqueeText` en el **Editor de código**.  En la parte superior del archivo, importe los espacios de nombres siguientes:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  Cambie la declaración de `MarqueeText` para heredar de <xref:System.Windows.Forms.Label> e implementar la interfaz `IMarqueeWidget`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. Declare las variables de instancia que corresponden a las propiedades expuestas e inicialícelas en el constructor.  El campo `isLit` determina si el texto se representa en el color proporcionado por la propiedad `LightColor`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. Implemente la interfaz `IMarqueeWidget`.  
  
     Los métodos `StartMarquee` y `StopMarquee` invocan los métodos <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> y <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> del componente <xref:System.ComponentModel.BackgroundWorker> para iniciar y detener la aplicación.  
  
     Los atributos <xref:System.ComponentModel.CategoryAttribute.Category%2A> y <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> se aplican a la propiedad `UpdatePeriod`, por lo que aparece en una sección personalizada de la ventana Propiedades llamada "Marquesina".  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. Implemente los descriptores de acceso de propiedad.  Expone dos propiedades a los clientes: `LightColor` y `DarkColor`.  Los atributos <xref:System.ComponentModel.CategoryAttribute.Category%2A> y <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> se aplican a estas propiedades, por lo que aparece en una sección personalizada de la ventana Propiedades llamada "Marquesina".  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. Implemente los controladores para los eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> del componente <xref:System.ComponentModel.BackgroundWorker>.  
  
     El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> permanece desactivado durante la cantidad de milisegundos especificada en `UpdatePeriod` y luego provoca el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, hasta que el código detiene la aplicación llamando al método <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> alterna el estado de iluminación y apagado del texto para proporcionar la apariencia de parpadeo.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. Reemplace el método <xref:System.Windows.Forms.Control.OnPaint%2A> para habilitar la animación.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. Presione F6 para compilar la solución.  
  
## Crear el control MarqueeBorder secundario  
 El control `MarqueeBorder` es ligeramente más complejo más que el control `MarqueeText`.  Tiene más propiedades y el método <xref:System.Windows.Forms.Control.OnPaint%2A> presenta más animación.  En principio, es bastante similar al control `MarqueeText`.  
  
 Dado que el control `MarqueeBorder` puede tener controles secundarios, necesita darse cuenta de los eventos <xref:System.Windows.Forms.Control.Layout>.  
  
#### Para crear el control MarqueeBorder  
  
1.  Agregue un nuevo elemento **Control personalizado** al proyecto `MarqueeControlLibrary`.  Dé el nombre base de "MarqueeControl" al nuevo archivo de código fuente.  
  
2.  Arrastre un componente <xref:System.ComponentModel.BackgroundWorker> desde el **Cuadro de herramientas** al control `MarqueeBorder`.  Este componente permitirá al control `MarqueeBorder` actualizarse de forma asincrónica.  
  
3.  En la ventana Propiedades, establezca las propiedades `WorkerReportsProgess` y <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente <xref:System.ComponentModel.BackgroundWorker> en `true`.  Esta configuración permite al componente <xref:System.ComponentModel.BackgroundWorker> provocar periódicamente el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y cancelar las actualizaciones asincrónicas.  Para obtener más información, vea [BackgroundWorker \(Componente\)](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
4.  En la ventana Propiedades, haga clic en el botón Eventos.  Asocie controladores para los eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.  
  
5.  Abra el archivo de código fuente `MarqueeBorder` en el **Editor de código**.  En la parte superior del archivo, importe los espacios de nombres siguientes:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  Cambie la declaración de `MarqueeBorder` para heredar de <xref:System.Windows.Forms.Panel> e implementar la interfaz `IMarqueeWidget`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  Declare dos enumeraciones para administrar el estado del control `MarqueeBorder`: `MarqueeSpinDirection`, que determina la dirección en la que la luz "gira" alrededor del borde, y `MarqueeLightShape`, que determina la forma de las luces \(cuadradas o circulares\).  Coloque estas declaraciones antes de la declaración de clase `MarqueeBorder`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  Declare las variables de instancia que corresponden a las propiedades expuestas e inicialícelas en el constructor.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. Implemente la interfaz `IMarqueeWidget`.  
  
     Los métodos `StartMarquee` y `StopMarquee` invocan los métodos <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> y <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> del componente <xref:System.ComponentModel.BackgroundWorker> para iniciar y detener la aplicación.  
  
     Como el control `MarqueeBorder` puede contener controles secundarios, el método `StartMarquee` enumera todos los controles secundarios y llama a `StartMarquee` en aquellos que implementa `IMarqueeWidget`.  El método `StopMarquee` tiene una implementación similar.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. Implemente los descriptores de acceso de propiedad.  El control `MarqueeBorder` dispone de varias propiedades para controlar su apariencia.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. Implemente los controladores para los eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> del componente <xref:System.ComponentModel.BackgroundWorker>.  
  
     El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> permanece desactivado durante la cantidad de milisegundos especificada en `UpdatePeriod` y luego provoca el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, hasta que el código detiene la aplicación llamando al método <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> aumenta la posición de la luz "base", desde la cual se determina el estado iluminado\/oscuro de las otras luces, y llama al método <xref:System.Windows.Forms.Control.Refresh%2A> para hacer que el control se pinte a sí mismo.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. Implemente los métodos auxiliares `IsLit` y `DrawLight`.  
  
     El método `IsLit` determina el color de una luz en una posición determinada.  Las luces que se "encienden" se representan en el color proporcionado por la propiedad `LightColor`, y los que son "oscuros" se representan en el color proporcionado por la propiedad `DarkColor`.  
  
     El método `DrawLight` dibuja una luz utilizando el color, la forma y la posición adecuados.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. Utilice los métodos <xref:System.Windows.Forms.Control.OnLayout%2A> y <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
     El método <xref:System.Windows.Forms.Control.OnPaint%2A> dibuja las luces a lo largo de los bordes del control `MarqueeBorder`.  
  
     Dado que el método <xref:System.Windows.Forms.Control.OnPaint%2A> depende de las dimensiones del control `MarqueeBorder`, necesita llamarlo cada vez que el diseño cambia.  Para ello, reemplace las llamadas a los métodos <xref:System.Windows.Forms.Control.OnLayout%2A> y <xref:System.Windows.Forms.Control.Refresh%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## Crear un diseñador personalizado para sombrear y filtrar propiedades  
 La clase `MarqueeControlRootDesigner` proporciona la implementación para el diseñador raíz.  Además de este diseñador, que funciona en `MarqueeControl`, necesitará a un diseñador personalizado que se asocia específicamente al control `MarqueeBorder`.  Este diseñador proporciona comportamiento personalizado que es adecuado en el contexto del diseñador raíz personalizado.  
  
 Específicamente, `MarqueeBorderDesigner` sombreará y filtrará ciertas propiedades en el control `MarqueeBorder`, cambiando su interacción con el entorno de diseño.  
  
 Las llamadas que interceptan al descriptor de acceso de propiedad de un componente se conocen como "sombreado". Permite a un diseñador realizar el seguimiento del valor establecido por el usuario y opcionalmente pasa ese valor al componente que se está diseñando.  
  
 En este ejemplo, las propiedades <xref:System.Windows.Forms.Control.Visible%2A> y <xref:System.Windows.Forms.Control.Enabled%2A> se sombrearán por `MarqueeBorderDesigner`, que impide al usuario hacer invisible o deshabilitar el control `MarqueeBorder` durante el tiempo de diseño.  
  
 Los diseñadores también pueden agregar y quitar propiedades.  En este ejemplo, se quitará la propiedad <xref:System.Windows.Forms.Control.Padding%2A> en tiempo de diseño, porque el control `MarqueeBorder` establece mediante programación el relleno en función del tamaño de las luces especificado en la propiedad `LightSize`.  
  
 La clase base para `MarqueeBorderDesigner` es <xref:System.ComponentModel.Design.ComponentDesigner>, que tiene métodos que pueden cambiar los atributos, propiedades y eventos expuestos por un control en tiempo de diseño:  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 Al cambiar la interfaz pública de un componente utilizando estos métodos, debe seguir las reglas siguientes:  
  
-   Agregue o quite elementos únicamente en los métodos `PreFilter`  
  
-   Modifique los elementos existentes únicamente en los métodos `PostFilter`  
  
-   Siempre llame primero a la implementación base de los métodos `PreFilter`  
  
-   Siempre llame primero a la implementación base de los métodos `PostFilter`  
  
 El cumplimiento de estas reglas garantiza que todos los diseñadores en entorno en tiempo de diseño poseen una vista coherente de todos los componentes que se están diseñando.  
  
 La clase <xref:System.ComponentModel.Design.ComponentDesigner> proporciona un diccionario para administrar los valores de propiedades reemplazadas, lo que libera de la necesidad de crear variables de instancia específicas.  
  
#### Para crear a un diseñador personalizado para sombrear y filtrar propiedades  
  
1.  Haga clic con el botón secundario del mouse en la carpeta **Diseño** y agregue una nueva clase.  Dé el nombre base de "MarqueeBorderDesigner" al archivo de código fuente.  
  
2.  Abra el archivo de código fuente `MarqueeBorderDesigner` en el **Editor de código**.  En la parte superior del archivo, importe los espacios de nombres siguientes:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  Cambie la declaración de `MarqueeBorderDesigner` para heredar de <xref:System.Windows.Forms.Design.ParentControlDesigner>.  
  
     Dado que el control `MarqueeBorder` puede contener controles secundarios, `MarqueeBorderDesigner` hereda de <xref:System.Windows.Forms.Design.ParentControlDesigner>, que controla la interacción primaria\-secundaria.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  Reemplace la implementación base de <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  Implemente las propiedades <xref:System.Windows.Forms.Control.Enabled%2A> y <xref:System.Windows.Forms.Control.Visible%2A>.  Estas implementaciones sombrean las propiedades del control.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## Controlar los cambios de componente  
 La clase `MarqueeControlRootDesigner` proporciona experiencia en tiempo de diseño personalizada para las instancias de `MarqueeControl`.  La mayor parte de la funcionalidad en tiempo de diseño se hereda de la clase <xref:System.Windows.Forms.Design.DocumentDesigner>; el código implementará dos personalizaciones determinadas: la administración de los cambios de componentes y la adición de verbos del diseñador.  
  
 Cuando los usuarios diseñan las instancias de `MarqueeControl`, el diseñador raíz realizará el seguimiento de los cambios en `MarqueeControl` y sus controles secundarios.  El entorno en tiempo de diseño ofrece un práctico servicio, <xref:System.ComponentModel.Design.IComponentChangeService>, para realizar el seguimiento de los cambios al estado de componente.  
  
 Adquiere una referencia a este servicio consultando el entorno con el método <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>.  Si la consulta es correcta, el diseñador puede adjuntar un controlador al evento <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> y realizar las tareas necesarias para conservar un estado coherente en tiempo de diseño.  
  
 En el caso de la clase `MarqueeControlRootDesigner`, llame al método <xref:System.Windows.Forms.Control.Refresh%2A> en cada objeto `IMarqueeWidget` contenido por `MarqueeControl`.  Esto hará que el objeto `IMarqueeWidget` se vuelva a representar correctamente cuando se cambien propiedades como la propiedad <xref:System.Windows.Forms.Control.Size%2A> del elemento primario.  
  
#### Para controlar los cambios de componente  
  
1.  Abra el archivo de código fuente `MarqueeControlRootDesigner` en el **Editor de código** y reemplace el método <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>.  Llame a la implementación base del método <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> y consulte <xref:System.ComponentModel.Design.IComponentChangeService>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  Implemente el controlador de eventos <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>.  Pruebe el tipo del componente enviado y si es `IMarqueeWidget`, llame al método <xref:System.Windows.Forms.Control.Refresh%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## Agregar verbos del diseñador al diseñador personalizado  
 Un verbo del diseñador es un comando de menú vinculado a un controlador de eventos.  Los verbos del diseñador se agregan en tiempo de diseño al menú contextual de un componente.  Para obtener más información, vea <xref:System.ComponentModel.Design.DesignerVerb>.  
  
 Agregará dos verbos del diseñador a los diseñadores: **Ejecutar prueba** y **Detener prueba**.  Estos verbos le permitirán ver en tiempo de diseño el comportamiento en tiempo de ejecución de `MarqueeControl`.  Estos verbos se agregarán a `MarqueeControlRootDesigner`.  
  
 Cuando se invoca **Ejecutar prueba**, el controlador de eventos del verbo llamará al método `StartMarquee` en `MarqueeControl`.  Cuando se invoca **Detener prueba**, el controlador de eventos del verbo llamará al método `StopMarquee` en `MarqueeControl`.  La implementación de los métodos `StartMarquee` y `StopMarquee` llama a estos métodos en controles contenidos que implementan `IMarqueeWidget`, por tanto también participará en la prueba cualquier control `IMarqueeWidget` contenido.  
  
#### Para agregar verbos del diseñador a los diseñadores personalizados  
  
1.  En la clase `MarqueeControlRootDesigner`, agregue los controladores de eventos denominados `OnVerbRunTest` y `OnVerbStopTest`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  Conecte estos controladores de eventos a los verbos de diseñador correspondientes.  `MarqueeControlRootDesigner` hereda una colección <xref:System.ComponentModel.Design.DesignerVerbCollection> de su clase base.  Creará dos nuevos objetos <xref:System.ComponentModel.Design.DesignerVerb> y los agregará a esta colección en el método <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## Crear un UITypeEditor personalizado  
 Cuando crea una experiencia en tiempo de diseño personalizada para los usuarios, se aconseja crear una interacción personalizada con la ventana Propiedades.  Puede llevarlo a cabo creando un <xref:System.Drawing.Design.UITypeEditor>.  Para obtener más información, vea [How to: Create a UI Type Editor](../Topic/How%20to:%20Create%20a%20UI%20Type%20Editor.md).  
  
 El control `MarqueeBorder` expone varias propiedades en la ventana Propiedades.  Dos de estas propiedades, `MarqueeSpinDirection` y `MarqueeLightShape`, se representan por enumeraciones.  Para explicar el uso de un editor de tipos de la interfaz de usuario, la propiedad `MarqueeLightShape` tendrá una clase <xref:System.Drawing.Design.UITypeEditor> asociada.  
  
#### Para crear un editor de tipos de la interfaz de usuario personalizada  
  
1.  Abra el archivo de código fuente `MarqueeBorder` en el **Editor de código**.  
  
2.  En la definición de la clase `MarqueeBorder`, declare una clase llamada `LightShapeEditor` que deriva de <xref:System.Drawing.Design.UITypeEditor>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  Declare una variable de instancia <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> denominada `editorService`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  Reemplace el método <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>.  Esta implementación devuelve <xref:System.Drawing.Design.UITypeEditorEditStyle>, que indica al entorno de diseño cómo mostrar `LightShapeEditor`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  Reemplace el método <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>.  Esta implementación consulta en el entorno de diseño un objeto <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>.  Si es correcto, crea un `LightShapeSelectionControl`.  El método <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> se invoca para iniciar `LightShapeEditor`.  El valor devuelto de esta invocación se devuelve al entorno de diseño.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## Crear un control de vista para UITypeEditor personalizado  
  
1.  La propiedad `MarqueeLightShape` admite dos tipos de formas para la iluminación: `Square` y `Circle`.  Creará un control personalizado que se utilizará únicamente para mostrar gráficamente estos valores en la ventana Propiedades.  <xref:System.Drawing.Design.UITypeEditor> utilizará este control personalizado para interactuar con la ventana Propiedades.  
  
#### Para crear un control de vista para el editor de tipos de la interfaz de usuario personalizado  
  
1.  Agregue un nuevo elemento <xref:System.Windows.Forms.UserControl> al proyecto `MarqueeControlLibrary`.  Dé el nombre base de "LightShapeSelectionControl" al nuevo archivo de código fuente.  
  
2.  Arrastre dos controles <xref:System.Windows.Forms.Panel> desde el **Cuadro de herramientas** a `LightShapeSelectionControl`.  Denomínelos `squarePanel` y `circlePanel`.  Organícelos en paralelo.  Establezca la propiedad <xref:System.Windows.Forms.Control.Size%2A> de ambos controles <xref:System.Windows.Forms.Panel> en \(60, 60\).  Establezca la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control `squarePanel` en \(8, 10\).  Establezca la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control `circlePanel` en \(80, 10\).  Finalmente, establezca la propiedad <xref:System.Windows.Forms.Control.Size%2A> de `LightShapeSelectionControl` en \(150, 80\).  
  
3.  Abra el archivo de código fuente de `LightShapeSelectionControl` en el **Editor de código**.  En la parte superior del archivo, importe el espacio de nombres <xref:System.Windows.Forms.Design?displayProperty=fullName>:  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  Implemente los controladores de eventos <xref:System.Windows.Forms.Control.Click> de los controles `squarePanel` y `circlePanel`.  Estos métodos invocan <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> para finalizar la sesión de edición de <xref:System.Drawing.Design.UITypeEditor> personalizada.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  Declare una variable de instancia <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> denominada `editorService`.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  Declare una variable de instancia `MarqueeLightShape` denominada `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  En el constructor `LightShapeSelectionControl`, asocie los controladores de eventos <xref:System.Windows.Forms.Control.Click> a los eventos <xref:System.Windows.Forms.Control.Click> de los controles `squarePanel` y `circlePanel`.  Asimismo, defina una sobrecarga del constructor que asigne el valor de `MarqueeLightShape` del entorno de diseño al campo `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  En el método <xref:System.ComponentModel.Component.Dispose%2A>, desasocie los controladores de eventos <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  Abra el archivo LightShapeSelectionControl.Designer.cs o LightShapeSelectionControl.Designer.vb y quite la definición predeterminada del método <xref:System.ComponentModel.Component.Dispose%2A>.  
  
5.  Implemente la propiedad `LightShape`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  Invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  Esta implementación dibujará un cuadrado y un círculo rellenos.  Resaltará también el valor seleccionado dibujando un borde alrededor de alguna de las dos formas.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## Probar el control personalizado en el diseñador  
 Llegado a este punto, puede compilar el proyecto `MarqueeControlLibrary`.  Pruebe la implementación; para ello, cree un control que herede de la clase `MarqueeControl` y utilícelo en un formulario.  
  
#### Para crear una implementación de MarqueeControl personalizada  
  
1.  Abra `DemoMarqueeControl` en el Diseñador de Windows Forms.  Esto creará una instancia del tipo `DemoMarqueeControl` y la mostrará en una instancia del tipo `MarqueeControlRootDesigner`.  
  
2.  En el **Cuadro de herramientas**, abra la ficha **Componentes de MarqueeControlLibrary**.  Verá los controles `MarqueeBorder` y `MarqueeText` disponibles para la selección.  
  
3.  Arrastre una instancia del control `MarqueeBorder` a la superficie de diseño `DemoMarqueeControl`.  Acople este control `MarqueeBorder` al control principal.  
  
4.  Arrastre una instancia del control `MarqueeText` a la superficie de diseño `DemoMarqueeControl`.  
  
5.  Compile la solución.  
  
6.  Haga clic con el botón secundario en `DemoMarqueeControl` y seleccione en el menú contextual la opción **Ejecutar prueba** para iniciar la animación.  Haga clic en **Detener prueba** para detener la animación.  
  
7.  Abra **Form1** en la vista Diseño.  
  
8.  Coloque dos controles <xref:System.Windows.Forms.Button> en el formulario.  Asígneles los nombres `startButton` y `stopButton`, y cambie los valores de propiedad <xref:System.Windows.Forms.Control.Text%2A> a Iniciar y Detener, respectivamente.  
  
9. Implemente los controladores de eventos <xref:System.Windows.Forms.Control.Click> para ambos controles <xref:System.Windows.Forms.Button>.  
  
10. En el **Cuadro de herramientas**, abra la ficha **Componentes de MarqueeControlTest**.  Verá el `DemoMarqueeControl` disponible para la selección.  
  
11. Arrastre una instancia de `DemoMarqueeControl` a la superficie de diseño de **Form1**.  
  
12. En los controladores de eventos <xref:System.Windows.Forms.Control.Click>, invoque los métodos `Start` y `Stop` en `DemoMarqueeControl`.  
  
```vb  
Private Sub startButton_Click(sender As Object, e As System.EventArgs)  
    Me.demoMarqueeControl1.Start()  
End Sub 'startButton_Click  
  
Private Sub stopButton_Click(sender As Object, e As System.EventArgs)  
Me.demoMarqueeControl1.Stop()  
End Sub 'stopButton_Click  
```  
  
```csharp  
private void startButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Start();  
}  
  
private void stopButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Stop();  
}  
```  
  
1.  Establezca el proyecto `MarqueeControlTest` como el proyecto de inicio y ejecútelo.  Verá que en el formulario se muestra `DemoMarqueeControl`.  Haga clic en el botón **Iniciar** para iniciar la animación.  Debe ver que el texto parpadea y que las luces se mueven por el borde.  
  
## Pasos siguientes  
 `MarqueeControlLibrary` muestra una implementación simple de controles personalizados y de los diseñadores asociados.  Hay varias formas de realizar este ejemplo más complejo:  
  
-   Cambie los valores de propiedad para `DemoMarqueeControl` en el diseñador.  Agregue más controles `MarqueBorder` y acóplelos dentro de sus instancias primarias para crear un efecto anidado.  Experimente con distintas configuraciones para `UpdatePeriod` y las propiedades relacionadas con la iluminación.  
  
-   Cree sus propias implementaciones de `IMarqueeWidget`.  Por ejemplo, podría crear un "signo de neón" parpadeante o un signo animado con varias imágenes.  
  
-   Siga personalizando la experiencia en tiempo de diseño.  Otra posibilidad es sombrear otras propiedades que no sean <xref:System.Windows.Forms.Control.Enabled%2A> y <xref:System.Windows.Forms.Control.Visible%2A> y agregar las nuevas propiedades.  Agregue nuevos verbos del diseñador para simplificar las tareas comunes como el acoplamiento de controles secundarios.  
  
-   Otorgue licencias `MarqueeControl`.  Para obtener más información, vea [How to: License Components and Controls](../Topic/How%20to:%20License%20Components%20and%20Controls.md).  
  
-   Controle cómo se serializan los controles y cómo se genera el código para ellos.  Para obtener más información, vea [Dynamic Source Code Generation and Compilation](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).  
  
## Vea también  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Design.ParentControlDesigner>   
 <xref:System.Windows.Forms.Design.DocumentDesigner>   
 <xref:System.ComponentModel.Design.IRootDesigner>   
 <xref:System.ComponentModel.Design.DesignerVerb>   
 <xref:System.Drawing.Design.UITypeEditor>   
 <xref:System.ComponentModel.BackgroundWorker>   
 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Custom Designers](../Topic/Custom%20Designers.md)   
 [.NET Shape Library: A Sample Designer](http://windowsforms.net/articles/shapedesigner.aspx)