---
title: Ver varias líneas en el control TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728279"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms
De forma predeterminada, el control Windows Forms <xref:System.Windows.Forms.TextBox> muestra una sola línea de texto y no muestra barras de desplazamiento. Si el texto es más largo que el espacio disponible, solo parte del texto es visible. Puede cambiar este comportamiento predeterminado si establece las propiedades <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>y <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en los valores adecuados.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Para mostrar un retorno de carro en el control TextBox  
  
- Para mostrar un retorno de carro en un <xref:System.Windows.Forms.TextBox>de varias líneas, use la propiedad <xref:System.Environment.NewLine%2A>.  
  
     Tenga en cuenta que la interpretación de los caracteres de escape (\\) es específica del idioma. Visual Basic usa `Chr$(13) & Chr$(10)` para la combinación de caracteres de retorno de carro y avance de carro.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Para ver varias líneas en el control TextBox  
  
1. Establezca la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`. Si <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> es `true` (valor predeterminado), el texto del control aparecerá como uno o más párrafos; en caso contrario, aparecerá como una lista, en la que algunas líneas se pueden recortar en el borde del control.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en un valor apropiado.  
  
    |{2&gt;Value&lt;2}|Descripción|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Use este valor si el texto va a ser un párrafo que casi siempre se ajusta al control. El usuario puede usar el puntero del mouse para desplazarse por el control si el texto es demasiado largo para mostrarlo todos a la vez.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Use este valor si desea que se muestre una lista de líneas, algunas de las cuales pueden ser mayores que el ancho del control <xref:System.Windows.Forms.TextBox>.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Use este valor si la lista puede ser más larga que el alto del control.|  
  
3. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.  
  
    |{2&gt;Value&lt;2}|Descripción|  
    |-----------|-----------------|  
    |`false`|El texto del control no se ajustará automáticamente, por lo que se desplazará hacia la derecha hasta que se alcance un salto de línea. Use este valor si eligió <xref:System.Windows.Forms.ScrollBars.Horizontal> barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.Both>, arriba.|  
    |`true` (predeterminado)|No aparecerá la barra de desplazamiento horizontal. Use este valor si eligió <xref:System.Windows.Forms.ScrollBars.Vertical> barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.None>, arriba, para mostrar uno o más párrafos.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Controlar el punto de inserción en un control TextBox de Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de sólo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Seleccionar texto en el control TextBox de Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
