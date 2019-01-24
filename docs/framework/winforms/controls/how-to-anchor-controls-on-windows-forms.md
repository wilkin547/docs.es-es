---
title: Procedimiento Delimitar controles en Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: d1f1fba28eec39202b37eb410a74df400ea461a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580947"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Procedimiento Delimitar controles en Windows Forms
Si está diseñando un formulario que el usuario puede cambiar el tamaño en tiempo de ejecución, deben cambiar el tamaño de los controles en el formulario y la posición de correctamente. Para cambiar el tamaño de controles dinámicamente con el formulario, puede usar el <xref:System.Windows.Forms.Control.Anchor%2A> propiedades de controles de Windows Forms. El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad define una posición de delimitación para el control. Cuando un control se acopla a un formulario y se cambia el tamaño del formulario, el control mantiene la distancia entre el control y las posiciones de anclaje. Por ejemplo, si tiene un <xref:System.Windows.Forms.TextBox> control que está anclada a la izquierda, derecha y los bordes de la parte inferior del formulario, como el tamaño del formulario, el <xref:System.Windows.Forms.TextBox> control cambia automáticamente de tamaño horizontalmente para que mantiene la misma distancia desde los lados derecho e izquierdos del formulario. Además, el control se coloca verticalmente para que su ubicación es siempre la misma distancia desde el borde inferior del formulario. Si no se encuentra delimitado respecto de un control y se cambia el tamaño del formulario, se cambia la posición del control en relación con los bordes del formulario.  
  
 El <xref:System.Windows.Forms.Control.Anchor%2A> propiedad interactúa con el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad. Para obtener más información, consulte [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-anchor-a-control-on-a-form"></a>Para anclar un control en un formulario  
  
1.  Seleccione el control que desee anclar.  
  
    > [!NOTE]
    >  Puede delimitar varios controles simultáneamente al presionar la tecla CTRL, haciendo clic en cada control para seleccionarlo y, a continuación, siga el resto de este procedimiento.  
  
2.  En el **propiedades** ventana, haga clic en la flecha situada a la derecha de la <xref:System.Windows.Forms.Control.Anchor%2A> propiedad.  
  
     Se muestra un editor que se muestra una cruz.  
  
3.  Para establecer un delimitador, haga clic en la parte superior, izquierda, derecha o la sección inferior de la cruz.  
  
     Los controles se fija con respecto a la parte superior y deja de forma predeterminada.  
  
4.  Para borrar un lado del control delimitado, haga clic en esa rama de la cruz.  
  
5.  Para cerrar el <xref:System.Windows.Forms.Control.Anchor%2A> editor de propiedades, haga clic en el <xref:System.Windows.Forms.Control.Anchor%2A> nuevo nombre de propiedad.  
  
 Cuando se muestre el formulario en tiempo de ejecución, el control cambia de tamaño para permanecer ubicado a la misma distancia desde el borde del formulario. La distancia desde el borde delimitado siempre permanece igual la distancia definida cuando se coloca el control en el Diseñador de Windows Forms.  
  
> [!NOTE]
>  Ciertos controles, como el <xref:System.Windows.Forms.ComboBox> controlar, tienen un límite de su alto. Delimitar el control a la parte inferior de su formulario o contenedor, no puede forzar el control a superar su límite de alto.  
  
 Los controles heredados deben estar `Protected` para poder ser delimitados. Para cambiar el nivel de acceso de un control, establezca su `Modifiers` propiedad en el **propiedades** ventana.  
  
## <a name="see-also"></a>Vea también
- [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)
- [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
- [Cómo: Acoplar controles en Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Diseñar Windows controles Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
