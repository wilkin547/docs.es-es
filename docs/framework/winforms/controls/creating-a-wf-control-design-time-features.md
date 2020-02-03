---
title: Crear un control que aproveche las características en tiempo de diseño de Visual Studio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7166b4203c54ab31f1d929c85cf1e6481ff120f8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744076"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Tutorial: crear un control que aproveche las características de tiempo de diseño

La experiencia en tiempo de diseño de un control personalizado se puede mejorar mediante la creación de un diseñador personalizado asociado.

En este artículo se muestra cómo crear un diseñador personalizado para un control personalizado. Implementará un tipo de `MarqueeControl` y una clase de diseñador asociada denominada `MarqueeControlRootDesigner`.

El tipo de `MarqueeControl` implementa una pantalla similar a una marquesina de teatro con luces animadas y texto intermitente.

El diseñador de este control interactúa con el entorno de diseño para proporcionar una experiencia personalizada en tiempo de diseño. Con el diseñador personalizado, puede ensamblar una implementación de `MarqueeControl` personalizado con luces animadas y texto intermitente en muchas combinaciones. Puede usar el control ensamblado en un formulario como cualquier otro control de Windows Forms.

Cuando haya terminado con este tutorial, el control personalizado tendrá un aspecto similar al siguiente:

![Aplicación que muestra una marquesina que indica el texto y los botones de inicio y detención.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Para obtener la lista de código completa, vea [Cómo: crear un control de Windows Forms que aprovecha las características en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).

## <a name="prerequisites"></a>Prerequisites

Para completar este tutorial, necesitará Visual Studio.

## <a name="create-the-project"></a>Creación del proyecto

El primer paso es crear el proyecto de la aplicación. Usará este proyecto para compilar la aplicación que hospeda el control personalizado.

En Visual Studio, cree un nuevo proyecto de aplicación de Windows Forms y asígnele el nombre **MarqueeControlTest**.

## <a name="create-the-control-library-project"></a>Crear el proyecto de biblioteca de controles

1. Agregue un proyecto de biblioteca de controles Windows Forms a la solución. Asigne al proyecto el nombre **MarqueeControlLibrary**.

2. Use **Explorador de soluciones**para eliminar el control predeterminado del proyecto eliminando el archivo de código fuente denominado "UserControl1.cs" o "UserControl1. VB", según el lenguaje que elija.

3. Agregue un nuevo elemento de <xref:System.Windows.Forms.UserControl> al proyecto de `MarqueeControlLibrary`. Asigne al nuevo archivo de código fuente un nombre base de **MarqueeControl**.

4. Con **Explorador de soluciones**, cree una nueva carpeta en el proyecto de `MarqueeControlLibrary`.

5. Haga clic con el botón secundario en la carpeta **diseño** y agregue una nueva clase. Asígnele el nombre **MarqueeControlRootDesigner**.

6. Tendrá que usar tipos del ensamblado System. Design, por lo que debe agregar esta referencia al proyecto `MarqueeControlLibrary`.

## <a name="reference-the-custom-control-project"></a>Referencia al proyecto de control personalizado

Usará el proyecto `MarqueeControlTest` para probar el control personalizado. El proyecto de prueba conocerá el control personalizado al agregar una referencia de proyecto al ensamblado `MarqueeControlLibrary`.

En el proyecto de `MarqueeControlTest`, agregue una referencia de proyecto al ensamblado `MarqueeControlLibrary`. Asegúrese de usar la pestaña **proyectos** del cuadro de diálogo **Agregar referencia** en lugar de hacer referencia al ensamblado de `MarqueeControlLibrary` directamente.

## <a name="define-a-custom-control-and-its-custom-designer"></a>Definir un control personalizado y su diseñador personalizado

El control personalizado se deriva de la clase <xref:System.Windows.Forms.UserControl>. Esto permite que el control contenga otros controles y proporciona a su control una gran cantidad de funcionalidad predeterminada.

El control personalizado tendrá un diseñador personalizado asociado. Esto le permite crear una experiencia de diseño única adaptada específicamente para su control personalizado.

Asocie el control a su diseñador mediante la clase <xref:System.ComponentModel.DesignerAttribute>. Dado que está desarrollando todo el comportamiento en tiempo de diseño del control personalizado, el diseñador personalizado implementará la interfaz <xref:System.ComponentModel.Design.IRootDesigner>.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Para definir un control personalizado y su diseñador personalizado

1. Abra el archivo de origen de `MarqueeControl` en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Agregue el <xref:System.ComponentModel.DesignerAttribute> a la declaración de clase `MarqueeControl`. Esto asocia el control personalizado a su diseñador.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Abra el archivo de origen de `MarqueeControlRootDesigner` en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Cambie la declaración de `MarqueeControlRootDesigner` para que hereden de la clase <xref:System.Windows.Forms.Design.DocumentDesigner>. Aplique el <xref:System.ComponentModel.ToolboxItemFilterAttribute> para especificar la interacción del diseñador con el **cuadro de herramientas**.

   > [!NOTE]
   > La definición de la clase `MarqueeControlRootDesigner` se ha incluido en un espacio de nombres denominado MarqueeControlLibrary. Design. Esta declaración coloca el diseñador en un espacio de nombres especial reservado para los tipos relacionados con el diseño.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Defina el constructor para la clase `MarqueeControlRootDesigner`. Inserte una instrucción <xref:System.Diagnostics.Trace.WriteLine%2A> en el cuerpo del constructor. Esto será útil para la depuración.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Crear una instancia de un control personalizado

1. Agregue un nuevo elemento de <xref:System.Windows.Forms.UserControl> al proyecto de `MarqueeControlTest`. Asigne al nuevo archivo de código fuente el nombre base de **DemoMarqueeControl**.

2. Abra el archivo `DemoMarqueeControl` en el **Editor de código**. En la parte superior del archivo, importe el espacio de nombres `MarqueeControlLibrary`:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Cambie la declaración de `DemoMarqueeControl` para que hereden de la clase `MarqueeControl`.

4. Compile el proyecto.

5. Abra Form1 en el Diseñador de Windows Forms.

6. Busque la pestaña **componentes de MarqueeControlTest** en el cuadro de **herramientas** y ábrala. Arrastre un `DemoMarqueeControl` desde el **cuadro de herramientas** hasta el formulario.

7. Compile el proyecto.

## <a name="set-up-the-project-for-design-time-debugging"></a>Configurar el proyecto para la depuración en tiempo de diseño

Al desarrollar una experiencia personalizada en tiempo de diseño, será necesario depurar los controles y componentes. Hay una manera sencilla de configurar el proyecto para permitir la depuración en tiempo de diseño. Para obtener más información, vea [Tutorial: depurar controles de Windows Forms personalizados en tiempo de diseño](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

1. Haga clic con el botón derecho en el proyecto `MarqueeControlLibrary` y seleccione **propiedades**.

2. En el cuadro de diálogo **páginas de propiedades de MarqueeControlLibrary** , seleccione la página **depurar** .

3. En la sección **acción de inicio** , seleccione **programa externo de inicio**. Va a depurar una instancia independiente de Visual Studio, por lo que debe hacer clic en los puntos suspensivos (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio](./media/visual-studio-ellipsis-button.png)) para buscar el IDE de Visual Studio. El nombre del archivo ejecutable es devenv. exe y, si lo instaló en la ubicación predeterminada, su ruta de acceso es *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<edition > \Common7\IDE\devenv.exe*.

4. Seleccione **Aceptar** para cerrar el cuadro de diálogo.

5. Haga clic con el botón derecho en el proyecto MarqueeControlLibrary y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.

## <a name="checkpoint"></a>Punto de control

Ahora está listo para depurar el comportamiento en tiempo de diseño del control personalizado. Una vez que haya determinado que el entorno de depuración está configurado correctamente, probará la asociación entre el control personalizado y el diseñador personalizado.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Para probar el entorno de depuración y la Asociación del diseñador

1. Abra el archivo de origen MarqueeControlRootDesigner en el **Editor de código** y coloque un punto de interrupción en la instrucción <xref:System.Diagnostics.Trace.WriteLine%2A>.

2. Presione **F5** para iniciar la sesión de depuración.

   Se crea una nueva instancia de Visual Studio.

3. En la nueva instancia de Visual Studio, abra la solución MarqueeControlTest. Puede encontrar fácilmente la solución seleccionando **proyectos recientes** en el menú **archivo** . El archivo de solución de MarqueeControlTest. sln se mostrará como el archivo usado más recientemente.

4. Abra el `DemoMarqueeControl` en el diseñador.

   La instancia de depuración de Visual Studio obtiene el foco y la ejecución se detiene en el punto de interrupción. Presione **F5** para continuar con la sesión de depuración.

En este punto, todo está en su lugar para desarrollar y depurar el control personalizado y su diseñador personalizado asociado. El resto de este artículo se centra en los detalles de la implementación de características del control y el diseñador.

## <a name="implement-the-custom-control"></a>Implementar el control personalizado

El `MarqueeControl` es un <xref:System.Windows.Forms.UserControl> con un poco de personalización. Expone dos métodos: `Start`, que inicia la animación de marquesina y `Stop`, que detiene la animación. Dado que el `MarqueeControl` contiene controles secundarios que implementan la interfaz `IMarqueeWidget`, `Start` y `Stop` enumeran cada control secundario y llaman a los métodos `StartMarquee` y `StopMarquee`, respectivamente, en cada control secundario que implementa `IMarqueeWidget`.

La apariencia de los controles `MarqueeBorder` y `MarqueeText` depende del diseño, por lo que `MarqueeControl` invalida el método <xref:System.Windows.Forms.Control.OnLayout%2A> y llama a <xref:System.Windows.Forms.Control.PerformLayout%2A> en los controles secundarios de este tipo.

Esta es la extensión de las personalizaciones de `MarqueeControl`. Las características de tiempo de ejecución se implementan mediante los controles `MarqueeBorder` y `MarqueeText`, y las características en tiempo de diseño se implementan mediante las clases `MarqueeBorderDesigner` y `MarqueeControlRootDesigner`.

### <a name="to-implement-your-custom-control"></a>Para implementar el control personalizado

1. Abra el archivo de origen de `MarqueeControl` en el **Editor de código**. Implemente los métodos `Start` y `Stop`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Invalide el método <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Crear un control secundario para el control personalizado

El `MarqueeControl` hospedará dos tipos de controles secundarios: el control `MarqueeBorder` y el control `MarqueeText`.

- `MarqueeBorder`: este control pinta un borde de "Lights" alrededor de los bordes. Las luces parpadean en secuencia, por lo que parecen moverse alrededor del borde. La velocidad a la que el parpadeo de las luces se controla mediante una propiedad denominada `UpdatePeriod`. Otras propiedades personalizadas determinan otros aspectos de la apariencia del control. Dos métodos, denominados `StartMarquee` y `StopMarquee`, controlan Cuándo se inicia y se detiene la animación.

- `MarqueeText`: este control pinta una cadena parpadeante. Al igual que el control de `MarqueeBorder`, la velocidad a la que parpadea el texto se controla mediante la propiedad `UpdatePeriod`. El control `MarqueeText` también tiene los métodos `StartMarquee` y `StopMarquee` en común con el control `MarqueeBorder`.

En tiempo de diseño, el `MarqueeControlRootDesigner` permite agregar estos dos tipos de control a un `MarqueeControl` en cualquier combinación.

Las características comunes de los dos controles se factorizan en una interfaz denominada `IMarqueeWidget`. Esto permite a los `MarqueeControl` detectar los controles secundarios relacionados con la marquesina y darles un tratamiento especial.

Para implementar la característica de animación periódica, usará <xref:System.ComponentModel.BackgroundWorker> objetos del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>. Podría usar objetos de <xref:System.Windows.Forms.Timer>, pero cuando haya muchos objetos `IMarqueeWidget`, es posible que el subproceso de la interfaz de usuario no pueda mantener el ritmo de la animación.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Para crear un control secundario para el control personalizado

1. Agregue un nuevo elemento de clase al proyecto `MarqueeControlLibrary`. Asigne al nuevo archivo de código fuente el nombre base "IMarqueeWidget".

2. Abra el archivo de origen de `IMarqueeWidget` en el **Editor de código** y cambie la declaración de `class` a `interface`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Agregue el código siguiente a la interfaz `IMarqueeWidget` para exponer dos métodos y una propiedad que manipula la animación de marquesina:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Agregue un nuevo elemento de **control personalizado** al proyecto `MarqueeControlLibrary`. Asigne el nombre base "MarqueeText" al nuevo archivo de código fuente.

5. Arrastre un componente de <xref:System.ComponentModel.BackgroundWorker> desde el **cuadro de herramientas** hasta el control `MarqueeText`. Este componente permitirá que el control de `MarqueeText` se actualice de forma asincrónica.

6. En la ventana **propiedades** , establezca las propiedades `WorkerReportsProgress` y <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente <xref:System.ComponentModel.BackgroundWorker> en **true**. Esta configuración permite al componente <xref:System.ComponentModel.BackgroundWorker> generar periódicamente el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y cancelar las actualizaciones asincrónicas.

   Para obtener más información, vea [BackgroundWorker (componente](backgroundworker-component.md)).

7. Abra el archivo de origen de `MarqueeText` en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Cambie la declaración de `MarqueeText` para que hereden de <xref:System.Windows.Forms.Label> y para implementar la interfaz `IMarqueeWidget`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Declare las variables de instancia que corresponden a las propiedades expuestas e inicialícela en el constructor. El campo `isLit` determina si el texto se va a pintar en el color dado por la propiedad `LightColor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implemente la interfaz `IMarqueeWidget`.

    Los métodos `StartMarquee` y `StopMarquee` invocan los métodos <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> y <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> del componente <xref:System.ComponentModel.BackgroundWorker> para iniciar y detener la animación.

    Los atributos <xref:System.ComponentModel.CategoryAttribute.Category%2A> y <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> se aplican a la propiedad `UpdatePeriod` de modo que aparezca en una sección personalizada de la ventana Propiedades denominada "Marquesina".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementar los descriptores de acceso de propiedad. Expondrá dos propiedades a los clientes: `LightColor` y `DarkColor`. Los atributos <xref:System.ComponentModel.CategoryAttribute.Category%2A> y <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> se aplican a estas propiedades, por lo que las propiedades aparecen en una sección personalizada de la ventana Propiedades denominada "Marquesina".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implemente los controladores para los eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y <xref:System.ComponentModel.BackgroundWorker.DoWork> del componente de <xref:System.ComponentModel.BackgroundWorker>.

    El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> suspende durante el número de milisegundos especificado por `UpdatePeriod`, a continuación, genera el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, hasta que el código detiene la animación mediante una llamada a <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> alterna el texto entre su estado claro y oscuro para dar la apariencia de parpadeo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A> para habilitar la animación.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Presione **F6** para compilar la solución.

## <a name="create-the-marqueeborder-child-control"></a>Crear el control secundario de MarqueeBorder

El control `MarqueeBorder` es ligeramente más sofisticado que el control `MarqueeText`. Tiene más propiedades y la animación en el método <xref:System.Windows.Forms.Control.OnPaint%2A> es más complicada. En principio, es bastante similar al control `MarqueeText`.

Dado que el control de `MarqueeBorder` puede tener controles secundarios, debe tener en cuenta los eventos de <xref:System.Windows.Forms.Control.Layout>.

### <a name="to-create-the-marqueeborder-control"></a>Para crear el control MarqueeBorder

1. Agregue un nuevo elemento de **control personalizado** al proyecto `MarqueeControlLibrary`. Asigne al nuevo archivo de código fuente el nombre base "MarqueeBorder".

2. Arrastre un componente de <xref:System.ComponentModel.BackgroundWorker> desde el **cuadro de herramientas** hasta el control `MarqueeBorder`. Este componente permitirá que el control de `MarqueeBorder` se actualice de forma asincrónica.

3. En la ventana **propiedades** , establezca las propiedades `WorkerReportsProgress` y <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente <xref:System.ComponentModel.BackgroundWorker> en **true**. Esta configuración permite al componente <xref:System.ComponentModel.BackgroundWorker> generar periódicamente el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y cancelar las actualizaciones asincrónicas. Para obtener más información, vea [BackgroundWorker (componente](backgroundworker-component.md)).

4. En la ventana **propiedades** , seleccione el botón **eventos** . Adjunte Controladores para los eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.

5. Abra el archivo de origen de `MarqueeBorder` en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Cambie la declaración de `MarqueeBorder` para que hereden de <xref:System.Windows.Forms.Panel> y para implementar la interfaz `IMarqueeWidget`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Declare dos enumeraciones para administrar el estado del control `MarqueeBorder`: `MarqueeSpinDirection`, que determina la dirección en la que las luces "giran" alrededor del borde y `MarqueeLightShape`, que determina la forma de las luces (cuadradas o circulares). Coloque estas declaraciones antes de la declaración de clase `MarqueeBorder`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Declare las variables de instancia que corresponden a las propiedades expuestas e inicialícela en el constructor.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implemente la interfaz `IMarqueeWidget`.

    Los métodos `StartMarquee` y `StopMarquee` invocan los métodos <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> y <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> del componente <xref:System.ComponentModel.BackgroundWorker> para iniciar y detener la animación.

    Dado que el control `MarqueeBorder` puede contener controles secundarios, el método `StartMarquee` enumera todos los controles secundarios y llama `StartMarquee` en los que implementan `IMarqueeWidget`. El método `StopMarquee` tiene una implementación similar.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementar los descriptores de acceso de propiedad. El control `MarqueeBorder` tiene varias propiedades para controlar su apariencia.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implemente los controladores para los eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> y <xref:System.ComponentModel.BackgroundWorker.DoWork> del componente de <xref:System.ComponentModel.BackgroundWorker>.

    El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork> suspende durante el número de milisegundos especificado por `UpdatePeriod`, a continuación, genera el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, hasta que el código detiene la animación mediante una llamada a <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    El controlador de eventos <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> incrementa la posición de la luz "base", desde la que se determina el estado claro o oscuro de las demás luces y llama al método <xref:System.Windows.Forms.Control.Refresh%2A> para que el control se vuelva a dibujar.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implemente los métodos auxiliares, `IsLit` y `DrawLight`.

    El método `IsLit` determina el color de una luz en una posición determinada. Las luces que están "encendidas" se dibujan en el color dado por la propiedad `LightColor`, y las que son "oscuras" se dibujan en el color que proporciona la propiedad `DarkColor`.

    El método `DrawLight` dibuja una luz con el color, la forma y la posición adecuados.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Invalide los métodos <xref:System.Windows.Forms.Control.OnLayout%2A> y <xref:System.Windows.Forms.Control.OnPaint%2A>.

    El método <xref:System.Windows.Forms.Control.OnPaint%2A> dibuja las luces a lo largo de los bordes del control `MarqueeBorder`.

    Dado que el método <xref:System.Windows.Forms.Control.OnPaint%2A> depende de las dimensiones del control `MarqueeBorder`, debe llamarlo cada vez que cambie el diseño. Para ello, invalide <xref:System.Windows.Forms.Control.OnLayout%2A> y llame a <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Crear un diseñador personalizado para sombrear y filtrar propiedades

La clase `MarqueeControlRootDesigner` proporciona la implementación para el diseñador raíz. Además de este diseñador, que opera en el `MarqueeControl`, necesitará un diseñador personalizado que esté asociado específicamente al control `MarqueeBorder`. Este diseñador proporciona un comportamiento personalizado que es adecuado en el contexto del diseñador raíz personalizado.

En concreto, el `MarqueeBorderDesigner` "prevalece" y filtra ciertas propiedades en el control `MarqueeBorder`, cambiando su interacción con el entorno de diseño.

La interceptación de llamadas al descriptor de acceso de propiedad de un componente se conoce como "sombreado". Permite a un diseñador realizar un seguimiento del valor establecido por el usuario y, opcionalmente, pasar ese valor al componente que se está diseñando.

En este ejemplo, las propiedades <xref:System.Windows.Forms.Control.Visible%2A> y <xref:System.Windows.Forms.Control.Enabled%2A> se separan mediante el `MarqueeBorderDesigner`, lo que evita que el usuario realice el control `MarqueeBorder` invisible o deshabilitado durante el tiempo de diseño.

Los diseñadores también pueden agregar y quitar propiedades. En este ejemplo, la propiedad <xref:System.Windows.Forms.Control.Padding%2A> se quitará en tiempo de diseño, porque el control `MarqueeBorder` establece mediante programación el relleno en función del tamaño de las luces especificadas por la propiedad `LightSize`.

La clase base para `MarqueeBorderDesigner` es <xref:System.ComponentModel.Design.ComponentDesigner>, que tiene métodos que pueden cambiar los atributos, las propiedades y los eventos expuestos por un control en tiempo de diseño:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Al cambiar la interfaz pública de un componente mediante estos métodos, siga estas reglas:

- Agregar o quitar elementos solo en los métodos `PreFilter`

- Modificar elementos existentes solo en los métodos de `PostFilter`

- Llame siempre a la implementación base en primer lugar en los métodos `PreFilter`

- Llame siempre a la implementación base en último lugar en los métodos `PostFilter`

La adhesión a estas reglas garantiza que todos los diseñadores del entorno en tiempo de diseño tienen una vista coherente de todos los componentes que se están diseñando.

La clase <xref:System.ComponentModel.Design.ComponentDesigner> proporciona un diccionario para administrar los valores de las propiedades con sombra, lo que evita la necesidad de crear variables de instancia específicas.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Para crear un diseñador personalizado para sombrear y filtrar propiedades

1. Haga clic con el botón secundario en la carpeta **diseño** y agregue una nueva clase. Asigne al archivo de origen un nombre base de **MarqueeBorderDesigner**.

2. Abra el archivo de origen de MarqueeBorderDesigner en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Cambie la declaración de `MarqueeBorderDesigner` para que hereden de <xref:System.Windows.Forms.Design.ParentControlDesigner>.

    Dado que el control `MarqueeBorder` puede contener controles secundarios, `MarqueeBorderDesigner` hereda de <xref:System.Windows.Forms.Design.ParentControlDesigner>, que controla la interacción de elementos primarios y secundarios.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Invalide la implementación base de <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implemente las propiedades <xref:System.Windows.Forms.Control.Enabled%2A> y <xref:System.Windows.Forms.Control.Visible%2A>. Estas implementaciones prevalecen sobre las propiedades del control.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Controlar cambios de componentes

La clase `MarqueeControlRootDesigner` proporciona la experiencia en tiempo de diseño personalizada para las instancias de `MarqueeControl`. La mayor parte de la funcionalidad en tiempo de diseño se hereda de la clase <xref:System.Windows.Forms.Design.DocumentDesigner>. El código implementará dos personalizaciones específicas: control de los cambios de componente y adición de verbos de diseñador.

A medida que los usuarios diseñan sus instancias de `MarqueeControl`, el diseñador raíz realizará un seguimiento de los cambios en el `MarqueeControl` y sus controles secundarios. El entorno en tiempo de diseño ofrece un servicio cómodo, <xref:System.ComponentModel.Design.IComponentChangeService>, para realizar el seguimiento de los cambios en el estado del componente.

Para adquirir una referencia a este servicio, consulte el entorno con el método <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>. Si la consulta se realiza correctamente, el diseñador puede adjuntar un controlador para el evento de <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> y realizar las tareas necesarias para mantener un estado coherente en tiempo de diseño.

En el caso de la clase `MarqueeControlRootDesigner`, llamará al método <xref:System.Windows.Forms.Control.Refresh%2A> en cada `IMarqueeWidget` objeto incluido en el `MarqueeControl`. Esto hará que el objeto de `IMarqueeWidget` se vuelva a dibujar de manera adecuada cuando se cambien las propiedades como la <xref:System.Windows.Forms.Control.Size%2A> de sus elementos primarios.

### <a name="to-handle-component-changes"></a>Para controlar los cambios de componentes

1. Abra el archivo de origen de `MarqueeControlRootDesigner` en el **Editor de código** e invalide el método <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>. Llame a la implementación base de <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> y consulte la <xref:System.ComponentModel.Design.IComponentChangeService>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implemente el controlador de eventos <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>. Pruebe el tipo del componente de envío y, si es un `IMarqueeWidget`, llame a su método <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Agregar verbos de diseñador al diseñador personalizado

Un verbo de diseñador es un comando de menú vinculado a un controlador de eventos. Los verbos de diseñador se agregan al menú contextual de un componente en tiempo de diseño. Para más información, consulte <xref:System.ComponentModel.Design.DesignerVerb>.

Agregará dos verbos de diseñador a los diseñadores: **Ejecutar prueba** y **detener prueba**. Estos verbos le permitirán ver el comportamiento de tiempo de ejecución del `MarqueeControl` en tiempo de diseño. Estos verbos se agregarán a `MarqueeControlRootDesigner`.

Cuando se invoca la **prueba de ejecución** , el controlador de eventos de verbo llamará al método `StartMarquee` en el `MarqueeControl`. Cuando se invoca la **prueba de detención** , el controlador de eventos de verbo llamará al método `StopMarquee` en el `MarqueeControl`. La implementación de los métodos `StartMarquee` y `StopMarquee` llama a estos métodos en controles contenidos que implementan `IMarqueeWidget`, por lo que todos los controles de `IMarqueeWidget` incluidos también participarán en la prueba.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Para agregar verbos de diseñador a los diseñadores personalizados

1. En la clase `MarqueeControlRootDesigner`, agregue controladores de eventos denominados `OnVerbRunTest` y `OnVerbStopTest`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Conecte estos controladores de eventos a sus verbos de diseñador correspondientes. `MarqueeControlRootDesigner` hereda un <xref:System.ComponentModel.Design.DesignerVerbCollection> de su clase base. Creará dos nuevos objetos de <xref:System.ComponentModel.Design.DesignerVerb> y los agregará a esta colección en el método <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Crear un UITypeEditor personalizado

Cuando se crea una experiencia personalizada en tiempo de diseño para los usuarios, a menudo es conveniente crear una interacción personalizada con el ventana Propiedades. Para ello, cree una <xref:System.Drawing.Design.UITypeEditor>.

El control `MarqueeBorder` expone varias propiedades en el ventana Propiedades. Dos de estas propiedades, `MarqueeSpinDirection` y `MarqueeLightShape` se representan mediante enumeraciones. Para ilustrar el uso de un editor de tipos de interfaz de usuario, la propiedad `MarqueeLightShape` tendrá una clase <xref:System.Drawing.Design.UITypeEditor> asociada.

### <a name="to-create-a-custom-ui-type-editor"></a>Para crear un editor de tipos de interfaz de usuario personalizado

1. Abra el archivo de origen de `MarqueeBorder` en el **Editor de código**.

2. En la definición de la clase `MarqueeBorder`, declare una clase llamada `LightShapeEditor` que derive de <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Declare una variable de instancia de <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> denominada `editorService`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Invalide el método <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Esta implementación devuelve <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, que indica al entorno de diseño cómo mostrar el `LightShapeEditor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Invalide el método <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Esta implementación consulta el entorno de diseño de un objeto <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>. Si se realiza correctamente, crea un `LightShapeSelectionControl`. Se invoca al método <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> para iniciar el `LightShapeEditor`. El valor devuelto de esta Invocación se devuelve al entorno de diseño.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Crear un control de vista para su UITypeEditor personalizado

La propiedad `MarqueeLightShape` admite dos tipos de formas claras: `Square` y `Circle`. Creará un control personalizado que se utiliza únicamente con el fin de mostrar gráficamente estos valores en el ventana Propiedades. El <xref:System.Drawing.Design.UITypeEditor> utilizará este control personalizado para interactuar con el ventana Propiedades.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Para crear un control de vista para el editor de tipos de interfaz de usuario personalizado

1. Agregue un nuevo elemento de <xref:System.Windows.Forms.UserControl> al proyecto de `MarqueeControlLibrary`. Asigne al nuevo archivo de código fuente el nombre base de **LightShapeSelectionControl**.

2. Arrastre dos controles <xref:System.Windows.Forms.Panel> desde el **cuadro de herramientas** hasta el `LightShapeSelectionControl`. Asígneles el nombre `squarePanel` y `circlePanel`. Organícelos en paralelo. Establezca la propiedad <xref:System.Windows.Forms.Control.Size%2A> de ambos controles <xref:System.Windows.Forms.Panel> en **(60, 60)** . Establezca la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control `squarePanel` en **(8, 10)** . Establezca la propiedad <xref:System.Windows.Forms.Control.Location%2A> del control `circlePanel` en **(80, 10)** . Por último, establezca la propiedad <xref:System.Windows.Forms.Control.Size%2A> del `LightShapeSelectionControl` en **(150, 80)** .

3. Abra el archivo de origen de `LightShapeSelectionControl` en el **Editor de código**. En la parte superior del archivo, importe el espacio de nombres <xref:System.Windows.Forms.Design?displayProperty=nameWithType>:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Implemente <xref:System.Windows.Forms.Control.Click> controladores de eventos para los controles `squarePanel` y `circlePanel`. Estos métodos invocan <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> para finalizar la sesión de edición de <xref:System.Drawing.Design.UITypeEditor> personalizada.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Declare una variable de instancia de <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> denominada `editorService`.

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Declare una variable de instancia de `MarqueeLightShape` denominada `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. En el constructor `LightShapeSelectionControl`, adjunte los controladores de eventos de <xref:System.Windows.Forms.Control.Click> a los eventos de <xref:System.Windows.Forms.Control.Click> de los controles `squarePanel` y `circlePanel`. Además, defina una sobrecarga de constructor que asigne el valor `MarqueeLightShape` del entorno de diseño al campo `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. En el método <xref:System.ComponentModel.Component.Dispose%2A>, desasocie los controladores de eventos <xref:System.Windows.Forms.Control.Click>.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**. Abra el archivo LightShapeSelectionControl.Designer.cs o LightShapeSelectionControl. Designer. VB y quite la definición predeterminada del método <xref:System.ComponentModel.Component.Dispose%2A>.

10. Implemente la propiedad `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A> . Esta implementación dibujará un cuadrado y un círculo rellenos. También resaltará el valor seleccionado dibujando un borde alrededor de una forma u otra.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Probar el control personalizado en el diseñador

En este momento, puede compilar el proyecto `MarqueeControlLibrary`. Pruebe la implementación creando un control que herede de la clase `MarqueeControl` y usando en un formulario.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Para crear una implementación personalizada de MarqueeControl

1. Abra `DemoMarqueeControl` en el Diseñador de Windows Forms. Esto crea una instancia del tipo de `DemoMarqueeControl` y la muestra en una instancia del tipo de `MarqueeControlRootDesigner`.

2. En el **cuadro de herramientas**, abra la pestaña **componentes de MarqueeControlLibrary** . Verá los controles `MarqueeBorder` y `MarqueeText` disponibles para la selección.

3. Arrastre una instancia del control `MarqueeBorder` a la superficie de diseño `DemoMarqueeControl`. Acople este control de `MarqueeBorder` al control principal.

4. Arrastre una instancia del control `MarqueeText` a la superficie de diseño `DemoMarqueeControl`.

5. Compile la solución.

6. Haga clic con el botón secundario en el `DemoMarqueeControl` y, en el menú contextual, seleccione la opción **Ejecutar prueba** para iniciar la animación. Haga clic en **detener prueba** para detener la animación.

7. Abra **Form1** en la vista Diseño.

8. Coloque dos <xref:System.Windows.Forms.Button> controles en el formulario. Asígneles el nombre `startButton` y `stopButton`, y cambie los valores de la propiedad <xref:System.Windows.Forms.Control.Text%2A> a **iniciar** y **detener**, respectivamente.

9. Implemente <xref:System.Windows.Forms.Control.Click> controladores de eventos para ambos controles de <xref:System.Windows.Forms.Button>.

10. En el **cuadro de herramientas**, abra la pestaña **componentes de MarqueeControlTest** . Verá el `DemoMarqueeControl` disponible para la selección.

11. Arrastre una instancia de `DemoMarqueeControl` a la superficie de diseño de **Form1** .

12. En los controladores de eventos <xref:System.Windows.Forms.Control.Click>, invoque los métodos `Start` y `Stop` en el `DemoMarqueeControl`.

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

13. Establezca el proyecto de `MarqueeControlTest` como el proyecto de inicio y ejecútelo. Verá el formulario en el que se muestra el `DemoMarqueeControl`. Seleccione el botón **iniciar** para iniciar la animación. Debería ver el parpadeo del texto y las luces desplazadas alrededor del borde.

## <a name="next-steps"></a>Pasos siguientes

En el `MarqueeControlLibrary` se muestra una implementación simple de controles personalizados y diseñadores asociados. Puede hacer que este ejemplo sea más sofisticado de varias maneras:

- Cambie los valores de propiedad para el `DemoMarqueeControl` en el diseñador. Agregue más `MarqueBorder` controles y acoplelos dentro de sus instancias primarias para crear un efecto anidado. Experimente con diferentes configuraciones para los `UpdatePeriod` y las propiedades relacionadas con la luz.

- Cree sus propias implementaciones de `IMarqueeWidget`. Por ejemplo, podría crear un "signo de neón" intermitente o un signo animado con varias imágenes.

- Personalizar aún más la experiencia en tiempo de diseño. Podría intentar sombrear más propiedades que <xref:System.Windows.Forms.Control.Enabled%2A> y <xref:System.Windows.Forms.Control.Visible%2A>y agregar nuevas propiedades. Agregue nuevos verbos de diseñador para simplificar las tareas comunes, como acoplar los controles secundarios.

- Licencia del `MarqueeControl`.

- Controlar cómo se serializan los controles y cómo se genera el código para ellos. Para obtener más información, vea [generación y compilación de código fuente dinámico](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
