---
title: 'Tutorial: Asignar contenido de WPF en formularios Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: b4efef869c96ddb4e58445e45ecad12b5658f9f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343355"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Asignar contenido de WPF en formularios Windows Forms en tiempo de diseño
Este tutorial muestra cómo seleccionar los tipos de control de Windows Presentation Foundation (WPF) que desea mostrar en el formulario. Puede seleccionar cualquier tipo de control WPF incluido en su proyecto.

 En este tutorial, realizará las tareas siguientes:

-   Crear el proyecto.

-   Crear los tipos de controles WPF.

-   Seleccionar los controles WPF.

> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   Visual Studio 2012.  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `SelectingWpfContent`.  
  
## <a name="creating-the-wpf-control-types"></a>Crear los tipos de control WPF  
 Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### <a name="to-create-wpf-control-types"></a>Para crear tipos de control WPF  
  
1. Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2. En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, vea [Cómo: Seleccionar y mover elementos en la superficie de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).  
  
3. En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.  
  
4. Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **contenido hospedado**.  
  
5. Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.  
  
6. En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.  
  
7. Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **Hosted Content 2**.  
  
 **Tenga en cuenta** en general, debería hospedar contenido WPF más sofisticado. El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.  
  
1. Compile el proyecto.  
  
## <a name="selecting-wpf-controls"></a>Seleccionar controles WPF  
 Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.  
  
#### <a name="to-select-wpf-controls"></a>Para seleccionar controles WPF  
  
1. Abra `Form1` en el Diseñador de Windows Forms.  
  
2. En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
3. En el panel de etiquetas inteligentes para `elementHost1`, abra el **seleccionar contenido hospedable** lista desplegable.  
  
4. Seleccione **UserControl2** desde el cuadro de lista desplegable.  
  
     El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.  
  
5. En el **propiedades** ventana, confirme que la <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl2**.  
  
6. Desde el **cuadro de herramientas**, en el **interoperabilidad con WPF** grupo, arrastre un <xref:System.Windows.Forms.Integration.ElementHost> al formulario.  
  
     El nombre predeterminado del nuevo control es `elementHost2`.  
  
7. En el panel de etiquetas inteligentes para `elementHost2`, abra el **seleccionar contenido hospedable** lista desplegable.  
  
8. Seleccione **UserControl1** en la lista desplegable.  
  
9. El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
