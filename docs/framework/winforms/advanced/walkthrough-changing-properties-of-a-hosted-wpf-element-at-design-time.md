---
title: 'Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: 15cab9266af5840aa4b37a62b71bd5010b7a859a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741025"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño
Este tutorial muestra cómo cambiar los valores de propiedad de un control de Windows Presentation Foundation (WPF) hospedado en un Windows Form.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear el control WPF.  
  
-   Hospedar los controles WPF en un Windows Form.  
  
-   Use el Diseñador de WPF de Visual Studio para cambiar los valores de propiedad.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `WpfHost`.  
  
## <a name="creating-the-wpf-control"></a>Crear el control WPF  
 Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.  
  
#### <a name="to-create-wpf-controls"></a>Para crear controles WPF  
  
1.  Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, consulte [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad `Blue`.  
  
3.  Compile el proyecto.  
  
## <a name="changing-property-values-on-the-wpf-control"></a>Cambiar los valores de propiedad en el control WPF  
 La etiqueta inteligente <xref:System.Windows.Forms.Integration.ElementHost> permite cambiar fácilmente las propiedades del contenido WPF hospedado mediante WPF Designer.  
  
#### <a name="to-host-a-wpf-control"></a>Para hospedar un control WPF  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **cuadro de herramientas**, en el **controles de usuario de WPF** , haga doble clic `UserControl1` para crear una instancia de `UserControl1` en el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
3.  En el **tareas de ElementHost** panel de etiquetas inteligentes, seleccione **editar contenido hospedado**.  
  
     Se abre UserControl1.xaml en WPF Designer.  
  
4.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad `Red`.  
  
5.  Recompile el proyecto.  
  
6.  Abra `Form1` en el Diseñador de Windows Forms.  
  
     La instancia de `UserControl1` tiene un fondo rojo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
