---
title: Filtrar para copiar y pegar un control ElementHost en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666177"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Filtrar Copiar y pegar un control ElementHost

En este procedimiento se muestra cómo copiar un control de Windows Presentation Foundation (WPF) en Windows Forms en Visual Studio.

1. En Visual Studio, agregue un nuevo WPF <xref:System.Windows.Controls.UserControl> a un proyecto Windows Forms. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño.

2. En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y de `UserControl1` en **200**.

3. Establezca el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad en **azul**.

4. Compile el proyecto.

5. Abra `Form1` en el Diseñador de Windows Forms.

6. En el **cuadro de herramientas**, arrastre una `UserControl1` instancia de al formulario.

   La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.

7. Con `elementHost1` seleccionado, presione **Ctrl**+**C** para copiarlo en el portapapeles.

8. Presione **Ctrl**+**V** para pegar el control copiado en el formulario.

   Se crea <xref:System.Windows.Forms.Integration.ElementHost> un nuevo `elementHost2` control denominado en el formulario.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
