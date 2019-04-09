---
title: Información general sobre el control DomainUpDown (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: bfe3e7239f77c6f1a0d9bb46a96c704653b43364
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102861"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Información general sobre el control DomainUpDown (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.DomainUpDown> control es básicamente una combinación de un cuadro de texto y un par de botones para desplazarse hacia arriba o hacia abajo a través de una lista. El control muestra y establece una cadena de texto de una lista de opciones. El usuario puede seleccionar la cadena, haga clic en botones para desplazarse por una lista de arriba y abajo, presionando las teclas de dirección arriba y abajo o escribiendo una cadena que coincide con un elemento en la lista. Es un uso posible para este control para seleccionar elementos de una lista ordenada alfabéticamente de los nombres.  
  
> [!NOTE]
>  Para ordenar la lista, establezca la <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> propiedad `true`.  
  
 La función de este control es muy similar al cuadro de lista o cuadro combinado, pero ocupa poco espacio.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades claves del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. El <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad contiene la lista de objetos cuyos valores de texto se muestran en el control. Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> está establecido en `false`, el control completa automáticamente el texto que el usuario escribe y coincide con un valor de la lista. Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> está establecido en `true`, al desplazarse más allá del último elemento irá al primer elemento en la lista y viceversa. Los métodos clave del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control muestra solo las cadenas de texto. Si desea un control que muestra los valores numéricos, utilice el <xref:System.Windows.Forms.NumericUpDown> control. Para obtener más información, consulte [información general del Control NumericUpDown](numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DomainUpDown>
- [Control DomainUpDown](domainupdown-control-windows-forms.md)
