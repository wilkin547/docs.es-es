---
title: Depurar controles personalizados en tiempo de diseño
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740187"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a>Tutorial: depurar controles de Windows Forms personalizados en tiempo de diseño

Al crear un control personalizado, a menudo es necesario depurar su comportamiento en tiempo de diseño. Esto es especialmente cierto si va a crear un diseñador personalizado para el control personalizado. Para obtener más información, vea [Tutorial: crear un control de Windows Forms que aprovecha las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).

Puede depurar los controles personalizados mediante Visual Studio, tal y como lo haría con cualquier otra clase de .NET Framework. La diferencia es que se depurará una instancia independiente de Visual Studio que ejecute el código del control personalizado.

## <a name="create-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto de la aplicación. Usará este proyecto para compilar la aplicación que hospeda el control personalizado.

En Visual Studio, cree un proyecto de aplicación para Windows y asígnele el nombre **DebuggingExample**.

## <a name="create-the-control-library-project"></a>Crear el proyecto de biblioteca de controles

1. Agregue un proyecto de **biblioteca de controles de Windows** a la solución.

2. Agregue un nuevo elemento **UserControl** al proyecto DebugControlLibrary. Asígnele el nombre **DebugControl**.

3. Para eliminar el control predeterminado del proyecto en **Explorador de soluciones**, elimine el archivo de código con un nombre base de UserControl1.

4. Compile la solución.

## <a name="checkpoint"></a>Punto de control

Llegados a este punto, podrá ver el control personalizado en el cuadro de **herramientas**.

Para comprobar el progreso, busque la nueva pestaña denominada **componentes de DebugControlLibrary** y haga clic para seleccionarla. Cuando se abra, verá que el control aparece como **DebugControl** con el icono predeterminado situado junto a él.

## <a name="add-a-property-to-your-custom-control"></a>Agregar una propiedad a un control personalizado

Para demostrar que el código del control personalizado se está ejecutando en tiempo de diseño, agregará una propiedad y establecerá un punto de interrupción en el código que implementa la propiedad.

1. Abra **DebugControl** en el **Editor de código**. Agregue el código siguiente a la definición de clase:

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

2. Compile la solución.

## <a name="add-your-custom-control-to-the-host-form"></a>Agregar el control personalizado al formulario de host

Para depurar el comportamiento en tiempo de diseño del control personalizado, colocará una instancia de la clase de control personalizada en un formulario host.

1. En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.

2. En el **cuadro de herramientas**, abra la pestaña **componentes de DebugControlLibrary** y arrastre una instancia de **DebugControl** al formulario.

3. Busque la propiedad personalizada `DemoString` en la ventana **propiedades** . Tenga en cuenta que puede cambiar su valor como lo haría con cualquier otra propiedad. Tenga en cuenta también que cuando se selecciona la propiedad `DemoString`, la cadena de descripción de la propiedad aparece en la parte inferior de la ventana **propiedades** .

## <a name="set-up-the-project-for-design-time-debugging"></a>Configurar el proyecto para la depuración en tiempo de diseño

Para depurar el comportamiento en tiempo de diseño del control personalizado, depurará una instancia independiente de Visual Studio que ejecute el código del control personalizado.

1. Haga clic con el botón derecho en el proyecto **DebugControlLibrary** en el **Explorador de soluciones** y seleccione **propiedades**.

2. En la hoja de propiedades **DebugControlLibrary** , seleccione la pestaña **depurar** .

     En la sección **acción de inicio** , seleccione **programa externo de inicio**. Va a depurar una instancia independiente de Visual Studio, por lo que debe hacer clic en los puntos suspensivos (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio](./media/visual-studio-ellipsis-button.png)) para buscar el IDE de Visual Studio. El nombre del archivo ejecutable es **devenv. exe**y, si lo instaló en la ubicación predeterminada, su ruta de acceso es *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<Edition > \Common7\IDE*.

3. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

4. Haga clic con el botón derecho en el proyecto **DebugControlLibrary** y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.

## <a name="debug-your-custom-control-at-design-time"></a>Depurar el control personalizado en tiempo de diseño

Ahora está listo para depurar el control personalizado mientras se ejecuta en modo de diseño. Al iniciar la sesión de depuración, se creará una nueva instancia de Visual Studio y se usará para cargar la solución "DebuggingExample". Cuando abra Form1 en el **Diseñador de formularios**, se creará una instancia del control personalizado y comenzará a ejecutarse.

1. Abra el archivo de origen **DebugControl** en el **Editor de código** y coloque un punto de interrupción en el descriptor de acceso `Set` de la propiedad `DemoString`.

2. Presione **F5** para iniciar la sesión de depuración. Se crea una nueva instancia de Visual Studio. Puede distinguir entre las instancias de dos maneras:

    - La instancia de depuración tiene la palabra en **ejecución** en la barra de título

    - La instancia de depuración tiene el botón **iniciar** en la barra de herramientas de **depuración** deshabilitada

   El punto de interrupción se establece en la instancia de depuración.

3. En la nueva instancia de Visual Studio, abra la solución "DebuggingExample". Puede encontrar fácilmente la solución seleccionando **proyectos recientes** en el menú **archivo** . El archivo de solución "DebuggingExample. sln" se mostrará como el archivo usado más recientemente.

4. Abra Form1 en el **Diseñador de formularios** y seleccione el control **DebugControl** .

5. Cambie el valor de la propiedad `DemoString` . Al confirmar el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción. Puede recorrer el descriptor de acceso de la propiedad de la misma forma que cualquier otro código.

6. Para detener la depuración, salga de la instancia hospedada de Visual Studio o seleccione el botón **detener depuración** en la instancia de depuración.

## <a name="next-steps"></a>Pasos siguientes

Ahora que puede depurar los controles personalizados en tiempo de diseño, hay muchas posibilidades de expandir la interacción del control con el IDE de Visual Studio.

- Puede usar la propiedad <xref:System.ComponentModel.Component.DesignMode%2A> de la clase <xref:System.ComponentModel.Component> para escribir código que solo se ejecutará en tiempo de diseño. Para obtener información detallada, vea <xref:System.ComponentModel.Component.DesignMode%2A>.

- Hay varios atributos que se pueden aplicar a las propiedades del control para manipular la interacción del control personalizado con el diseñador. Puede encontrar estos atributos en el espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>.

- Puede escribir un diseñador personalizado para el control personalizado. Esto le proporciona un control completo sobre la experiencia de diseño mediante la infraestructura de diseñador extensible expuesta por Visual Studio. Para obtener más información, vea [Tutorial: crear un control de Windows Forms que aprovecha las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).

## <a name="see-also"></a>Vea también

- [Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md)
