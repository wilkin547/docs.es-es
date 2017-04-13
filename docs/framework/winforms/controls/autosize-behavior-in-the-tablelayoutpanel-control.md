---
title: "Comportamiento de AutoSize en el control TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cambiar de tamaño de forma automática"
  - "AutoSize (propiedad), TableLayoutPanel (control)"
  - "AutoSizeMode (propiedad)"
  - "controles [Windows Forms], ajustar el tamaño"
  - "diseño [Windows Forms], AutoSize"
  - "adaptar formularios"
  - "ajustar el tamaño, automáticamente"
  - "TableLayoutPanel (control) [Windows Forms], comportamiento de AutoSize"
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Comportamiento de AutoSize en el control TableLayoutPanel
## Distintos comportamientos de AutoSize  
 El control <xref:System.Windows.Forms.TableLayoutPanel> admite las siguientes maneras del comportamiento de cambio de tamaño automático:  
  
-   A través de la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>;  
  
-   A través de la propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> en los estilos de fila y columna del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
### La propiedad AutoSize con estilos de fila y columna  
 En la tabla siguiente se describe la interacción entre la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> y los estilos de fila y columna del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
|Configuración de AutoSize|Interacción de estilo|  
|-------------------------------|---------------------------|  
|`false`|El control <xref:System.Windows.Forms.TableLayoutPanel> se realiza de izquierda a derecha y asigna el espacio para la columna o fila o en el orden siguiente.<br /><br /> 1.  Si la propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> se establece en <xref:System.Windows.Forms.SizeType>, se asigna el número de píxeles especificado por <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A>.<br />2.  Si la propiedad <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> se establece en <xref:System.Windows.Forms.SizeType>, se asigna el número de píxeles devuelto por el método <xref:System.Windows.Forms.Control.GetPreferredSize%2A> del control secundario.<br />3.  Después de que se haya asignado el espacio para todas las filas o columnas de <xref:System.Windows.Forms.SizeType> y <xref:System.Windows.Forms.SizeType>, se utilizan todas las filas o columnas con <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> establecidas en <xref:System.Windows.Forms.SizeType> para asignar proporcionalmente el espacio disponible restante.|  
|`true`|Similar a la interacción anterior, excepto que las columnas o filas de <xref:System.Windows.Forms.SizeType> adquieren un aspecto de cambio de tamaño automático.<br /><br /> El control <xref:System.Windows.Forms.TableLayoutPanel> amplía la columna o fila para crear el espacio necesario, de tal forma que ninguna columna o fila con estilo <xref:System.Windows.Forms.SizeType> recorte su contenido.  El control <xref:System.Windows.Forms.TableLayoutPanel> asigna proporcionalmente el nuevo espacio en función de la propiedad <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A>.|  
  
## Vea también  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Información general sobre el control TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)