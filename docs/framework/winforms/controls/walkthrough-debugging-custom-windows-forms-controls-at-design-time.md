---
title: "Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc5f0fab7c380268dfc041d6105595858c2fed93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño
Cuando se crea un control personalizado, a menudo encontrará es necesario para depurar su comportamiento en tiempo de diseño. Esto es especialmente cierto si va a crear un diseñador personalizado para el control personalizado. Para obtener más información, consulte [Tutorial: crear un Windows Forms Control que toma ventaja de tiempo de diseño características de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
 Puede depurar sus controles personalizados mediante Visual Studio, tal y como se harían otras clases de .NET Framework. La diferencia es que depurará una instancia independiente de Visual Studio que está ejecutando código del control personalizado  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms para hospedar el control personalizado  
  
-   Crear un proyecto de biblioteca de controles  
  
-   Agregar una propiedad al control personalizado  
  
-   Agregar el control personalizado al formulario de host  
  
-   Configurar el proyecto para la depuración en tiempo de diseño  
  
-   Depurar el control personalizado en tiempo de diseño  
  
 Cuando haya terminado, tendrá un conocimiento de las tareas necesarias para depurar el comportamiento en tiempo de diseño de un control personalizado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de aplicación. Este proyecto se utilizará para compilar la aplicación que hospeda el control personalizado.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Cree un proyecto de aplicación de Windows denominado "DebuggingExample". Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## <a name="creating-a-control-library-project"></a>Crear un proyecto de biblioteca de controles  
 El siguiente paso es crear el proyecto de biblioteca de controles y configurar el control personalizado.  
  
#### <a name="to-create-the-control-library-project"></a>Para crear el proyecto de biblioteca de controles  
  
1.  Agregar un **biblioteca de controles de Windows** proyecto a la solución.  
  
2.  Agregue un nuevo **UserControl** elemento al proyecto DebugControlLibrary. Para obtener más información, consulte [NIB: Cómo: agregar nuevos elementos de proyecto](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Asigne al archivo de origen nuevo un nombre de base de "DebugControl".  
  
3.  Mediante el **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código con un nombre de base de "`UserControl1`". Para obtener más información, consulte [NIB: Cómo: quitar, eliminar y excluir elementos](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
4.  Compile la solución.  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, podrá ver el control personalizado en el **cuadro de herramientas**.  
  
#### <a name="to-check-your-progress"></a>Para comprobar su progreso  
  
-   Busque la nueva ficha denominada **componentes de DebugControlLibrary** y haga clic para seleccionarlo. Cuando se abre, verá el control aparece como **DebugControl** con el icono predeterminado junto a él.  
  
## <a name="adding-a-property-to-your-custom-control"></a>Agregar una propiedad al Control personalizado  
 Para demostrar que se está ejecutando código del control personalizado en tiempo de diseño, agregará una propiedad y establezca un punto de interrupción en el código que implementa la propiedad.  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>Para agregar una propiedad al control personalizado  
  
1.  Abra **DebugControl** en el **Editor de código**. Agregue el código siguiente a la definición de clase:  
  
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
  
## <a name="adding-your-custom-control-to-the-host-form"></a>Agregar el Control personalizado al formulario de Host  
 Para depurar el comportamiento en tiempo de diseño del control personalizado, deberá colocar una instancia de la clase de control personalizado en un formulario de host.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>Para agregar el control personalizado en el formulario de host  
  
1.  En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.  
  
2.  En el **cuadro de herramientas**, abra el **componentes de DebugControlLibrary** pestaña y arrastre un **DebugControl** instancia en el formulario.  
  
3.  Buscar el `DemoString` propiedad personalizada en el **propiedades** ventana. Tenga en cuenta que puede cambiar el valor tal y como lo haría con cualquier otra propiedad. Tenga en cuenta también que, cuando la `DemoString` propiedad está seleccionada, la cadena de descripción de la propiedad aparece en la parte inferior de la **propiedades** ventana.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Configurar el proyecto para la depuración en tiempo de diseño  
 Para depurar el comportamiento en tiempo de diseño del control personalizado, que desea depurar una instancia independiente de Visual Studio que está ejecutando código del control personalizado.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>Para configurar el proyecto para la depuración en tiempo de diseño  
  
1.  Haga doble clic en el **DebugControlLibrary** del proyecto en el **el Explorador de soluciones** y seleccione **propiedades**.  
  
2.  En el **DebugControlLibrary** hoja de propiedades, seleccione la **depurar** ficha.  
  
     En el **acción de inicio** sección, seleccione **iniciar programa externo**. Estará depurando una instancia independiente de Visual Studio, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) botón para buscar el IDE de Visual Studio. El nombre del archivo ejecutable es **devenv.exe**, y si ha instalado en la ubicación predeterminada, su ruta de acceso es %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.  
  
3.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
4.  Haga clic en el **DebugControlLibrary** de proyecto y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>Depurar el Control personalizado en tiempo de diseño  
 Ahora está listo para depurar el control personalizado mientras se ejecuta en modo de diseño. Cuando se inicia la sesión de depuración, se creará una nueva instancia de Visual Studio, y podrá utilizarla para cargar la solución "DebuggingExample". Cuando abra Form1 en el **Diseñador de formularios**, una instancia del control personalizado se crearán y empezará a ejecutarse.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>Para depurar el control personalizado en tiempo de diseño  
  
1.  Abra la **DebugControl** archivo de código fuente en el **Editor de código** y establecer un punto de interrupción en la `Set` descriptor de acceso de la `DemoString` propiedad.  
  
2.  Presione F5 para iniciar la sesión de depuración. Tenga en cuenta que se crea una nueva instancia de Visual Studio. Puede distinguir entre las instancias de dos maneras:  
  
    -   La instancia de depuración tiene la palabra **ejecutando** en su barra de título  
  
    -   La instancia de depuración tiene la **iniciar** situado en su **depurar** deshabilitado de la barra de herramientas  
  
     El punto de interrupción se establece en la instancia de depuración.  
  
3.  En la nueva instancia de Visual Studio, abra la solución "DebuggingExample". Puede encontrar fácilmente la solución seleccionando **proyectos recientes** desde el **archivo** menú. El archivo de solución "DebuggingExample.sln" se mostrará como los archivos usados recientemente.  
  
4.  Abra Form1 en el **Diseñador de formularios** y seleccione la **DebugControl** control.  
  
5.  Cambie el valor de la `DemoString` propiedad. Tenga en cuenta que cuando se confirma el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción. Puede paso a paso a través del descriptor de acceso de propiedad al igual que la haría cualquier otro código.  
  
6.  Cuando haya terminado con la sesión de depuración, puede salir descartando la instancia de host de Visual Studio o haciendo clic en el **Detener depuración** botón en la instancia de depuración.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que puede depurar los controles personalizados en tiempo de diseño, hay muchas posibilidades de ampliar la interacción del control con el IDE de Visual Studio.  
  
-   Puede usar el <xref:System.ComponentModel.Component.DesignMode%2A> propiedad de la <xref:System.ComponentModel.Component> clase para escribir código que solo se ejecutará en tiempo de diseño. Para obtener información detallada, vea <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Hay varios atributos puede aplicar a las propiedades del control para manipular la interacción del control personalizado con el diseñador. Puede encontrar estos atributos en el <xref:System.ComponentModel?displayProperty=nameWithType> espacio de nombres.  
  
-   Puede escribir un diseñador personalizado para el control personalizado. Esto proporciona un control completo sobre la experiencia de diseño mediante la infraestructura del diseñador extensible expuesta por Visual Studio. Para obtener más información, consulte [Tutorial: crear un Windows Forms Control que toma ventaja de tiempo de diseño características de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [Cómo: obtener acceso a servicios en tiempo de diseño](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [Cómo: obtener acceso a la compatibilidad en tiempo de diseño en formularios Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
