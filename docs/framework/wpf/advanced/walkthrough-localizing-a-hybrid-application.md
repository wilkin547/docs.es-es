---
title: "Tutorial: Localizar una aplicación híbrida"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d46ea30a0e6a509d6a6cac6d8686e5f5307f0cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Tutorial: Localizar una aplicación híbrida
En este tutorial se muestra cómo localizar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos en un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-aplicación híbrida basada en.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proyecto host.  
  
-   Agregar contenido localizable.  
  
-   Habilitar la localización.  
  
-   Asignar identificadores de recursos.  
  
-   Usar la herramienta LocBaml para generar un ensamblado satélite.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [localizar un ejemplo de aplicación híbrido](http://go.microsoft.com/fwlink/?LinkID=160015).  
  
 Cuando haya terminado, tendrá una aplicación híbrida localizada.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-windows-forms-host-project"></a>Crear el proyecto del host de Windows Forms  
 El primer paso es crear el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aplicación del proyecto y agregue un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento con contenido que se va a localizar.  
  
#### <a name="to-create-the-host-project"></a>Para crear el proyecto del host  
  
1.  Cree un proyecto de aplicación WPF denominado `LocalizingWpfInWf`. Para obtener más información, consulta [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Agregar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> elemento denominado `SimpleControl` al proyecto.  
  
3.  Use la <xref:System.Windows.Forms.Integration.ElementHost> control se coloque un `SimpleControl` elemento en el formulario. Para obtener más información, consulte [Tutorial: hospedar un Control compuesto 3D de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).  
  
## <a name="adding-localizable-content"></a>Agregar contenido localizable  
 A continuación, agregará un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control de etiqueta y establezca el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido del elemento en una cadena localizable.  
  
#### <a name="to-add-localizable-content"></a>Para agregar contenido localizable  
  
1.  En el Explorador de soluciones, haga doble clic en **SimpleControl.xaml** para abrirlo en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Establecer el contenido de la <xref:System.Windows.Controls.Button> controlar mediante el código siguiente.  
  
     [!code-xaml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  En el Explorador de soluciones, haga doble clic en **Form1** para abrirlo en el Diseñador de Windows Forms.  
  
4.  Abra el cuadro de herramientas y haga doble clic en **etiqueta** para agregar un control de etiqueta al formulario. Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `"Hello"`.  
  
5.  Presione F5 para compilar y ejecutar la aplicación.  
  
     Tanto el `SimpleControl` elemento y el control de etiqueta muestran el texto **"Hello"**.  
  
## <a name="enabling-localization"></a>Habilitar la localización  
 El Diseñador de Windows Forms proporciona opciones para habilitar la localización en un ensamblado satélite.  
  
#### <a name="to-enable-localization"></a>Para habilitar la localización  
  
1.  En el Explorador de soluciones, haga doble clic en **Form1.cs** para abrirlo en el Diseñador de Windows Forms.  
  
2.  En la ventana Propiedades, establezca el valor de la forma **Localizable** propiedad `true`.  
  
3.  En la ventana Propiedades, establezca el valor de la **lenguaje** propiedad **español (España)**.  
  
4.  En el Diseñador de Windows Forms, seleccione el control de etiqueta.  
  
5.  En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.Control.Text%2A> propiedad `"Hola"`.  
  
     Se ha agregado al proyecto un nuevo archivo de recursos denominado Form1.es-ES.resx.  
  
6.  En el Explorador de soluciones, haga clic en **Form1.cs** y haga clic en **ver código** para abrirlo en el Editor de código.  
  
7.  Copie el código siguiente en el `Form1` constructor, anterior a la llamada a `InitializeComponent`.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  En el Explorador de soluciones, haga clic en **LocalizingWpfInWf** y haga clic en **descargar el proyecto**.  
  
     El nombre del proyecto con la etiqueta **(no disponible)**.  
  
9. Haga clic en **LocalizingWpfInWf**y haga clic en **editar LocalizingWpfInWf.csproj**.  
  
     El archivo del proyecto se abre en el Editor de código.  
  
10. Copie la siguiente línea en la primera `PropertyGroup` en el archivo de proyecto.  
  
    ```xml  
    <UICulture>en-US</UICulture>   
    ```  
  
11. Guarde el archivo del proyecto y ciérrelo.  
  
12. En el Explorador de soluciones, haga clic en **LocalizingWpfInWf** y haga clic en **recargar el proyecto**.  
  
## <a name="assigning-resource-identifiers"></a>Asignar identificadores de recursos  
 Puede asignar el contenido localizable a ensamblados de recursos usando identificadores de recursos. La aplicación MsBuild.exe asigna automáticamente los identificadores de recursos cuando se especifica la `updateuid` opción.  
  
#### <a name="to-assign-resource-identifiers"></a>Para asignar identificadores de recursos  
  
1.  En el menú Inicio, abra el [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] símbolo del sistema.  
  
2.  Use el siguiente comando para asignar identificadores de recursos al contenido localizable.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  En el Explorador de soluciones, haga doble clic en **SimpleControl.xaml** para abrirlo en el Editor de código. Verá que la `msbuild` comando agregada la `Uid` a todos los elementos de atributo. Esto facilita la localización mediante la asignación de identificadores de recursos.  
  
     [!code-xaml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  Presione F6 para compilar la solución.  
  
## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Usar LocBaml para generar un ensamblado satélite  
 El contenido localizado se almacena en un recurso solo *ensamblado satélite*. Use la herramienta de línea de comandos LocBaml.exe para generar un ensamblado localizado para su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido.  
  
#### <a name="to-produce-a-satellite-assembly"></a>Para generar un ensamblado satélite  
  
1.  Copie LocBaml.exe en la carpeta obj\Debug del proyecto. Para obtener más información, consulte [adaptar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
2.  En la ventana del símbolo del sistema, use el siguiente comando para extraer las cadenas de recursos en un archivo temporal.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  Abra el archivo temp.csv con [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] u otro editor de texto. Reemplace la cadena `"Hello"` con su traducción al español, `"Hola"`.  
  
4.  Guarde el archivo temp.csv.  
  
5.  Use el siguiente comando para generar el archivo de recursos localizado.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     El archivo LocalizingWpfInWf.g.es-ES.resources se crea en la carpeta obj\Debug.  
  
6.  Use el siguiente comando para compilar el ensamblado satélite localizado.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     El archivo LocalizingWpfInWf.resources.dll se crea en la carpeta obj\Debug.  
  
7.  Copie el archivo LocalizingWpfInWf.resources.dll en la carpeta bin\Debug\es-ES del proyecto. Reemplace el archivo existente.  
  
8.  Ejecute LocalizingWpfInWf.exe, que se encuentra en la carpeta bin\Debug del proyecto. No vuelva a compilar la aplicación; de lo contrario, el ensamblado satélite se sobrescribirá.  
  
     La aplicación muestra las cadenas localizadas en lugar de las cadenas en inglés.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)  
 [Tutorial: Adaptar formularios Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)  
 [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
