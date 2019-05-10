---
title: Procedimiento para mostrar ayuda emergente
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: bf3bcbff0cd6f3bbf71e96e748cb170d5ce68dfc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211400"
---
# <a name="how-to-display-pop-up-help"></a>Procedimiento Mostrar la Ayuda emergente

Es una manera de mostrar la Ayuda en Windows Forms a través de la **ayuda** situado en el lado derecho de la barra de título, accesible a través de la <xref:System.Windows.Forms.Form.HelpButton%2A> propiedad. Este tipo de visualización de la Ayuda está indicado para cuadros de diálogo. Los cuadros de diálogo que se muestran de forma modal (con el método <xref:System.Windows.Forms.Form.ShowDialog%2A>) tienen problemas para abrir los sistemas de Ayuda externos porque los cuadros de diálogo modales deben cerrarse antes de poder pasar el foco a otra ventana. Además, el uso de la **ayuda** botón requiere que no hay ningún **minimizar** botón o **maximizar** botón se muestra en la barra de título. Esta es una convención de cuadro de diálogo estándar, mientras que los formularios normalmente tienen **minimizar** y **maximizar** botones.

También puede usar el <xref:System.Windows.Forms.HelpProvider> componente para vincular controles a archivos en un sistema de ayuda, incluso si ha implementado Ayuda emergente. Para obtener más información, consulte [proporcionar ayuda en una aplicación de Windows](how-to-provide-help-in-a-windows-application.md).

## <a name="display-pop-up-help"></a>Mostrar la Ayuda emergente

1. En Visual Studio, arrastre un [HelpProvider](../controls/helpprovider-component-windows-forms.md) componente desde el cuadro de herramientas al formulario.

   Se colocará en la bandeja, en la parte inferior del Diseñador de Windows Forms.

2. En la ventana de propiedades, establezca la propiedad <xref:System.Windows.Forms.Form.HelpButton%2A> en `true`. Se mostrará un botón con un signo de interrogación en el lado derecho de la barra de título del formulario.

3. Para que el <xref:System.Windows.Forms.Form.HelpButton%2A> se muestre, las propiedades <xref:System.Windows.Forms.Form.MinimizeBox%2A> y <xref:System.Windows.Forms.Form.MaximizeBox%2A> del formulario deben establecerse en `false`, la propiedad <xref:System.Windows.Forms.Form.ControlBox%2A> debe establecerse en `true` y la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> debe establecerse en uno de los siguientes valores: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> o <xref:System.Windows.Forms.FormBorderStyle.Sizable>.

4. Seleccione el control para el que quiere mostrar la Ayuda en el formulario y establezca la cadena de Ayuda en la ventana Propiedades. Esta es la cadena de texto que se mostrará en una ventana similar a un [información sobre herramientas](../controls/tooltip-component-windows-forms.md).

5. Presione **F5**.

6. Presione el **ayuda** situado en la barra de título y haga clic en el control en el que se establece la cadena de ayuda.

## <a name="see-also"></a>Vea también

- [Controlar la ayuda mediante componentes Tooltip](control-help-using-tooltips.md)
- [Integrar la Ayuda de usuario en Windows Forms](integrating-user-help-in-windows-forms.md)
- [Windows Forms](../index.md)
