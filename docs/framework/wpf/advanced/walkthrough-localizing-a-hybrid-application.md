---
title: "Tutorial: Localizar una aplicaci&#243;n h&#237;brida | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicaciones híbridas [interoperabilidad con WPF]"
  - "localización [interoperabilidad con WPF]"
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Tutorial: Localizar una aplicaci&#243;n h&#237;brida
En este tutorial se muestra cómo localizar los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una aplicación híbrida basada en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto host de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Agregar el contenido localizable.  
  
-   Habilitar la localización.  
  
-   Asignar los identificadores de recursos.  
  
-   Utilizar la herramienta LocBaml para generar un ensamblado satélite.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [Localizing a Hybrid Application Sample](http://go.microsoft.com/fwlink/?LinkID=160015).  
  
 Al completar este tutorial, dispondrá de una aplicación híbrida localizada.  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Crear el proyecto host de formularios Windows Forms  
 El primer paso consiste en crear el proyecto de la aplicación de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y en agregar un elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con el contenido que se va a localizar.  
  
#### Para crear el proyecto host  
  
1.  Cree un proyecto de aplicación de WPF denominado `LocalizingWpfInWf`.  Para obtener más información, consulte [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Agregue un elemento <xref:System.Windows.Controls.UserControl> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominado `SimpleControl` al proyecto.  
  
3.  Utilice el control <xref:System.Windows.Forms.Integration.ElementHost> para colocar un elemento `SimpleControl` en el formulario.  Para obtener más información, vea [Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).  
  
## Agregar contenido localizable  
 A continuación, agregará un control de etiqueta de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y se establecerá el contenido del elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una cadena localizable.  
  
#### Para agregar el contenido localizable  
  
1.  En el Explorador de soluciones, haga doble clic en el archivo **SimpleControl.xaml** para abrirlo en [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Establezca el contenido del control <xref:System.Windows.Controls.Button> mediante el código siguiente.  
  
     [!code-xml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  En el Explorador de soluciones, haga doble clic en **Form1** para abrirlo en el Diseñador de Windows Forms.  
  
4.  Abra el Cuadro de herramientas y haga doble clic en **Etiqueta** para agregar un control de etiqueta al formulario.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control en `"Hello"`.  
  
5.  Presione F5 para compilar y ejecutar la aplicación.  
  
     Tanto el elemento `SimpleControl` como el control de etiqueta muestran el texto **"Hello"**.  
  
## Habilitar la localización  
 El Diseñador de Windows Forms proporciona valores para habilitar la localización en un ensamblado satélite.  
  
#### Para habilitar la localización  
  
1.  En el Explorador de soluciones, haga doble clic en **Form1.cs** para abrirlo en el Diseñador de Windows Forms.  
  
2.  En la ventana Propiedades, establezca el valor de la propiedad **Localizable** del formulario en `true`.  
  
3.  En la ventana Propiedades, establezca el valor de la propiedad **Idioma** en **Español \(España\)**.  
  
4.  En el Diseñador de Windows Forms, seleccione el control de etiqueta.  
  
5.  En la ventana Propiedades, establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Text%2A> en `"Hola"`.  
  
     Se agrega al proyecto un nuevo archivo de recursos denominado Form1.es\-ES.resx.  
  
6.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **Form1.cs** y seleccione **Ver código** para abrirlo en el Editor de código.  
  
7.  Copie el código siguiente en el constructor `Form1`, antes de la llamada a `InitializeComponent`.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  En el Explorador de soluciones, haga clic con el botón secundario en **LocalizingWpfInWf** y seleccione **Descargar el proyecto**.  
  
     El nombre del proyecto tiene la etiqueta **\(no disponible\)**.  
  
9. Haga clic con el botón secundario en **LocalizingWpfInWf** y seleccione **Editar LocalizingWpfInWf.csproj**.  
  
     Se abre el archivo de proyecto en el Editor de código.  
  
10. Copie la línea siguiente en el primer `PropertyGroup` del archivo de proyecto.  
  
    ```  
    <UICulture>en-US</UICulture>   
    ```  
  
11. Guarde el archivo de proyecto y ciérrelo.  
  
12. En el Explorador de soluciones, haga clic con el botón secundario en **LocalizingWpfInWf** y seleccione **Volver a cargar el proyecto**.  
  
## Asignar identificadores de recursos  
 Puede asignar el contenido localizable a ensamblados de recursos utilizando identificadores de recursos.  La aplicación MsBuild.exe asigna automáticamente los identificadores de recursos cuando se especifica la opción `updateuid`.  
  
#### Para asignar los identificadores de recursos  
  
1.  En el menú Inicio, abra el símbolo del sistema de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
2.  Utilice el comando siguiente para asignar identificadores de recursos al contenido localizable.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  En el Explorador de soluciones, haga doble clic en el archivo **SimpleControl.xaml** para abrirlo en el Editor de código.  Observará que el comando `msbuild` ha agregado el atributo `Uid` a todos los elementos.  Esto facilita la localización mediante la asignación de identificadores de recursos.  
  
     [!code-xml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  Presione F6 para compilar la solución.  
  
## Utilizar LocBaml para generar un ensamblado satélite  
 El contenido localizado se almacena en un *ensamblado satélite* sólo de recursos.  Utilice la herramienta de la línea de comandos LocBaml.exe a fin de generar un ensamblado localizado para el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
#### Para generar un ensamblado satélite  
  
1.  Copie LocBaml.exe en la carpeta obj\\Debug del proyecto.  Para obtener más información, consulte [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
2.  En la ventana del símbolo del sistema, utilice el comando siguiente para extraer las cadenas de recursos a un archivo temporal.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  Abra el archivo temp.csv con [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] u otro editor de texto.  Reemplace la cadena `"Hello"` por su traducción al español, `"Hola"`.  
  
4.  Guarde el archivo temp.csv.  
  
5.  Utilice el comando siguiente para generar el archivo de recursos localizado.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     Se crea el archivo LocalizingWpfInWf.g.es\-ES.resources en la carpeta obj\\Debug.  
  
6.  Utilice el comando siguiente para compilar el ensamblado satélite localizado.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     Se crea el archivo LocalizingWpfInWf.resources.dll en la carpeta obj\\Debug.  
  
7.  Copie el archivo LocalizingWpfInWf.resources.dll en la carpeta bin\\Debug\\es\-ES del proyecto.  Reemplace el archivo existente.  
  
8.  Ejecute LocalizingWpfInWf.exe, que se encuentra en la carpeta bin\\Debug del proyecto.  No recompile la aplicación, pues de lo contrario se sobrescribirá el ensamblado satélite.  
  
     La aplicación muestra las cadenas localizadas en lugar de las cadenas en inglés.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/es-es/9a96220d-a19b-4de0-9f48-01e5d82679e5)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)