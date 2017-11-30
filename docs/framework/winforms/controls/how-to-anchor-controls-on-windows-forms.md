---
title: "Cómo: Delimitar controles en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c6f7cc527c7409ffecab2ac67386d0f819cce3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Cómo: Delimitar controles en formularios Windows Forms
Si va a diseñar un formulario que el usuario puede cambiar el tamaño en tiempo de ejecución, deben cambiar el tamaño de los controles en el formulario y la posición correctamente. Para cambiar el tamaño de los controles de forma dinámica con el formulario, puede usar el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad de los controles de formularios Windows Forms. El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad define una posición de delimitación para el control. Cuando un control se acopla a un formulario y se cambia el tamaño del formulario, el control mantiene la distancia entre el control y las posiciones de delimitación. Por ejemplo, si tiene un <xref:System.Windows.Forms.TextBox> control que está anclada a la izquierda, derecha y los bordes de la parte inferior del formulario, tal y como se cambia el tamaño del formulario, el <xref:System.Windows.Forms.TextBox> control cambia de tamaño horizontalmente para que mantiene la misma distancia desde los lados derecho e izquierdos del formulario. Además, el control se ubica verticalmente para que su ubicación es siempre la misma distancia desde el borde inferior del formulario. Si un control no se acopla y se cambia el tamaño del formulario, se cambia la posición del control en relación con los bordes del formulario.  
  
 El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad interactúa con el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad. Para obtener más información, consulte [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-anchor-a-control-on-a-form"></a>Para fijar un control en un formulario  
  
1.  Seleccione el control que desee anclar.  
  
    > [!NOTE]
    >  Se pueden delimitar varios controles simultáneamente al presionar la tecla CTRL, haga clic en cada control para seleccionarlo y, a continuación, siguiendo el resto de este procedimiento.  
  
2.  En el **propiedades** ventana, haga clic en la flecha situada a la derecha de la <xref:System.Windows.Forms.Control.Anchor%2A> propiedad.  
  
     Se muestra un editor que muestra una cruz.  
  
3.  Para establecer un delimitador, haga clic en la parte superior, izquierda, derecha o sección de la parte inferior de la cruz.  
  
     Los controles se fija con respecto a la parte superior y deja de forma predeterminada.  
  
4.  Para borrar un lado del control que ha sido anclado, haga clic en el brazo correspondiente de la cruz.  
  
5.  Para cerrar la <xref:System.Windows.Forms.Control.Anchor%2A> editor de propiedades, haga clic en el <xref:System.Windows.Forms.Control.Anchor%2A> nuevo nombre de propiedad.  
  
 Cuando se muestre el formulario en tiempo de ejecución, el control cambia de tamaño para mantener la posición en la misma distancia desde el borde del formulario. La distancia desde el borde delimitado siempre permanece igual la distancia definida cuando se coloca el control en el Diseñador de Windows Forms.  
  
> [!NOTE]
>  Ciertos controles, como el <xref:System.Windows.Forms.ComboBox> controlar, tienen un límite de su alto. Delimitar el control a la parte inferior de su formulario o contenedor, no puede forzar el control supere el límite de alto.  
  
 Los controles heredados deben estar `Protected` para poder ser delimitados. Para cambiar el nivel de acceso de un control, establezca su `Modifiers` propiedad en el **propiedades** ventana.  
  
## <a name="see-also"></a>Vea también  
 [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Procedimiento para acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Tutorial: Diseñar controles de Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
