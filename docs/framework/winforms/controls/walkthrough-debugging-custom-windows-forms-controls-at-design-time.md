---
title: 'Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
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
ms.openlocfilehash: ceee83c9deb318f5912eb724cbd237c3d7b73152
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733342"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño
Cuando se crea un control personalizado, a menudo encontrará lo necesario para depurar su comportamiento en tiempo de diseño. Esto es especialmente cierto si va a crear un diseñador personalizado para el control personalizado. Para obtener más información, consulte [Tutorial: Crear un Windows Forms Control que aprovecha las características de tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
 Puede depurar sus controles personalizados mediante Visual Studio, simplemente como lo haría cualquier otras clases de .NET Framework. La diferencia es que desea depurar una instancia independiente de Visual Studio que se está ejecutando código del control personalizado  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de Windows Forms para hospedar el control personalizado  
  
-   Crear un proyecto de biblioteca de controles  
  
-   Agregar una propiedad al control personalizado  
  
-   Agregar el control personalizado al formulario de host  
  
-   Configurar el proyecto para la depuración de tiempo de diseño  
  
-   Depurar el control personalizado en tiempo de diseño  
  
 Cuando haya terminado, tendrá una comprensión de las tareas necesarias para depurar el comportamiento en tiempo de diseño de un control personalizado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de aplicación. Este proyecto se utilizará para compilar la aplicación que hospeda el control personalizado.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Cree un proyecto de aplicación de Windows denominado "DebuggingExample" (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).  
  
## <a name="creating-a-control-library-project"></a>Crear un proyecto de biblioteca de controles  
 El siguiente paso es crear el proyecto de biblioteca de controles y configurar el control personalizado.  
  
#### <a name="to-create-the-control-library-project"></a>Para crear el proyecto de biblioteca de control  
  
1.  Agregar un **biblioteca de controles de Windows** proyecto a la solución.  
  
2.  Agregue un nuevo **UserControl** al proyecto DebugControlLibrary. Para obtener más información, consulte [NIB: Cómo: Agregar nuevos elementos de proyecto](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Asigne el nuevo archivo de origen en un nombre de base de "DebugControl".  
  
3.  Mediante el **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código con el nombre de base "`UserControl1`". Para obtener más información, consulte [NIB: Cómo: Quitar, eliminar y excluir elementos](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
4.  Compile la solución.  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, podrá ver el control personalizado en el **cuadro de herramientas**.  
  
#### <a name="to-check-your-progress"></a>Para comprobar su progreso  
  
-   Busque la nueva pestaña denominada **DebugControlLibrary componentes** y haga clic para seleccionarlo. Cuando se abre, verá el control aparece como **DebugControl** con el icono predeterminado junto a él.  
  
## <a name="adding-a-property-to-your-custom-control"></a>Agregar una propiedad al Control personalizado  
 Para demostrar que se está ejecutando código del control personalizado en tiempo de diseño, agregará una propiedad y establecer un punto de interrupción en el código que implementa la propiedad.  
  
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
 Para depurar el comportamiento en tiempo de diseño del control personalizado, colocará una instancia de la clase de control personalizado en un formulario de host.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>Para agregar el control personalizado a la forma de host  
  
1.  En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.  
  
2.  En el **cuadro de herramientas**, abra el **DebugControlLibrary componentes** pestaña y arrastre un **DebugControl** instancia hasta el formulario.  
  
3.  Buscar el `DemoString` propiedad personalizada en el **propiedades** ventana. Tenga en cuenta que puede cambiar su valor como lo haría con cualquier otra propiedad. Tenga en cuenta también que, cuando el `DemoString` propiedad está seleccionada, la cadena de descripción de la propiedad aparece en la parte inferior de la **propiedades** ventana.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Configurar el proyecto para la depuración de tiempo de diseño  
 Para depurar el comportamiento en tiempo de diseño del control personalizado, que desea depurar una instancia independiente de Visual Studio que se está ejecutando código del control personalizado.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>Para configurar el proyecto para la depuración de tiempo de diseño  
  
1.  Haga doble clic en el **DebugControlLibrary** del proyecto en el **el Explorador de soluciones** y seleccione **propiedades**.  
  
2.  En el **DebugControlLibrary** hoja de propiedades, seleccione la **depurar** ficha.  
  
     En el **acción de inicio** sección, seleccione **iniciar programa externo**. Puede depurar una instancia independiente de Visual Studio, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) botón para buscar el IDE de Visual Studio. El nombre del archivo ejecutable es **devenv.exe**, y si ha instalado en la ubicación predeterminada, su ruta de acceso es %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.  
  
3.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
4.  Haga clic en el **DebugControlLibrary** del proyecto y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>Depurar el Control personalizado en tiempo de diseño  
 Ahora está listo para depurar el control personalizado mientras se ejecuta en modo de diseño. Al iniciar la sesión de depuración, se creará una nueva instancia de Visual Studio y se usará para cargar la solución "DebuggingExample". Cuando se abre Form1 en el **Diseñador de formularios**, una instancia del control personalizado se crea y se volverá a ejecutarse.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>Para depurar el control personalizado en tiempo de diseño  
  
1.  Abra el **DebugControl** archivo de código fuente en el **Editor de código** y coloque un punto de interrupción en el `Set` descriptor de acceso de la `DemoString` propiedad.  
  
2.  Presione F5 para iniciar la sesión de depuración. Tenga en cuenta que se crea una nueva instancia de Visual Studio. Puede distinguir entre las instancias de dos maneras:  
  
    -   La instancia de depuración con la palabra **ejecutando** en su barra de título  
  
    -   La instancia de depuración tiene el **iniciar** situado en su **depurar** deshabilitado de la barra de herramientas  
  
     El punto de interrupción se establece en la instancia de depuración.  
  
3.  En la nueva instancia de Visual Studio, abra la solución "DebuggingExample". Puede encontrar fácilmente la solución seleccionando **proyectos recientes** desde el **archivo** menú. El archivo de solución "DebuggingExample.sln" se mostrará como los archivos usados recientemente.  
  
4.  Abra Form1 en el **Diseñador de formularios** y seleccione el **DebugControl** control.  
  
5.  Cambie el valor de la propiedad `DemoString` . Tenga en cuenta que cuando se confirma el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción. Puede paso a paso a través del descriptor de acceso de propiedad al igual que su cualquier otro código.  
  
6.  Cuando haya terminado con la sesión de depuración, puede salir descartando la instancia hospedada de Visual Studio o haciendo clic en el **Detener depuración** botón en la instancia de depuración.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que puede depurar controles personalizados en tiempo de diseño, hay muchas posibilidades para expandir la interacción del control con el IDE de Visual Studio.  
  
-   Puede usar el <xref:System.ComponentModel.Component.DesignMode%2A> propiedad de la <xref:System.ComponentModel.Component> clase para escribir código que solo se ejecutará en tiempo de diseño. Para obtener información detallada, vea <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Hay varios atributos puede aplicar a las propiedades del control para manipular la interacción del control personalizado con el diseñador. Puede encontrar estos atributos en el <xref:System.ComponentModel?displayProperty=nameWithType> espacio de nombres.  
  
-   Puede escribir un diseñador personalizado para el control personalizado. Esto le ofrece control completo sobre la experiencia de diseño mediante la infraestructura del diseñador extensible expuesta por Visual Studio. Para obtener más información, consulte [Tutorial: Crear un Windows Forms Control que aprovecha las características de tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
## <a name="see-also"></a>Vea también
- [Tutorial: Crear un Control de Windows Forms que aproveche las características de tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)
- [Cómo: Acceso a servicios en tiempo de diseño](https://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)
- [Cómo: Compatibilidad de tiempo de diseño de acceso en Windows Forms](https://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
