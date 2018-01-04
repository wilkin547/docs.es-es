---
title: Comportamiento de AutoSize en el control TableLayoutPanel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06bd0686b31b52ccb8580a545910339d2e2cd5bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>Comportamiento de AutoSize en el control TableLayoutPanel
## <a name="distinct-autosize-behaviors"></a>Distintos comportamientos de AutoSize  
 El <xref:System.Windows.Forms.TableLayoutPanel> control admite el comportamiento de ajuste automático de tamaño de las maneras siguientes:  
  
-   A través de la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad;  
  
-   A través de la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad en el <xref:System.Windows.Forms.TableLayoutPanel> estilos de fila y columna del control.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>La propiedad AutoSize con estilos de columna y fila  
 En la tabla siguiente se describe la interacción entre el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad y el <xref:System.Windows.Forms.TableLayoutPanel> estilos de fila y columna del control.  
  
|Ajuste automático de tamaño|Interacción de estilo|  
|----------------------|-----------------------|  
|`false`|El <xref:System.Windows.Forms.TableLayoutPanel> control avanza de izquierda a derecha y asigna espacio para la columna o fila o en el siguiente orden.<br /><br /> 1.  Si el <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad está establecida en <xref:System.Windows.Forms.SizeType.Absolute>, el número de píxeles especificado por <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> está asignada.<br />2.  Si el <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad está establecida en <xref:System.Windows.Forms.SizeType.AutoSize>, el número de píxeles devuelto por el control secundario <xref:System.Windows.Forms.Control.GetPreferredSize%2A> se asigna el método.<br />3.  Después de un espacio para todos los <xref:System.Windows.Forms.SizeType.Absolute> y <xref:System.Windows.Forms.SizeType.AutoSize> está asignado el columnas o filas, las columnas o filas con <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> establecido en <xref:System.Windows.Forms.SizeType.Percent> se usan para asignar proporcionalmente el espacio libre restante|  
|`true`|Similar a la interacción anterior, con la excepción que <xref:System.Windows.Forms.SizeType.Percent> columnas o filas adquieren un aspecto de ajuste automático de tamaño.<br /><br /> El <xref:System.Windows.Forms.TableLayoutPanel> control expande la columna o fila para crear espacio libre suficiente, por lo que ninguna columna o fila con <xref:System.Windows.Forms.SizeType.Percent> estilo recorta su contenido. El <xref:System.Windows.Forms.TableLayoutPanel> control asigna el nuevo espacio proporcionalmente conforme a la <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> propiedad.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Información general sobre el control TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
