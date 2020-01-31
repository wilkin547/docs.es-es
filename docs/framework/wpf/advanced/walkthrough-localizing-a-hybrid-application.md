---
title: 'Tutorial: Localizar una aplicación híbrida'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: b406d539f2446824027e9462c8ecbe20c18cfb27
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794124"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Tutorial: Localizar una aplicación híbrida

En este tutorial se muestra cómo localizar elementos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una aplicación híbrida basada en Windows Forms.

Las tareas ilustradas en este tutorial incluyen:

- Crear el proyecto de host de Windows Forms.

- Agregar contenido localizable.

- Habilitar la localización.

- Asignar identificadores de recursos.

- Usar la herramienta LocBaml para generar un ensamblado satélite.

Para obtener una lista de código completa de las tareas ilustradas en este tutorial, consulte [localizar una aplicación híbrida de ejemplo](https://go.microsoft.com/fwlink/?LinkID=160015).

Cuando haya terminado, tendrá una aplicación híbrida localizada.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Crear el proyecto del host de Windows Forms

El primer paso consiste en crear el proyecto de aplicación de Windows Forms y agregar un elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con el contenido que se va a localizar.

### <a name="to-create-the-host-project"></a>Para crear el proyecto del host

1. Cree un proyecto de **aplicación de WPF** denominado `LocalizingWpfInWf`.  (**Archivo** > **nuevo** **proyecto** de >  ** > C# visual** o **Visual Basic** > **aplicación WPF** > de **escritorio clásico** ).

2. Agregue un elemento de <xref:System.Windows.Controls.UserControl> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]denominado `SimpleControl` al proyecto.

3. Utilice el control <xref:System.Windows.Forms.Integration.ElementHost> para colocar un elemento `SimpleControl` en el formulario. Para obtener más información, vea [Tutorial: hospedar un control compuesto de WPF 3D en Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).

## <a name="adding-localizable-content"></a>Agregar contenido localizable

A continuación, agregará un control etiqueta de Windows Forms y establecerá el contenido del elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una cadena localizable.

### <a name="to-add-localizable-content"></a>Para agregar contenido localizable

1. En **Explorador de soluciones**, haga doble clic en **SimpleControl. Xaml** para abrirlo en el diseñador de WPF.

2. Establezca el contenido del control <xref:System.Windows.Controls.Button> mediante el código siguiente.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. En **Explorador de soluciones**, haga doble clic en **Form1** para abrirlo en el diseñador de Windows Forms.

4. Abra el **cuadro de herramientas** y haga doble clic en **etiqueta** para agregar un control etiqueta al formulario. Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `"Hello"`.

5. Presione **F5** para compilar y ejecutar la aplicación.

     Tanto el elemento `SimpleControl` como el control etiqueta muestran el texto **"Hello"** .

## <a name="enabling-localization"></a>Habilitar la localización

El Diseñador de Windows Forms proporciona opciones para habilitar la localización en un ensamblado satélite.

### <a name="to-enable-localization"></a>Para habilitar la localización

1. En **Explorador de soluciones**, haga doble clic en **Form1.CS** para abrirlo en el diseñador de Windows Forms.

2. En la ventana **propiedades** , establezca el valor de la propiedad **traducible** del formulario en `true`.

3. En la ventana **propiedades** , establezca el valor de la propiedad **idioma** en **Español (España)** .

4. En el Diseñador de Windows Forms, seleccione el control de etiqueta.

5. En la ventana **propiedades** , establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Text%2A> en `"Hola"`.

     Se ha agregado al proyecto un nuevo archivo de recursos denominado Form1.es-ES.resx.

6. En **Explorador de soluciones**, haga clic con el botón secundario en **Form1.CS** y haga clic en **Ver código** para abrirlo en el editor de código.

7. Copie el código siguiente en el constructor `Form1`, antes de la llamada a `InitializeComponent`.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. En **Explorador de soluciones**, haga clic con el botón secundario en **LocalizingWpfInWf** y haga clic en **descargar el proyecto**.

     El nombre del proyecto tiene la etiqueta **(no disponible)** .

9. Haga clic con el botón secundario en **LocalizingWpfInWf**y haga clic en **Editar LocalizingWpfInWf. csproj**.

     El archivo del proyecto se abre en el Editor de código.

10. Copie la siguiente línea en el primer `PropertyGroup` del archivo de proyecto.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Guarde el archivo del proyecto y ciérrelo.

12. En **Explorador de soluciones**, haga clic con el botón secundario en **LocalizingWpfInWf** y haga clic en **volver a cargar el proyecto**.

## <a name="assigning-resource-identifiers"></a>Asignar identificadores de recursos

Puede asignar el contenido localizable a ensamblados de recursos usando identificadores de recursos. La aplicación MsBuild. exe asigna automáticamente los identificadores de recursos cuando se especifica la opción `updateuid`.

### <a name="to-assign-resource-identifiers"></a>Para asignar identificadores de recursos

1. En el menú Inicio, abra el Símbolo del sistema para desarrolladores de Visual Studio.

2. Use el siguiente comando para asignar identificadores de recursos al contenido localizable.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. En **Explorador de soluciones**, haga doble clic en **SimpleControl. Xaml** para abrirlo en el editor de código. Verá que el comando `msbuild` ha agregado el atributo `Uid` a todos los elementos. Esto facilita la localización mediante la asignación de identificadores de recursos.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Presione **F6** para compilar la solución.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Usar LocBaml para generar un ensamblado satélite

El contenido localizado se almacena en un *ensamblado satélite*solo de recursos. Use la herramienta de línea de comandos LocBaml. exe para generar un ensamblado localizado para el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

### <a name="to-produce-a-satellite-assembly"></a>Para generar un ensamblado satélite

1. Copie LocBaml.exe en la carpeta obj\Debug del proyecto. Para obtener más información, consulte [localizar una aplicación](how-to-localize-an-application.md).

2. En la ventana del símbolo del sistema, use el siguiente comando para extraer las cadenas de recursos en un archivo temporal.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Abra el archivo temp. csv con Visual Studio u otro editor de texto. Reemplace la cadena `"Hello"` por su traducción española `"Hola"`.

4. Guarde el archivo temp.csv.

5. Use el siguiente comando para generar el archivo de recursos localizado.

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     El archivo LocalizingWpfInWf.g.es-ES.resources se crea en la carpeta obj\Debug.

6. Use el siguiente comando para compilar el ensamblado satélite localizado.

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     El archivo LocalizingWpfInWf.resources.dll se crea en la carpeta obj\Debug.

7. Copie el archivo LocalizingWpfInWf.resources.dll en la carpeta bin\Debug\es-ES del proyecto. Reemplace el archivo existente.

8. Ejecute LocalizingWpfInWf.exe, que se encuentra en la carpeta bin\Debug del proyecto. No vuelva a compilar la aplicación; de lo contrario, el ensamblado satélite se sobrescribirá.

     La aplicación muestra las cadenas localizadas en lugar de las cadenas en inglés.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Localizar una aplicación](how-to-localize-an-application.md)
- [Tutorial: localizar Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
