---
title: Crear un control que aproveche las características en tiempo de diseño de Visual Studio
description: Aprenda a crear un diseñador personalizado para un control personalizado en Windows Forms que aprovecha las características de tiempo de diseño.
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
ms.openlocfilehash: 03c04578ecb01b689f58d41a46eef5793fb1182c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613915"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Tutorial: crear un control que aproveche las características de tiempo de diseño

La experiencia en tiempo de diseño de un control personalizado se puede mejorar mediante la creación de un diseñador personalizado asociado.

En este artículo se muestra cómo crear un diseñador personalizado para un control personalizado. Implementará un `MarqueeControl` tipo y una clase de diseñador asociada denominada `MarqueeControlRootDesigner` .

El `MarqueeControl` tipo implementa una pantalla similar a una marquesina de teatro con luces animadas y texto parpadeante.

El diseñador de este control interactúa con el entorno de diseño para proporcionar una experiencia personalizada en tiempo de diseño. Con el diseñador personalizado, puede ensamblar una `MarqueeControl` implementación personalizada con luces animadas y texto intermitente en muchas combinaciones. Puede usar el control ensamblado en un formulario como cualquier otro control de Windows Forms.

Cuando haya terminado con este tutorial, el control personalizado tendrá un aspecto similar al siguiente:

