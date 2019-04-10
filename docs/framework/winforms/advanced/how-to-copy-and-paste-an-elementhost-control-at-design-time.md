---
title: Filtrar para copiar y pegar un control ElementHost en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: e8bc4aa4ecd2bff2981b7d4faf1e270337f346e7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346215"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>Filtrar para copiar y pegar un control ElementHost en tiempo de diseño
Este procedimiento muestra cómo copiar un control de Windows Presentation Foundation (WPF) en un formulario de Windows.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>Para copiar y pegar un control ElementHost en tiempo de diseño  
  
1. Agregue un nuevo WPF <xref:System.Windows.Controls.UserControl> a su proyecto de Windows Forms. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2. En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades de `UserControl1` a `200`.  
  
3. Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Blue`.  
  
4. Compile el proyecto.  
  
5. Abra `Form1` en el Diseñador de Windows Forms.  
  
6. Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
7. Con `elementHost1` seleccionado, presione CTRL+C para copiarlo en el Portapapeles.  
  
8. Presione CTRL+V para pegar el control copiado en el formulario.  
  
     Un nuevo <xref:System.Windows.Forms.Integration.ElementHost> control denominado `elementHost2` se crea en el formulario.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
