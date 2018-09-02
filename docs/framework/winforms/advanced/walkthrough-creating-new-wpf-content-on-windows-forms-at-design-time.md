---
title: 'Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: dc72b86a69d44ad282e30b000313b73211cad09c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43461753"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño

En este tema se muestra cómo crear un control de Windows Presentation Foundation (WPF) para usarlo en aplicaciones basadas en Windows Forms.

En este tutorial, realizará las tareas siguientes:

- Crear el proyecto.

- Crear un nuevo control WPF.

- Agregar el nuevo control WPF a un Windows Form. El control WPF se hospeda en un control <xref:System.Windows.Forms.Integration.ElementHost>.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio 2017

## <a name="creating-the-project"></a>Crear el proyecto

El primer paso es crear el proyecto de Windows Forms. Abra Visual Studio y cree un nuevo **Windows Forms App (.NET Framework)** proyecto en Visual Basic o Visual C# llamado `HostingWpf`.

> [!NOTE]
> Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.

## <a name="creating-a-new-wpf-control"></a>Crear un nuevo control WPF

Crear un nuevo control WPF y agregarlo al proyecto es tan fácil como agregar cualquier otro elemento al proyecto. El Diseñador de formularios de Windows funciona con un determinado tipo de control denominado *control compuesto*, o *control de usuario*. Para obtener más información acerca de los controles de usuario WPF, consulte <xref:System.Windows.Controls.UserControl>.

> [!NOTE]
> El tipo de <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> para WPF es distinto del tipo de control de usuario proporcionado por Windows Forms, que también se llama <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.

### <a name="to-create-a-new-wpf-control"></a>Para crear un nuevo control WPF

1. En **el Explorador de soluciones**, agregue un nuevo **biblioteca de controles de usuario de WPF (.NET Framework)** proyecto a la solución. Use el nombre predeterminado de la biblioteca de controles, `WpfControlLibrary1`. El nombre predeterminado del control es `UserControl1.xaml`.

     Agregar el nuevo control tiene los efectos siguientes:

    - Se agrega el archivo UserControl1.xaml.

    - Se agrega el archivo UserControl1.xaml.cs o UserControl1.xaml.vb. Este archivo contiene el código subyacente de los controladores de eventos y otras implementaciones.

    - Se agregan referencias a ensamblados de WPF.

    - Se abre el archivo UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].

2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, consulte [Cómo: seleccionar y mover elementos en la superficie de diseño](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).

3. En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a **200**.

4. Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control a la superficie de diseño.

5. En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **contenido hospedado**.

    > [!NOTE]
    > Por lo general, debería hospedar contenido WPF más sofisticado. El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.

6. Compile el proyecto.

## <a name="adding-a-wpf-control-to-a-windows-form"></a>Agregar un control WPF a un Windows Form

El nuevo control WPF está listo para usarse en el formulario. Windows Forms utiliza el <xref:System.Windows.Forms.Integration.ElementHost> control para hospedar contenido WPF.

### <a name="to-add-a-wpf-control-to-a-windows-form"></a>Para agregar un control WPF a un Windows Form

1. Abra `Form1` en el Diseñador de Windows Forms.

2. En el **cuadro de herramientas**, busque la pestaña **controles de usuario de WPF WPFUserControlLibrary**.

3. Arrastre una instancia de `UserControl1` hasta el formulario.

    - Se crea automáticamente un control <xref:System.Windows.Forms.Integration.ElementHost> en el formulario para hospedar el control WPF.

    - El <xref:System.Windows.Forms.Integration.ElementHost> control se denomina `elementHost1` y en el **propiedades** ventana, puede ver su <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl1**.

    - Se agregan referencias a ensamblados de WPF al proyecto.

    - El control `elementHost1` tiene un panel de etiquetas inteligentes que muestra las opciones de hospedaje disponibles.

4. En el **tareas de ElementHost** panel de etiquetas inteligentes, seleccione **acoplar en contenedor primario**.

5. Presione **F5** para compilar y ejecutar la aplicación.

## <a name="next-steps"></a>Pasos siguientes

Windows Forms y WPF son tecnologías diferentes, pero están diseñadas para interoperar estrechamente. Para proporcionar un aspecto y comportamiento en sus aplicaciones, pruebe lo siguiente:

- Hospede un control de Windows Forms en una página WPF. Para obtener más información, consulte [Tutorial: hospedar un Control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).

- Aplique estilos visuales de Windows Forms a su contenido de WPF. Para más información, vea [Cómo: Habilitar estilos visuales en una aplicación híbrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).

- Cambie el estilo de su contenido de WPF. Para obtener más información, consulte [Tutorial: aplicar estilos a contenido de WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
