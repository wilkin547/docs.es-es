---
title: Información general sobre el control DomainUpDown
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745862"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Información general sobre el control DomainUpDown (formularios Windows Forms)
El control Windows Forms <xref:System.Windows.Forms.DomainUpDown> es esencialmente una combinación de un cuadro de texto y un par de botones para subir o bajar por una lista. El control muestra y establece una cadena de texto de una lista de opciones. Para seleccionar la cadena, el usuario puede hacer clic en los botones arriba y abajo para desplazarse por una lista; para ello, presione las teclas de flecha arriba y abajo, o bien escriba una cadena que coincida con un elemento de la lista. Un uso posible para este control es la selección de elementos de una lista ordenada alfabéticamente de nombres.  
  
> [!NOTE]
> Para ordenar la lista, establezca la propiedad <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> en `true`.  
  
 La función de este control es muy similar al cuadro de lista o cuadro combinado, pero ocupa muy poco espacio.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades clave del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. La propiedad <xref:System.Windows.Forms.DomainUpDown.Items%2A> contiene la lista de objetos cuyos valores de texto se muestran en el control. Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> se establece en `false`, el control completa automáticamente el texto que el usuario escribe y lo hace coincidir con un valor de la lista. Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> se establece en `true`, el desplazamiento más allá del último elemento le llevará al primer elemento de la lista y viceversa. Los métodos clave del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control solo muestra cadenas de texto. Si desea un control que muestre valores numéricos, utilice el control <xref:System.Windows.Forms.NumericUpDown>. Para más información, consulte [información general sobre el control NumericUpDown](numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DomainUpDown>
- [DomainUpDown (control)](domainupdown-control-windows-forms.md)
