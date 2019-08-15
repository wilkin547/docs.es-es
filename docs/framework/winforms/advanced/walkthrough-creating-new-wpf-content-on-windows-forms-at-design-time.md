---
title: 'Tutorial: Crear contenido de WPF en formularios Windows Forms en tiempo de diseño'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 889e81053d4e2264755468446a4e1681216ae22e
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040375"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño

En este artículo se muestra cómo crear un control de Windows Presentation Foundation (WPF) para su uso en las aplicaciones basadas en Windows Forms.

En este tutorial, realizará las tareas siguientes:

- Crear el proyecto.

- Crear un nuevo control WPF.

- Agregar el nuevo control WPF a un Windows Form. El control WPF se hospeda en un control <xref:System.Windows.Forms.Integration.ElementHost>.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio

## <a name="create-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto de Windows Forms. Abra Visual Studio y cree un nuevo proyecto de **Windows Forms App (.NET Framework)** en Visual Basic o C# en `HostingWpf`visual denominado.

> [!NOTE]
> Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.

## <a name="create-a-new-wpf-control"></a>Crear un nuevo control WPF

Crear un nuevo control WPF y agregarlo al proyecto es tan fácil como agregar cualquier otro elemento al proyecto. El Diseñador de Windows Forms funciona con un tipo determinado de control denominado *control compuesto*o *control de usuario*. Para obtener más información acerca de los controles de usuario WPF, consulte <xref:System.Windows.Controls.UserControl>.

> [!NOTE]
> El tipo de <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> para WPF es distinto del tipo de control de usuario proporcionado por Windows Forms, que también se llama <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.

Para crear un control de WPF nuevo:

1. En **Explorador de soluciones**, agregue un nuevo proyecto **biblioteca de controles de usuario (.NET Framework) de WPF** a la solución. Use el nombre predeterminado de la biblioteca de controles, `WpfControlLibrary1`. El nombre predeterminado del control es `UserControl1.xaml`.

     Agregar el nuevo control tiene los siguientes efectos:

    - Se agrega el archivo UserControl1.xaml.

    - Se agrega el archivo UserControl1.xaml.cs o UserControl1.xaml.vb. Este archivo contiene el código subyacente de los controladores de eventos y otras implementaciones.

    - Se agregan referencias a ensamblados de WPF.

    - Se abre el archivo UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].

2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, consulte [Cómo Seleccione y mueva los elementos en el](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))superficie de diseño.

3. En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en **200**.

4. En el **cuadro de herramientas**, <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> arrastre un control hasta la superficie de diseño.

5. En la ventana **propiedades** , establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad en **contenido hospedado**.

    > [!NOTE]
    > Por lo general, debería hospedar contenido WPF más sofisticado. El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.

6. Compile el proyecto.

## <a name="add-a-wpf-control-to-a-windows-form"></a>Agregar un control WPF a Windows Forms

El nuevo control WPF está listo para usarse en el formulario. Windows Forms usa el <xref:System.Windows.Forms.Integration.ElementHost> control para hospedar contenido de WPF.

Para agregar un control de WPF a un Windows Form:

1. Abra `Form1` en el Diseñador de Windows Forms.

2. En el **cuadro de herramientas**, busque la pestaña etiquetada **WPFUserControlLibrary control de usuario de WPF**.

3. Arrastre una instancia de `UserControl1` hasta el formulario.

    - Se crea automáticamente un control <xref:System.Windows.Forms.Integration.ElementHost> en el formulario para hospedar el control WPF.

    - El <xref:System.Windows.Forms.Integration.ElementHost> control se denomina `elementHost1` y, en la ventana **propiedades** , puede ver que <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> su propiedad está establecida en **UserControl1**.

    - Se agregan referencias a ensamblados de WPF al proyecto.

    - El control `elementHost1` tiene un panel de etiquetas inteligentes que muestra las opciones de hospedaje disponibles.

4. En el panel de etiquetas inteligentes **tareas de ElementHost** , seleccione **acoplar en contenedor primario**.

5. Presione **F5** para compilar y ejecutar la aplicación.

## <a name="next-steps"></a>Pasos siguientes

Windows Forms y WPF son tecnologías diferentes, pero están diseñadas para interoperar estrechamente. Para proporcionar una apariencia y un comportamiento más completos en las aplicaciones, intente lo siguiente:

- Hospede un control de Windows Forms en una página WPF. Para obtener más información, vea [Tutorial: Hospedar un control de Windows Forms](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)en WPF.

- Aplique estilos visuales de Windows Forms a su contenido de WPF. Para obtener más información, consulte [Cómo Habilitar estilos visuales en una aplicación](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)híbrida.

- Cambie el estilo de su contenido de WPF. Para obtener más información, vea [Tutorial: Aplicar estilos al](walkthrough-styling-wpf-content.md)contenido de WPF.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
