---
title: 'Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
ms.openlocfilehash: 55b426fbe95bac269183a649ecd839175a8cbdda
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "44778479"
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a>Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes
En este tutorial se muestra cómo copiar un control de Windows Presentation Foundation (WPF) de un Windows Form a otro.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Copiar un control WPF.  
  
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
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `CopyElementHost`.  
  
## <a name="copying-a-wpf-control"></a>Copiar un control WPF  
 Después de agregar un control WPF al proyecto, puede copiarlo a otros formularios del proyecto.  
  
#### <a name="to-copy-a-wpf-control"></a>Para copiar un control WPF  
  
1.  Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, consulte [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Compile el proyecto.  
  
3.  Abra `Form1` en el Diseñador de Windows Forms.  
  
4.  Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
5.  Con `elementHost1` seleccionado, presione CTRL+C para copiarlo en el Portapapeles.  
  
6.  Agregue un nuevo Windows Form al proyecto. Use el nombre predeterminado para el tipo de formulario, `Form2`.  
  
7.  Con `Form2` abierto en el Diseñador de Windows Forms, presione CTRL+V para pegar una copia de `elementHost1` en el formulario.  
  
     El control copiado también se llama `elementHost1`, porque es un campo privado de la clase `Form2`. No hay ningún conflicto de nombres con el `elementHost1` en la clase `Form1`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
