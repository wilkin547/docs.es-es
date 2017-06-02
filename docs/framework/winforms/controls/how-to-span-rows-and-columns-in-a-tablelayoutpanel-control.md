---
title: "C&#243;mo: Abarcar filas y columnas en un control TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "celdas, combinar"
  - "columnas [Windows Forms], abarcar"
  - "combinar celdas"
  - "filas [Windows Forms], abarcar"
  - "TableLayoutPanel (control) [Windows Forms], abarcar filas y columnas"
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Abarcar filas y columnas en un control TableLayoutPanel
Los controles de un control <xref:System.Windows.Forms.TableLayoutPanel> pueden abarcar filas y columnas adyacentes.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para abarcar columnas y filas  
  
1.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  
  
2.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** a la celda superior izquierda del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Establezca la propiedad **ColumSpan** del control <xref:System.Windows.Forms.Button> en 2.  Observe que el control <xref:System.Windows.Forms.Button> abarca la primera y segunda columnas.  
  
4.  Establezca la propiedad **RowSpan** del control <xref:System.Windows.Forms.Button> en 2.  Observe que el control <xref:System.Windows.Forms.Button> abarca la primera y segunda filas.  
  
5.  Establezca la propiedad **ColumSpan** del control <xref:System.Windows.Forms.Button> en 1.  Observe que el control <xref:System.Windows.Forms.Button> se mueve a la primera columna y abarca la primera y segunda fila.  
  
## Vea también  
 [TableLayoutPanel \(Control\)](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)