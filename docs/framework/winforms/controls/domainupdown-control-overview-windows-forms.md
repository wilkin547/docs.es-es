---
title: "Información general sobre el control DomainUpDown (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0692677b8ef596bb31b1869480603573a9ec98d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="domainupdown-control-overview-windows-forms"></a>Información general sobre el control DomainUpDown (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.DomainUpDown> del control es básicamente una combinación de un cuadro de texto y un par de botones para moverse hacia arriba o hacia abajo por una lista. El control muestra y establece una cadena de texto en una lista de opciones. El usuario puede seleccionar la cadena, haga clic en Subir y Bajar botones para desplazarse a través de una lista, presionando las teclas de dirección arriba y abajo o escribiendo una cadena que coincide con un elemento en la lista. Un uso posible para este control es para seleccionar elementos de una lista ordenada alfabéticamente de nombres.  
  
> [!NOTE]
>  Para ordenar la lista, establezca la <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> propiedad `true`.  
  
 La función de este control es muy similar al cuadro de lista o cuadro combinado, pero ocupa muy poco espacio.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades principales del control son <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, y <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. El <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad contiene la lista de objetos cuyos valores de texto se muestran en el control. Si <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> se establece en `false`, el control completa automáticamente el texto que escribe el usuario y lo hace coincidir con un valor en la lista. Si <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> se establece en `true`, al desplazarse más allá del último elemento irá al primer elemento en la lista y viceversa. Los métodos principales del control son <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> y <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Este control muestra solo las cadenas de texto. Si desea un control que muestra valores numéricos, utilice el <xref:System.Windows.Forms.NumericUpDown> control. Para obtener más información, consulte [información general del Control NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DomainUpDown>  
 [DomainUpDown (control)](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
