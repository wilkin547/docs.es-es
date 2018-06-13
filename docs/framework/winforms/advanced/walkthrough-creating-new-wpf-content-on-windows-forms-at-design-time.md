---
title: 'Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 1ea0160530fea0f35c6d4746dc4bbca9439bc462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529014"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño
En este tema se muestra cómo crear un control de Windows Presentation Foundation (WPF) para usarlo en aplicaciones basadas en Windows Forms.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear un nuevo control WPF.  
  
-   Agregar el nuevo control WPF a un Windows Form. El control WPF se hospeda en un control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Crear un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `HostingWpf`.  
  
## <a name="creating-a-new-wpf-control"></a>Crear un nuevo control WPF  
 Crear un nuevo control WPF y agregarlo al proyecto es tan fácil como agregar cualquier otro elemento al proyecto. El Diseñador de Windows Forms funciona con un tipo determinado de control denominado *control compuesto*, o *control de usuario*. Para obtener más información acerca de los controles de usuario WPF, consulte <xref:System.Windows.Controls.UserControl>.  
  
> [!NOTE]
>  El tipo de <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> para WPF es distinto del tipo de control de usuario proporcionado por Windows Forms, que también se llama <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.  
  
#### <a name="to-create-a-new-wpf-control"></a>Para crear un nuevo control WPF  
  
1.  En **el Explorador de soluciones**, agregue un nuevo **biblioteca de controles de usuario de WPF** proyecto a la solución. Use el nombre predeterminado de la biblioteca de controles, `WpfControlLibrary1`. El nombre predeterminado del control es `UserControl1.xaml`.  
  
     Agregar el nuevo control tiene los siguientes efectos.  
  
    -   Se agrega el archivo UserControl1.xaml.  
  
    -   Se agrega el archivo UserControl1.xaml.cs o UserControl1.xaml.vb. Este archivo contiene el código subyacente de los controladores de eventos y otras implementaciones.  
  
    -   Se agregan referencias a ensamblados de WPF.  
  
    -   Se abre el archivo UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, consulte [Cómo: seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades para `200`.  
  
4.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control a la superficie de diseño.  
  
5.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **contenido hospedado**.  
  
    > [!NOTE]
    >  Por lo general, debería hospedar contenido WPF más sofisticado. El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.  
  
6.  Compile el proyecto.  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a>Agregar un control WPF a un Windows Form  
 El nuevo control WPF está listo para usarse en el formulario. Windows Forms usa el control <xref:System.Windows.Forms.Integration.ElementHost> para hospedar contenido WPF  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a>Para agregar un control WPF a un Windows Form  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **cuadro de herramientas**, busque la pestaña etiquetada como **controles de usuario de WPF WPFUserControlLibrary**.  
  
3.  Arrastre una instancia de `UserControl1` hasta el formulario.  
  
    -   Se crea automáticamente un control <xref:System.Windows.Forms.Integration.ElementHost> en el formulario para hospedar el control WPF.  
  
    -   El <xref:System.Windows.Forms.Integration.ElementHost> se denomina control `elementHost1` y en el **propiedades** ventana, puede ver su <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl1**.  
  
    -   Se agregan referencias a ensamblados de WPF al proyecto.  
  
    -   El control `elementHost1` tiene un panel de etiquetas inteligentes que muestra las opciones de hospedaje disponibles.  
  
4.  En el **tareas de ElementHost** panel de etiquetas inteligentes, seleccione **acoplar en contenedor principal**.  
  
5.  Presione F5 para compilar y ejecutar la aplicación.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Windows Forms y WPF son tecnologías diferentes, pero están diseñadas para interoperar estrechamente. Para proporcionar un aspecto y un comportamiento más enriquecido a sus aplicaciones, pruebe lo siguiente.  
  
-   Hospede un control de Windows Forms en una página WPF. Para obtener más información, consulte [Tutorial: hospedar un Control de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).  
  
-   Aplique estilos visuales de Windows Forms a su contenido de WPF. Para más información, vea [Cómo: Habilitar estilos visuales en una aplicación híbrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
-   Cambie el estilo de su contenido de WPF. Para obtener más información, consulte [Tutorial: aplicar estilos a contenido de WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
