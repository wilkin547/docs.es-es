---
title: DomainUpDown (Control, formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: c23f374f1ec9cab6e43b12d32b97c40533ac36cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown (Control, formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.DomainUpDown> control es similar a una combinación de un cuadro de texto y un par de botones para moverse hacia arriba o hacia abajo por una lista. El control muestra y establece una cadena de texto en una lista de opciones. El usuario puede seleccionar la cadena, haga clic en Subir y Bajar botones para desplazarse a través de una lista, presionando las teclas de dirección arriba y abajo o escribiendo una cadena que coincide con un elemento en la lista. Un uso posible para este control es para seleccionar elementos de una lista ordenada alfabéticamente de nombres. (Para ordenar la lista, establezca la <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> propiedad `true`.) La función de este control es muy similar al cuadro de lista o cuadro combinado, pero ocupa muy poco espacio.  
  
 Las propiedades principales del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. El <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad contiene la lista de objetos cuyos valores de texto se muestran en el control. Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> se establece en `false`, el control completa automáticamente el texto que escribe el usuario y lo hace coincidir con un valor en la lista. Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> se establece en `true`, al desplazarse más allá del último elemento irá al primer elemento en la lista y viceversa. Los métodos principales del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control muestra solo las cadenas de texto. Si desea un control que muestra valores numéricos, utilice el <xref:System.Windows.Forms.NumericUpDown> control. Para obtener más información, consulte [NumericUpDown Control](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre el control DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 Presenta los conceptos generales de la <xref:System.Windows.Forms.DomainUpDown> control, lo que permite a los usuarios examinar y seleccionar de una lista de cadenas de texto.  
  
 [Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Describe cómo especificar las cadenas de texto el <xref:System.Windows.Forms.DomainUpDown> control debe mostrar.  
  
 [Quitar elementos de los controles DomainUpDown de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Describe cómo eliminar elementos de la <xref:System.Windows.Forms.DomainUpDown> control en el código.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DomainUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros...  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Controles que puede utilizar en Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.