![Aplicación que muestra una marquesina que indica el texto y los botones de inicio y detención.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Para obtener la lista de código completa, vea [Cómo: crear un control de Windows Forms que aprovecha las características en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).

## <a name="prerequisites"></a>Requisitos previos

Para completar este tutorial, necesitará Visual Studio.

## <a name="create-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto de la aplicación. Usará este proyecto para compilar la aplicación que hospeda el control personalizado.

En Visual Studio, cree un nuevo proyecto de aplicación de Windows Forms y asígnele el nombre **MarqueeControlTest**.

## <a name="create-the-control-library-project"></a>Crear el proyecto de biblioteca de controles

1. Agregue un proyecto de biblioteca de controles Windows Forms a la solución. Asigne al proyecto el nombre **MarqueeControlLibrary**.

2. Use **Explorador de soluciones**para eliminar el control predeterminado del proyecto eliminando el archivo de código fuente denominado "UserControl1.cs" o "UserControl1. VB", según el lenguaje que elija.

3. Agregue un nuevo <xref:System.Windows.Forms.UserControl> elemento al `MarqueeControlLibrary` proyecto. Asigne al nuevo archivo de código fuente un nombre base de **MarqueeControl**.

4. Con **Explorador de soluciones**, cree una nueva carpeta en el `MarqueeControlLibrary` proyecto.

5. Haga clic con el botón secundario en la carpeta **diseño** y agregue una nueva clase. Asígnele el nombre **MarqueeControlRootDesigner**.

6. Tendrá que usar tipos del ensamblado System. Design, por lo que debe agregar esta referencia al `MarqueeControlLibrary` proyecto.

## <a name="reference-the-custom-control-project"></a>Referencia al proyecto de control personalizado

Usará el `MarqueeControlTest` proyecto para probar el control personalizado. El proyecto de prueba conocerá el control personalizado al agregar una referencia de proyecto al `MarqueeControlLibrary` ensamblado.

En el `MarqueeControlTest` proyecto, agregue una referencia de proyecto al `MarqueeControlLibrary` ensamblado. Asegúrese de usar la pestaña **proyectos** del cuadro de diálogo **Agregar referencia** en lugar de hacer referencia al `MarqueeControlLibrary` ensamblado directamente.

## <a name="define-a-custom-control-and-its-custom-designer"></a>Definir un control personalizado y su diseñador personalizado

El control personalizado se deriva de la <xref:System.Windows.Forms.UserControl> clase. Esto permite que el control contenga otros controles y proporciona a su control una gran cantidad de funcionalidad predeterminada.

El control personalizado tendrá un diseñador personalizado asociado. Esto le permite crear una experiencia de diseño única adaptada específicamente para su control personalizado.

Asocie el control a su diseñador mediante la <xref:System.ComponentModel.DesignerAttribute> clase. Dado que está desarrollando todo el comportamiento en tiempo de diseño del control personalizado, el diseñador personalizado implementará la <xref:System.ComponentModel.Design.IRootDesigner> interfaz.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Para definir un control personalizado y su diseñador personalizado

1. Abra el `MarqueeControl` archivo de código fuente en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Agregue <xref:System.ComponentModel.DesignerAttribute> a la `MarqueeControl` declaración de clase. Esto asocia el control personalizado a su diseñador.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Abra el `MarqueeControlRootDesigner` archivo de código fuente en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Cambie la declaración de `MarqueeControlRootDesigner` para que herede de la <xref:System.Windows.Forms.Design.DocumentDesigner> clase. Aplique <xref:System.ComponentModel.ToolboxItemFilterAttribute> para especificar la interacción del diseñador con el **cuadro de herramientas**.

   > [!NOTE]
   > La definición de la `MarqueeControlRootDesigner` clase se ha incluido en un espacio de nombres denominado MarqueeControlLibrary. Design. Esta declaración coloca el diseñador en un espacio de nombres especial reservado para los tipos relacionados con el diseño.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Defina el constructor para la `MarqueeControlRootDesigner` clase. Inserte una <xref:System.Diagnostics.Trace.WriteLine%2A> instrucción en el cuerpo del constructor. Esto será útil para la depuración.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Crear una instancia de un control personalizado

1. Agregue un nuevo <xref:System.Windows.Forms.UserControl> elemento al `MarqueeControlTest` proyecto. Asigne al nuevo archivo de código fuente el nombre base de **DemoMarqueeControl**.

2. Abra el `DemoMarqueeControl` archivo en el **Editor de código**. En la parte superior del archivo, importe el `MarqueeControlLibrary` espacio de nombres:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Cambie la declaración de `DemoMarqueeControl` para que herede de la `MarqueeControl` clase.

4. Compile el proyecto.

5. Abra Form1 en el Diseñador de Windows Forms.

6. Busque la pestaña **componentes de MarqueeControlTest** en el cuadro de **herramientas** y ábrala. Arrastre un `DemoMarqueeControl` desde el **cuadro de herramientas** hasta el formulario.

7. Compile el proyecto.

## <a name="set-up-the-project-for-design-time-debugging"></a>Configurar el proyecto para la depuración en tiempo de diseño

Al desarrollar una experiencia personalizada en tiempo de diseño, será necesario depurar los controles y componentes. Hay una manera sencilla de configurar el proyecto para permitir la depuración en tiempo de diseño. Para obtener más información, vea [Tutorial: depurar controles de Windows Forms personalizados en tiempo de diseño](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

1. Haga clic con el botón derecho en el `MarqueeControlLibrary` proyecto y seleccione **propiedades**.

2. En el cuadro de diálogo **páginas de propiedades de MarqueeControlLibrary** , seleccione la página **depurar** .

3. En la sección **acción de inicio** , seleccione **programa externo de inicio**. Va a depurar una instancia independiente de Visual Studio, por lo que debe hacer clic en los puntos suspensivos ( ![ el botón de puntos suspensivos (...) del botón ventana Propiedades de Visual Studio ](./media/visual-studio-ellipsis-button.png) ) para buscar el IDE de Visual Studio. El nombre del archivo ejecutable es devenv.exe y, si lo instaló en la ubicación predeterminada, su ruta de acceso es *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019 \\ \<edition>\Common7\IDE\devenv.exe*.

4. Seleccione **Aceptar** para cerrar el cuadro de diálogo.

5. Haga clic con el botón derecho en el proyecto MarqueeControlLibrary y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.

## <a name="checkpoint"></a>Punto de control

Ahora está listo para depurar el comportamiento en tiempo de diseño del control personalizado. Una vez que haya determinado que el entorno de depuración está configurado correctamente, probará la asociación entre el control personalizado y el diseñador personalizado.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Para probar el entorno de depuración y la Asociación del diseñador

1. Abra el archivo de origen MarqueeControlRootDesigner en el **Editor de código** y coloque un punto de interrupción en la <xref:System.Diagnostics.Trace.WriteLine%2A> instrucción.

2. Presione **F5** para iniciar la sesión de depuración.

   Se crea una nueva instancia de Visual Studio.

3. En la nueva instancia de Visual Studio, abra la solución MarqueeControlTest. Puede encontrar fácilmente la solución seleccionando **proyectos recientes** en el menú **archivo** . El archivo de solución de MarqueeControlTest. sln se mostrará como el archivo usado más recientemente.

4. Abra `DemoMarqueeControl` en el diseñador.

   La instancia de depuración de Visual Studio obtiene el foco y la ejecución se detiene en el punto de interrupción. Presione **F5** para continuar con la sesión de depuración.

En este punto, todo está en su lugar para desarrollar y depurar el control personalizado y su diseñador personalizado asociado. El resto de este artículo se centra en los detalles de la implementación de características del control y el diseñador.

## <a name="implement-the-custom-control"></a>Implementar el control personalizado

`MarqueeControl`Es un <xref:System.Windows.Forms.UserControl> con un poco de personalización. Expone dos métodos: `Start` , que inicia la animación de marquesina y `Stop` , que detiene la animación. Dado `MarqueeControl` que contiene controles secundarios que implementan la `IMarqueeWidget` interfaz `Start` , `Stop` enumera cada control secundario y llama a los `StartMarquee` `StopMarquee` métodos y, respectivamente, en cada control secundario que implementa `IMarqueeWidget` .

La apariencia de los `MarqueeBorder` `MarqueeText` controles y depende del diseño, por lo que `MarqueeControl` reemplaza el <xref:System.Windows.Forms.Control.OnLayout%2A> método y llama a los <xref:System.Windows.Forms.Control.PerformLayout%2A> controles secundarios de este tipo.

Esta es la extensión de las `MarqueeControl` personalizaciones. Los controles y implementan las características en tiempo de ejecución `MarqueeBorder` `MarqueeText` , y las características en tiempo de diseño las implementan `MarqueeBorderDesigner` las `MarqueeControlRootDesigner` clases y.

### <a name="to-implement-your-custom-control"></a>Para implementar el control personalizado

1. Abra el `MarqueeControl` archivo de código fuente en el **Editor de código**. Implemente `Start` los `Stop` métodos y.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Invalide el método <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Crear un control secundario para el control personalizado

`MarqueeControl`Hospedará dos tipos de controles secundarios: el `MarqueeBorder` control y el `MarqueeText` control.

- `MarqueeBorder`: Este control pinta un borde de "Lights" alrededor de los bordes. Las luces parpadean en secuencia, por lo que parecen moverse alrededor del borde. La velocidad a la que se controla el parpadeo de las luces mediante una propiedad denominada `UpdatePeriod` . Otras propiedades personalizadas determinan otros aspectos de la apariencia del control. Dos métodos, denominados `StartMarquee` y `StopMarquee` , controlan Cuándo se inicia y se detiene la animación.

- `MarqueeText`: Este control pinta una cadena parpadeante. Al igual `MarqueeBorder` que el control, la velocidad a la que el texto parpadea se controla mediante la `UpdatePeriod` propiedad. El `MarqueeText` control también tiene los `StartMarquee` `StopMarquee` métodos y en común con el `MarqueeBorder` control.

En tiempo de diseño, `MarqueeControlRootDesigner` permite agregar estos dos tipos de controles a un `MarqueeControl` en cualquier combinación.

Las características comunes de los dos controles se factorizan en una interfaz denominada `IMarqueeWidget` . Esto permite `MarqueeControl` que detecte los controles secundarios relacionados con la marquesina y les dé un tratamiento especial.

Para implementar la característica de animación periódica, usará <xref:System.ComponentModel.BackgroundWorker> objetos del espacio de <xref:System.ComponentModel?displayProperty=nameWithType> nombres. Puede usar <xref:System.Windows.Forms.Timer> objetos, pero cuando hay muchos `IMarqueeWidget` objetos, es posible que el subproceso de la interfaz de usuario no pueda mantener el ritmo de la animación.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Para crear un control secundario para el control personalizado

1. Agregue un nuevo elemento de clase al `MarqueeControlLibrary` proyecto. Asigne al nuevo archivo de código fuente el nombre base "IMarqueeWidget".

2. Abra el `IMarqueeWidget` archivo de código fuente en el **Editor de código** y cambie la declaración de `class` a `interface` :

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Agregue el código siguiente a la `IMarqueeWidget` interfaz para exponer dos métodos y una propiedad que manipula la animación de marquesina:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Agregue un nuevo elemento de **control personalizado** al `MarqueeControlLibrary` proyecto. Asigne el nombre base "MarqueeText" al nuevo archivo de código fuente.

5. Arrastre un <xref:System.ComponentModel.BackgroundWorker> componente desde el **cuadro de herramientas** hasta el `MarqueeText` control. Este componente permitirá que el `MarqueeText` control se actualice a sí mismo de forma asincrónica.

6. En la ventana **propiedades** , establezca las <xref:System.ComponentModel.BackgroundWorker> `WorkerReportsProgress` propiedades y del componente <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> en **true**. Esta configuración permite que el <xref:System.ComponentModel.BackgroundWorker> componente genere periódicamente el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento y cancele las actualizaciones asincrónicas.

   Para obtener más información, vea [BackgroundWorker (componente](backgroundworker-component.md)).

7. Abra el `MarqueeText` archivo de código fuente en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Cambie la declaración de `MarqueeText` para que herede de <xref:System.Windows.Forms.Label> e implemente la `IMarqueeWidget` interfaz:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Declare las variables de instancia que corresponden a las propiedades expuestas e inicialícela en el constructor. El `isLit` campo determina si el texto se va a pintar en el color dado por la `LightColor` propiedad.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementar la interfaz `IMarqueeWidget`.

    Los `StartMarquee` `StopMarquee` métodos y invocan los <xref:System.ComponentModel.BackgroundWorker> métodos y del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> para iniciar y detener la animación.

    Los <xref:System.ComponentModel.CategoryAttribute.Category%2A> <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> atributos y se aplican a la `UpdatePeriod` propiedad, por lo que aparece en una sección personalizada del ventana Propiedades denominada "Marquesina".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementar los descriptores de acceso de propiedad. Expondrá dos propiedades a los clientes: `LightColor` y `DarkColor` . Los <xref:System.ComponentModel.CategoryAttribute.Category%2A> <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> atributos y se aplican a estas propiedades, por lo que las propiedades aparecen en una sección personalizada del ventana Propiedades denominada "Marquesina".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implemente los controladores para los <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> eventos y del componente <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    El <xref:System.ComponentModel.BackgroundWorker.DoWork> controlador de eventos se suspende durante el número de milisegundos especificado por `UpdatePeriod` y, a continuación, genera el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, hasta que el código detiene la animación mediante una llamada a <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    El <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> controlador de eventos alterna el texto entre su estado claro y oscuro para dar la apariencia de parpadeo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Invalide el <xref:System.Windows.Forms.Control.OnPaint%2A> método para habilitar la animación.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Presione **F6** para compilar la solución.

## <a name="create-the-marqueeborder-child-control"></a>Crear el control secundario de MarqueeBorder

El `MarqueeBorder` control es ligeramente más sofisticado que el `MarqueeText` control. Tiene más propiedades y la animación en el <xref:System.Windows.Forms.Control.OnPaint%2A> método es más complicada. En principio, es bastante similar al `MarqueeText` control.

Dado que el `MarqueeBorder` control puede tener controles secundarios, debe ser consciente de <xref:System.Windows.Forms.Control.Layout> los eventos.

### <a name="to-create-the-marqueeborder-control"></a>Para crear el control MarqueeBorder

1. Agregue un nuevo elemento de **control personalizado** al `MarqueeControlLibrary` proyecto. Asigne al nuevo archivo de código fuente el nombre base "MarqueeBorder".

2. Arrastre un <xref:System.ComponentModel.BackgroundWorker> componente desde el **cuadro de herramientas** hasta el `MarqueeBorder` control. Este componente permitirá que el `MarqueeBorder` control se actualice a sí mismo de forma asincrónica.

3. En la ventana **propiedades** , establezca las <xref:System.ComponentModel.BackgroundWorker> `WorkerReportsProgress` propiedades y del componente <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> en **true**. Esta configuración permite que el <xref:System.ComponentModel.BackgroundWorker> componente genere periódicamente el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento y cancele las actualizaciones asincrónicas. Para obtener más información, vea [BackgroundWorker (componente](backgroundworker-component.md)).

4. En la ventana **propiedades** , seleccione el botón **eventos** . Adjunte Controladores para los <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventos y.

5. Abra el `MarqueeBorder` archivo de código fuente en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Cambie la declaración de `MarqueeBorder` para que herede de <xref:System.Windows.Forms.Panel> e implemente la `IMarqueeWidget` interfaz.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Declare dos enumeraciones para administrar el `MarqueeBorder` Estado del control: `MarqueeSpinDirection` , que determina la dirección en la que las luces "giran" alrededor del borde y `MarqueeLightShape` , que determina la forma de las luces (cuadradas o circulares). Coloque estas declaraciones antes de la `MarqueeBorder` declaración de clase.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Declare las variables de instancia que corresponden a las propiedades expuestas e inicialícela en el constructor.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementar la interfaz `IMarqueeWidget`.

    Los `StartMarquee` `StopMarquee` métodos y invocan los <xref:System.ComponentModel.BackgroundWorker> métodos y del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> para iniciar y detener la animación.

    Dado que el `MarqueeBorder` control puede contener controles secundarios, el `StartMarquee` método enumera todos los controles secundarios y llama a los `StartMarquee` que implementan `IMarqueeWidget` . El `StopMarquee` método tiene una implementación similar.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementar los descriptores de acceso de propiedad. El `MarqueeBorder` control tiene varias propiedades para controlar su apariencia.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implemente los controladores para los <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> eventos y del componente <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    El <xref:System.ComponentModel.BackgroundWorker.DoWork> controlador de eventos se suspende durante el número de milisegundos especificado por `UpdatePeriod` y, a continuación, genera el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, hasta que el código detiene la animación mediante una llamada a <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    El <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> controlador de eventos incrementa la posición de la luz "base", desde la que se determina el estado claro/oscuro de las demás luces y llama al <xref:System.Windows.Forms.Control.Refresh%2A> método para que el control se vuelva a dibujar.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implemente los métodos auxiliares, `IsLit` y `DrawLight` .

    El `IsLit` método determina el color de una luz en una posición determinada. Las luces que están "encendidas" se dibujan en el color dado por la `LightColor` propiedad, y las que se "oscuras" se dibujan en el color dado por la `DarkColor` propiedad.

    El `DrawLight` método dibuja una luz con el color, la forma y la posición adecuados.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Invalide los métodos <xref:System.Windows.Forms.Control.OnLayout%2A> y <xref:System.Windows.Forms.Control.OnPaint%2A>.

    El <xref:System.Windows.Forms.Control.OnPaint%2A> método dibuja las luces a lo largo de los bordes del `MarqueeBorder` control.

    Dado que el <xref:System.Windows.Forms.Control.OnPaint%2A> método depende de las dimensiones del `MarqueeBorder` control, debe llamarlo cada vez que cambie el diseño. Para ello, invalide <xref:System.Windows.Forms.Control.OnLayout%2A> y llame a <xref:System.Windows.Forms.Control.Refresh%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Crear un diseñador personalizado para sombrear y filtrar propiedades

La `MarqueeControlRootDesigner` clase proporciona la implementación para el diseñador raíz. Además de este diseñador, que opera en `MarqueeControl` , necesitará un diseñador personalizado que esté asociado específicamente al `MarqueeBorder` control. Este diseñador proporciona un comportamiento personalizado que es adecuado en el contexto del diseñador raíz personalizado.

En concreto, el `MarqueeBorderDesigner` sombreará y filtrará determinadas propiedades del `MarqueeBorder` control, lo que cambiará su interacción con el entorno de diseño.

La interceptación de llamadas al descriptor de acceso de propiedad de un componente se conoce como "sombreado". Permite a un diseñador realizar un seguimiento del valor establecido por el usuario y, opcionalmente, pasar ese valor al componente que se está diseñando.

En este ejemplo, las <xref:System.Windows.Forms.Control.Visible%2A> propiedades y se separan <xref:System.Windows.Forms.Control.Enabled%2A> mediante `MarqueeBorderDesigner` , lo que evita que el usuario pueda hacer que el `MarqueeBorder` control sea invisible o deshabilitado durante el tiempo de diseño.

Los diseñadores también pueden agregar y quitar propiedades. En este ejemplo, la <xref:System.Windows.Forms.Control.Padding%2A> propiedad se quitará en tiempo de diseño, porque el `MarqueeBorder` control establece mediante programación el relleno en función del tamaño de las luces especificadas por la `LightSize` propiedad.

La clase base de `MarqueeBorderDesigner` es <xref:System.ComponentModel.Design.ComponentDesigner> , que tiene métodos que pueden cambiar los atributos, las propiedades y los eventos expuestos por un control en tiempo de diseño:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Al cambiar la interfaz pública de un componente mediante estos métodos, siga estas reglas:

- Agregar o quitar elementos solo en los `PreFilter` métodos

- Modificar elementos existentes solo en los `PostFilter` métodos

- Llame siempre a la implementación base en primer lugar en los `PreFilter` métodos.

- Llame siempre a la implementación base en último lugar en los `PostFilter` métodos.

La adhesión a estas reglas garantiza que todos los diseñadores del entorno en tiempo de diseño tienen una vista coherente de todos los componentes que se están diseñando.

La <xref:System.ComponentModel.Design.ComponentDesigner> clase proporciona un diccionario para administrar los valores de las propiedades sombreadas, lo que evita la necesidad de crear variables de instancia específicas.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Para crear un diseñador personalizado para sombrear y filtrar propiedades

1. Haga clic con el botón secundario en la carpeta **diseño** y agregue una nueva clase. Asigne al archivo de origen un nombre base de **MarqueeBorderDesigner**.

2. Abra el archivo de origen de MarqueeBorderDesigner en el **Editor de código**. En la parte superior del archivo, importe los siguientes espacios de nombres:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Cambie la declaración de `MarqueeBorderDesigner` para que herede de <xref:System.Windows.Forms.Design.ParentControlDesigner> .

    Dado `MarqueeBorder` que el control puede contener controles secundarios, `MarqueeBorderDesigner` hereda de <xref:System.Windows.Forms.Design.ParentControlDesigner> , que controla la interacción de elementos primarios y secundarios.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Invalide la implementación base de <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implemente las propiedades <xref:System.Windows.Forms.Control.Enabled%2A> y <xref:System.Windows.Forms.Control.Visible%2A>. Estas implementaciones prevalecen sobre las propiedades del control.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Controlar cambios de componentes

La `MarqueeControlRootDesigner` clase proporciona la experiencia en tiempo de diseño personalizada para las `MarqueeControl` instancias de. La mayor parte de la funcionalidad en tiempo de diseño se hereda de la <xref:System.Windows.Forms.Design.DocumentDesigner> clase. El código implementará dos personalizaciones específicas: control de los cambios de componente y adición de verbos de diseñador.

A medida que los usuarios diseñan sus `MarqueeControl` instancias, el diseñador raíz realizará un seguimiento de los cambios en `MarqueeControl` y en sus controles secundarios. El entorno en tiempo de diseño ofrece un servicio cómodo, <xref:System.ComponentModel.Design.IComponentChangeService> , para realizar un seguimiento de los cambios en el estado del componente.

Para adquirir una referencia a este servicio, consulte el entorno con el <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> método. Si la consulta se realiza correctamente, el diseñador puede adjuntar un controlador para el <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> evento y realizar las tareas necesarias para mantener un estado coherente en tiempo de diseño.

En el caso de la `MarqueeControlRootDesigner` clase, llamará al <xref:System.Windows.Forms.Control.Refresh%2A> método en cada `IMarqueeWidget` objeto incluido en `MarqueeControl` . Esto hará que el `IMarqueeWidget` objeto se vuelva a dibujar de manera adecuada cuando se cambien las propiedades como sus elementos primarios <xref:System.Windows.Forms.Control.Size%2A> .

### <a name="to-handle-component-changes"></a>Para controlar los cambios de componentes

1. Abra el `MarqueeControlRootDesigner` archivo de código fuente en el **Editor de código** e invalide el <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> método. Llame a la implementación base de <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> y consulte para <xref:System.ComponentModel.Design.IComponentChangeService> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implemente el <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> controlador de eventos. Pruebe el tipo del componente de envío y, si es `IMarqueeWidget` , llame a su <xref:System.Windows.Forms.Control.Refresh%2A> método.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Agregar verbos de diseñador al diseñador personalizado

Un verbo de diseñador es un comando de menú vinculado a un controlador de eventos. Los verbos de diseñador se agregan al menú contextual de un componente en tiempo de diseño. Para obtener más información, vea <xref:System.ComponentModel.Design.DesignerVerb>.

Agregará dos verbos de diseñador a los diseñadores: **Ejecutar prueba** y **detener prueba**. Estos verbos le permitirán ver el comportamiento de tiempo de ejecución de `MarqueeControl` en tiempo de diseño. Estos verbos se agregarán a `MarqueeControlRootDesigner` .

Cuando se invoca la **prueba de ejecución** , el controlador de eventos de verbo llamará al `StartMarquee` método en `MarqueeControl` . Cuando se invoca la **prueba de detención** , el controlador de eventos de verbo llamará al `StopMarquee` método en `MarqueeControl` . La implementación de los `StartMarquee` `StopMarquee` métodos y llama a estos métodos en controles contenidos que implementan `IMarqueeWidget` , por lo que los `IMarqueeWidget` controles contenidos también participarán en la prueba.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Para agregar verbos de diseñador a los diseñadores personalizados

1. En la `MarqueeControlRootDesigner` clase, agregue controladores de eventos denominados `OnVerbRunTest` y `OnVerbStopTest` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Conecte estos controladores de eventos a sus verbos de diseñador correspondientes. `MarqueeControlRootDesigner`hereda un <xref:System.ComponentModel.Design.DesignerVerbCollection> de su clase base. Creará dos nuevos <xref:System.ComponentModel.Design.DesignerVerb> objetos y los agregará a esta colección en el <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> método.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Crear un UITypeEditor personalizado

Cuando se crea una experiencia personalizada en tiempo de diseño para los usuarios, a menudo es conveniente crear una interacción personalizada con el ventana Propiedades. Para ello, puede crear un <xref:System.Drawing.Design.UITypeEditor> .

El `MarqueeBorder` control expone varias propiedades en el ventana Propiedades. Dos de estas propiedades, `MarqueeSpinDirection` y `MarqueeLightShape` se representan mediante enumeraciones. Para ilustrar el uso de un editor de tipos de interfaz de usuario, la `MarqueeLightShape` propiedad tendrá una <xref:System.Drawing.Design.UITypeEditor> clase asociada.

### <a name="to-create-a-custom-ui-type-editor"></a>Para crear un editor de tipos de interfaz de usuario personalizado

1. Abra el `MarqueeBorder` archivo de código fuente en el **Editor de código**.

2. En la definición de la `MarqueeBorder` clase, declare una clase denominada `LightShapeEditor` que se derive de <xref:System.Drawing.Design.UITypeEditor> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Declare una <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variable de instancia denominada `editorService` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Invalide el método <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Esta implementación devuelve <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown> , que indica al entorno de diseño cómo mostrar el `LightShapeEditor` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Invalide el método <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Esta implementación consulta el entorno de diseño de un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> objeto. Si se realiza correctamente, crea un `LightShapeSelectionControl` . <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>Se invoca el método para iniciar el `LightShapeEditor` . El valor devuelto de esta Invocación se devuelve al entorno de diseño.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Crear un control de vista para su UITypeEditor personalizado

La `MarqueeLightShape` propiedad admite dos tipos de formas claras: `Square` y `Circle` . Creará un control personalizado que se utiliza únicamente con el fin de mostrar gráficamente estos valores en el ventana Propiedades. Usará este control personalizado <xref:System.Drawing.Design.UITypeEditor> para interactuar con el ventana Propiedades.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Para crear un control de vista para el editor de tipos de interfaz de usuario personalizado

1. Agregue un nuevo <xref:System.Windows.Forms.UserControl> elemento al `MarqueeControlLibrary` proyecto. Asigne al nuevo archivo de código fuente el nombre base de **LightShapeSelectionControl**.

2. Arrastre dos <xref:System.Windows.Forms.Panel> controles desde el **cuadro de herramientas** hasta el `LightShapeSelectionControl` . Asígneles nombres `squarePanel` y `circlePanel` . Organícelos en paralelo. Establezca la <xref:System.Windows.Forms.Control.Size%2A> propiedad de ambos <xref:System.Windows.Forms.Panel> controles en **(60, 60)**. Establezca la <xref:System.Windows.Forms.Control.Location%2A> propiedad del `squarePanel` control en **(8, 10)**. Establezca la <xref:System.Windows.Forms.Control.Location%2A> propiedad del `circlePanel` control en **(80, 10)**. Por último, establezca la <xref:System.Windows.Forms.Control.Size%2A> propiedad de `LightShapeSelectionControl` en **(150, 80)**.

3. Abra el `LightShapeSelectionControl` archivo de código fuente en el **Editor de código**. En la parte superior del archivo, importe el <xref:System.Windows.Forms.Design?displayProperty=nameWithType> espacio de nombres:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Implemente <xref:System.Windows.Forms.Control.Click> controladores de eventos para `squarePanel` los `circlePanel` controles y. Estos métodos invocan <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> para finalizar la <xref:System.Drawing.Design.UITypeEditor> sesión de edición personalizada.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Declare una <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variable de instancia denominada `editorService` .

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Declare una `MarqueeLightShape` variable de instancia denominada `lightShapeValue` .

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. En el `LightShapeSelectionControl` constructor, asocie los <xref:System.Windows.Forms.Control.Click> controladores de eventos a los `squarePanel` eventos de los `circlePanel` controles y <xref:System.Windows.Forms.Control.Click> . Además, defina una sobrecarga de constructor que asigne el `MarqueeLightShape` valor del entorno de diseño al `lightShapeValue` campo.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. En el <xref:System.ComponentModel.Component.Dispose%2A> método, desasocie los <xref:System.Windows.Forms.Control.Click> controladores de eventos.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**. Abra el archivo LightShapeSelectionControl.Designer.cs o LightShapeSelectionControl. Designer. VB y quite la definición predeterminada del <xref:System.ComponentModel.Component.Dispose%2A> método.

10. Implemente la propiedad `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A> . Esta implementación dibujará un cuadrado y un círculo rellenos. También resaltará el valor seleccionado dibujando un borde alrededor de una forma u otra.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Probar el control personalizado en el diseñador

En este momento, puede compilar el `MarqueeControlLibrary` proyecto. Pruebe la implementación creando un control que herede de la `MarqueeControl` clase y usando en un formulario.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Para crear una implementación personalizada de MarqueeControl

1. Abra `DemoMarqueeControl` en el Diseñador de Windows Forms. Esto crea una instancia del `DemoMarqueeControl` tipo y la muestra en una instancia del `MarqueeControlRootDesigner` tipo.

2. En el **cuadro de herramientas**, abra la pestaña **componentes de MarqueeControlLibrary** . Verá los `MarqueeBorder` `MarqueeText` controles y disponibles para la selección.

3. Arrastre una instancia del `MarqueeBorder` control a la `DemoMarqueeControl` superficie de diseño. Acople este `MarqueeBorder` control al control principal.

4. Arrastre una instancia del `MarqueeText` control a la `DemoMarqueeControl` superficie de diseño.

5. Compile la solución.

6. Haga clic con el botón secundario en y, en `DemoMarqueeControl` el menú contextual, seleccione la opción **Ejecutar prueba** para iniciar la animación. Haga clic en **detener prueba** para detener la animación.

7. Abra **Form1** en vista de diseño.

8. Coloque dos <xref:System.Windows.Forms.Button> controles en el formulario. Asígnele `startButton` un nombre y `stopButton` , y cambie los <xref:System.Windows.Forms.Control.Text%2A> valores de propiedad a **iniciar** y **detener**, respectivamente.

9. Implemente <xref:System.Windows.Forms.Control.Click> controladores de eventos para ambos <xref:System.Windows.Forms.Button> controles.

10. En el **cuadro de herramientas**, abra la pestaña **componentes de MarqueeControlTest** . Verá que `DemoMarqueeControl` está disponible para la selección.

11. Arrastre una instancia de a `DemoMarqueeControl` la superficie de diseño de **Form1** .

12. En los <xref:System.Windows.Forms.Control.Click> controladores de eventos, invoque `Start` los `Stop` métodos y en `DemoMarqueeControl` .

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

13. Establezca el `MarqueeControlTest` proyecto como el proyecto de inicio y ejecútelo. Verá el formulario que muestra el `DemoMarqueeControl` . Seleccione el botón **iniciar** para iniciar la animación. Debería ver el parpadeo del texto y las luces desplazadas alrededor del borde.

## <a name="next-steps"></a>Pasos siguientes

El `MarqueeControlLibrary` muestra una implementación simple de controles personalizados y diseñadores asociados. Puede hacer que este ejemplo sea más sofisticado de varias maneras:

- Cambie los valores de propiedad para `DemoMarqueeControl` en el diseñador. Agregue más `MarqueBorder` controles y acoplelos dentro de sus instancias primarias para crear un efecto anidado. Experimente con diferentes configuraciones para `UpdatePeriod` y las propiedades relacionadas con la luz.

- Cree sus propias implementaciones de `IMarqueeWidget` . Por ejemplo, podría crear un "signo de neón" intermitente o un signo animado con varias imágenes.

- Personalizar aún más la experiencia en tiempo de diseño. Podría intentar sombrear más propiedades que <xref:System.Windows.Forms.Control.Enabled%2A> y <xref:System.Windows.Forms.Control.Visible%2A> , y agregar nuevas propiedades. Agregue nuevos verbos de diseñador para simplificar las tareas comunes, como acoplar los controles secundarios.

- Licencia de `MarqueeControl` .

- Controlar cómo se serializan los controles y cómo se genera el código para ellos. Para obtener más información, vea [generación y compilación de código fuente dinámico](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
