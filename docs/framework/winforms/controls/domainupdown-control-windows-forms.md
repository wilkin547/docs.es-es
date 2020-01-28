---
title: DomainUpDown (Control)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745830"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown (Control, formularios Windows Forms)
El control de <xref:System.Windows.Forms.DomainUpDown> de Windows Forms es similar a una combinación de un cuadro de texto y un par de botones para subir o bajar a través de una lista. El control muestra y establece una cadena de texto de una lista de opciones. Para seleccionar la cadena, el usuario puede hacer clic en los botones arriba y abajo para desplazarse por una lista; para ello, presione las teclas de flecha arriba y abajo, o bien escriba una cadena que coincida con un elemento de la lista. Un uso posible para este control es la selección de elementos de una lista ordenada alfabéticamente de nombres. (Para ordenar la lista, establezca la propiedad <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> en `true`). La función de este control es muy similar al cuadro de lista o cuadro combinado, pero ocupa muy poco espacio.  
  
 Las propiedades clave del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. La propiedad <xref:System.Windows.Forms.DomainUpDown.Items%2A> contiene la lista de objetos cuyos valores de texto se muestran en el control. Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> se establece en `false`, el control completa automáticamente el texto que el usuario escribe y lo hace coincidir con un valor de la lista. Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> se establece en `true`, el desplazamiento más allá del último elemento le llevará al primer elemento de la lista y viceversa. Los métodos clave del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control solo muestra cadenas de texto. Si desea un control que muestre valores numéricos, utilice el control <xref:System.Windows.Forms.NumericUpDown>. Para obtener más información, vea [NumericUpDown (control](numericupdown-control-windows-forms.md) ).  
  
## <a name="in-this-section"></a>Esta sección  
 [Información general sobre el control DomainUpDown](domainupdown-control-overview-windows-forms.md)  
 Presenta los conceptos generales del control <xref:System.Windows.Forms.DomainUpDown>, que permite a los usuarios examinar y seleccionar en una lista de cadenas de texto.  
  
 [Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Describe cómo especificar las cadenas de texto que debe mostrar el control <xref:System.Windows.Forms.DomainUpDown>.  
  
 [Quitar elementos de los controles DomainUpDown de formularios Windows Forms](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Describe cómo eliminar elementos del control <xref:System.Windows.Forms.DomainUpDown> en el código.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DomainUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Controles que puede utilizar en Windows Forms](controls-to-use-on-windows-forms.md)  
 Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.
