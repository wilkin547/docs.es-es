---
title: 'Cómo: Copiar y pegar un control ElementHost en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e89510558274558e560bf810afe746e250ff26a4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459228"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Cómo: copiar y pegar un control ElementHost

En este procedimiento se muestra cómo copiar un control de Windows Presentation Foundation (WPF) en Windows Forms en Visual Studio.

1. En Visual Studio, agregue un nuevo <xref:System.Windows.Controls.UserControl> de WPF a un proyecto de Windows Forms. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. En la ventana **propiedades** , establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de `UserControl1` en **200**.

3. Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en **Blue**.

4. Compile el proyecto.

5. Abra `Form1` en el Diseñador de Windows Forms.

6. En el **cuadro de herramientas**, arrastre una instancia de `UserControl1` al formulario.

   La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.

7. Con `elementHost1` seleccionado, presione **Ctrl**+**C** para copiarlo en el portapapeles.

8. Presione **Ctrl**+**V** para pegar el control copiado en el formulario.

   En el formulario se crea un nuevo control de <xref:System.Windows.Forms.Integration.ElementHost> denominado `elementHost2`.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
