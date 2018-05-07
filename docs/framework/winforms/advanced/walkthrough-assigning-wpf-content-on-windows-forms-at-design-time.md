---
title: 'Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: abdeb2e77486d4f94f3d0543d94186168baae31c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de diseño
Este tutorial muestra cómo seleccionar los tipos de control de Windows Presentation Foundation (WPF) que desea mostrar en el formulario. Puede seleccionar cualquier tipo de control WPF incluido en su proyecto.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear los tipos de controles WPF.  
  
-   Seleccionar los controles WPF.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Crear un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `SelectingWpfContent`.  
  
## <a name="creating-the-wpf-control-types"></a>Crear los tipos de control WPF  
 Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### <a name="to-create-wpf-control-types"></a>Para crear tipos de control WPF  
  
1.  Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, consulte [Tutorial: crear nuevo WPF contenido en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, consulte [Cómo: seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades para `200`.  
  
4.  Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **contenido hospedado**.  
  
5.  Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.  
  
6.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades para `200`.  
  
7.  Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **Hosted Content 2**.  
  
 **Tenga en cuenta** en general, debería hospedar contenido WPF más sofisticado. El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.  
  
1.  Compile el proyecto.  
  
## <a name="selecting-wpf-controls"></a>Seleccionar controles WPF  
 Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.  
  
#### <a name="to-select-wpf-controls"></a>Para seleccionar controles WPF  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
3.  En el panel de etiquetas inteligentes para `elementHost1`, abra el **seleccionar contenido hospedable** lista desplegable.  
  
4.  Seleccione **UserControl2** en el cuadro de lista desplegable.  
  
     El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.  
  
5.  En el **propiedades** ventana, confirme que la <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl2**.  
  
6.  Desde el **cuadro de herramientas**, en la **interoperabilidad con WPF** grupo, arrastre un <xref:System.Windows.Forms.Integration.ElementHost> al formulario.  
  
     El nombre predeterminado del nuevo control es `elementHost2`.  
  
7.  En el panel de etiquetas inteligentes para `elementHost2`, abra el **seleccionar contenido hospedable** lista desplegable.  
  
8.  Seleccione **UserControl1** en la lista desplegable.  
  
9. El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
