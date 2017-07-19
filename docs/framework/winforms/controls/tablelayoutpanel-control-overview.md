---
title: "Informaci&#243;n general sobre el control TableLayoutPanel | Microsoft Docs"
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
  - "TableLayoutPanel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], cambiar el tamaño"
  - "diseño [Windows Forms], TableLayoutPanel (control)"
  - "controles de tamaño variable"
  - "TableLayoutPanel (control) [Windows Forms], acerca del control TableLayoutPanel"
  - "controles de Windows Forms, cambio de tamaño proporcional"
  - "Windows Forms, cambio de tamaño de controles proporcional"
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre el control TableLayoutPanel
El control <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula.  Como el diseño se realiza en tiempo de diseño y en tiempo de ejecución, puede cambiar dinámicamente cuando cambie el entorno de la aplicación.  Esto proporciona a los controles del panel la capacidad de ajustar el tamaño proporcionalmente para poder responder a cambios como el ajuste de tamaño del control primario o el cambio de longitud del texto debido a la localización.  
  
 Cualquier control de Windows Forms puede ser un control secundario del control <xref:System.Windows.Forms.TableLayoutPanel>, incluidas otras instancias de <xref:System.Windows.Forms.TableLayoutPanel>.  Esto permite construir diseños sofisticados que se adaptan a los cambios en tiempo de ejecución.  
  
 El control <xref:System.Windows.Forms.TableLayoutPanel> puede expandirse para acomodar nuevos controles cuando se agreguen, dependiendo del valor de las propiedades <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> y <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>.  Establecer las propiedades <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> o <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> en un valor de 0 especifica que el <xref:System.Windows.Forms.TableLayoutPanel> se desenlazará en la dirección correspondiente.  
  
 También puede controlar la dirección de expansión \(horizontal o vertical\) cuando el control <xref:System.Windows.Forms.TableLayoutPanel> se llene de controles secundarios.  De forma predeterminada, el control <xref:System.Windows.Forms.TableLayoutPanel> se expande hacia abajo agregando filas.  
  
 Si quiere que el comportamiento de las filas y columnas sea diferente del predeterminado, puede controlar las propiedades de las filas y columnas mediante las propiedades <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> y <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.  Puede establecer las propiedades de las filas o columnas individualmente.  
  
 El control <xref:System.Windows.Forms.TableLayoutPanel> agrega las siguientes propiedades a sus controles secundarios: `Cell`, `Column`, `Row`, `ColumnSpan` y `RowSpan`.  
  
 Puede combinar las celdas del control <xref:System.Windows.Forms.TableLayoutPanel> estableciendo las propiedades `ColumnSpan` o `RowSpan` de un control secundario.  
  
1.  [Cómo: Alinear y expandir un control en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171688%20\(v=vs.110\))  
  
2.  [Cómo: Abarcar filas y columnas en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171688%20\(v=vs.110\))  
  
3.  [Cómo: Editar columnas y filas en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171688%20\(v=vs.110\))  
  
4.  [Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
## Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutSettings>   
 [Cómo: Crear un diseño de formularios Windows Forms que sea apropiado para la localización](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)   
 [Cómo: Crear Windows Forms de entrada de datos de tamaño variable](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)   
 [Procedimientos recomendados para el control TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)