---
title: Ver varias líneas en el control TextBox
description: Obtenga información sobre cómo ver varias líneas en el control TextBox Windows Forms estableciendo las propiedades Multiline, WordWrap y ScrollBars.
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
ms.openlocfilehash: e40d720bcd56366f4f06bfe2e2d347aaf9aa9d6c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174476"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms
De forma predeterminada, el <xref:System.Windows.Forms.TextBox> control Windows Forms muestra una sola línea de texto y no muestra barras de desplazamiento. Si el texto es más largo que el espacio disponible, solo parte del texto es visible. Puede cambiar este comportamiento predeterminado si establece las <xref:System.Windows.Forms.TextBox.Multiline%2A> propiedades, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> y <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en los valores adecuados.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Para mostrar un retorno de carro en el control TextBox  
  
- Para mostrar un retorno de carro en una línea múltiple <xref:System.Windows.Forms.TextBox> , utilice la <xref:System.Environment.NewLine%2A> propiedad.  
  
     Tenga en cuenta que la interpretación de los caracteres de escape ( \\ ) es específica del idioma. Visual Basic utiliza `Chr$(13) & Chr$(10)` para la combinación de caracteres de retorno de carro y avance de la alimentación.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Para ver varias líneas en el control TextBox  
  
1. Establezca la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`. Si <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> es `true` (valor predeterminado), el texto del control aparecerá como uno o más párrafos; de lo contrario, aparecerá como una lista, en la que algunas líneas se pueden recortar en el borde del control.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en un valor apropiado.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Use este valor si el texto va a ser un párrafo que casi siempre se ajusta al control. El usuario puede usar el puntero del mouse para desplazarse por el control si el texto es demasiado largo para mostrarlo todos a la vez.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Utilice este valor si desea mostrar una lista de líneas, algunas de las cuales pueden ser mayores que el ancho del <xref:System.Windows.Forms.TextBox> control.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Use este valor si la lista puede ser más larga que el alto del control.|  
  
3. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |`false`|El texto del control no se ajustará automáticamente, por lo que se desplazará hacia la derecha hasta que se alcance un salto de línea. Use este valor si ha elegido <xref:System.Windows.Forms.ScrollBars.Horizontal> barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.Both> , arriba.|  
    |`true` (valor predeterminado)|No aparecerá la barra de desplazamiento horizontal. Use este valor si ha elegido <xref:System.Windows.Forms.ScrollBars.Vertical> barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.None> , arriba, para mostrar uno o más párrafos.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedimiento para crear un cuadro de texto de solo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedimiento para insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
