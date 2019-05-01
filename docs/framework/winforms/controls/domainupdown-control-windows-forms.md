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
ms.openlocfilehash: 83d674e3fb7ff7e715b75c635b891cd4e9703a21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972060"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown (Control, formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.DomainUpDown> control es similar a una combinación de un cuadro de texto y un par de botones para desplazarse hacia arriba o hacia abajo por una lista. El control muestra y establece una cadena de texto de una lista de opciones. El usuario puede seleccionar la cadena, haga clic en botones para desplazarse por una lista de arriba y abajo, presionando las teclas de dirección arriba y abajo o escribiendo una cadena que coincide con un elemento en la lista. Es un uso posible para este control para seleccionar elementos de una lista ordenada alfabéticamente de los nombres. (Para ordenar la lista, establezca la <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> propiedad `true`.) La función de este control es muy similar al cuadro de lista o cuadro combinado, pero ocupa poco espacio.  
  
 Las propiedades claves del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. El <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad contiene la lista de objetos cuyos valores de texto se muestran en el control. Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> está establecido en `false`, el control completa automáticamente el texto que el usuario escribe y coincide con un valor de la lista. Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> está establecido en `true`, al desplazarse más allá del último elemento irá al primer elemento en la lista y viceversa. Los métodos clave del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control muestra solo las cadenas de texto. Si desea un control que muestra los valores numéricos, utilice el <xref:System.Windows.Forms.NumericUpDown> control. Para obtener más información, consulte [NumericUpDown Control](numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre el control DomainUpDown](domainupdown-control-overview-windows-forms.md)  
 Presenta los conceptos generales de la <xref:System.Windows.Forms.DomainUpDown> control, que permite a los usuarios examinar y seleccionar entre una lista de cadenas de texto.  
  
 [Cómo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Describe cómo especificar las cadenas de texto el <xref:System.Windows.Forms.DomainUpDown> control debe mostrar.  
  
 [Cómo: Quitar elementos de controles DomainUpDown de formularios Windows Forms](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Describe cómo eliminar elementos de la <xref:System.Windows.Forms.DomainUpDown> control en el código.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DomainUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros...  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Controles que puede utilizar en Windows Forms](controls-to-use-on-windows-forms.md)  
 Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.
