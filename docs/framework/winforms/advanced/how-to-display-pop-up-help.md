---
title: "Cómo: Mostrar ayuda emergente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d139c283d002ac76005f22385d83190144c5082
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-pop-up-help"></a>Cómo: Mostrar ayuda emergente
Una manera de mostrar la Ayuda en Windows Forms es a través de la **ayuda** situado en el lado derecho de la barra de título, accesible a través de la <xref:System.Windows.Forms.Form.HelpButton%2A> propiedad. Este tipo de visualización de la Ayuda está indicado para cuadros de diálogo. Los cuadros de diálogo que se muestran de forma modal (con el método <xref:System.Windows.Forms.Form.ShowDialog%2A>) tienen problemas para abrir los sistemas de Ayuda externos porque los cuadros de diálogo modales deben cerrarse antes de poder pasar el foco a otra ventana. Además, para usar el **ayuda** botón requiere que no hay ningún **minimizar** botón o **maximizar** botón se muestra en la barra de título. Esto es una convención estándar del cuadro de diálogo, mientras que los formularios normalmente tienen **minimizar** y **maximizar** botones.  
  
 Tenga en cuenta que también puede usar el componente <xref:System.Windows.Forms.HelpProvider> para vincular controles a archivos en un sistema de Ayuda, aunque haya implementado ayuda emergente. Para obtener más información, consulte [proporcionar ayuda en una aplicación de Windows](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-display-pop-up-help"></a>Para mostrar Ayuda emergente  
  
1.  Arrastre un [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) componente del cuadro de herramientas al formulario.  
  
     Se colocará en la bandeja, en la parte inferior del Diseñador de Windows Forms.  
  
2.  En la ventana de propiedades, establezca la propiedad <xref:System.Windows.Forms.Form.HelpButton%2A> en `true`. Se mostrará un botón con un signo de interrogación en el lado derecho de la barra de título del formulario.  
  
3.  Para que el <xref:System.Windows.Forms.Form.HelpButton%2A> se muestre, las propiedades <xref:System.Windows.Forms.Form.MinimizeBox%2A> y <xref:System.Windows.Forms.Form.MaximizeBox%2A> del formulario deben establecerse en `false`, la propiedad <xref:System.Windows.Forms.Form.ControlBox%2A> debe establecerse en `true` y la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> debe establecerse en uno de los siguientes valores: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> o <xref:System.Windows.Forms.FormBorderStyle.Sizable>.  
  
4.  Seleccione el control para el que quiere mostrar la Ayuda en el formulario y establezca la cadena de Ayuda en la ventana Propiedades. Ésta es la cadena de texto que se mostrará en una ventana similar a una [información sobre herramientas](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).  
  
5.  Presione **F5**.  
  
6.  Presione el **ayuda** situado en la barra de título y haga clic en el control en el que se establece la cadena de ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Controlar la ayuda mediante componentes Tooltip](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Integrar la Ayuda de usuario en Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
