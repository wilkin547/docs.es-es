---
title: "C&#243;mo: Crear un cuadro de di&#225;logo est&#225;ndar de interfaz de usuario mediante Grid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cuadros de diálogo, crear"
  - "Grid (control), crear, cuadro de diálogo"
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Crear un cuadro de di&#225;logo est&#225;ndar de interfaz de usuario mediante Grid
En este ejemplo se muestra cómo crear un cuadro de diálogo estándar de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] por medio del elemento <xref:System.Windows.Controls.Grid>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un cuadro de diálogo igual que **Ejecutar** en el sistema operativo [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 En el ejemplo se crea un elemento <xref:System.Windows.Controls.Grid> y se usan las clases <xref:System.Windows.Controls.ColumnDefinition> y <xref:System.Windows.Controls.RowDefinition> para definir cinco columnas y cuatro filas.  
  
 A continuación, se agrega y se coloca un elemento <xref:System.Windows.Controls.Image>, `RunIcon.png` para representar la imagen que se encuentra en el cuadro de diálogo.  La imagen se coloca en la primera columna y fila de <xref:System.Windows.Controls.Grid> \(la esquina superior izquierda\).  
  
 Luego, en el ejemplo, se agrega un elemento <xref:System.Windows.Controls.TextBlock> a la primera columna, que abarca las demás columnas de la primera fila.  Se agrega otro elemento <xref:System.Windows.Controls.TextBlock> a la segunda fila de la primera columna para representar el cuadro de texto **Abrir**.  El elemento <xref:System.Windows.Controls.TextBlock> que va a continuación representa el área de entrada de datos.  
  
 Por último, se agregan tres elementos <xref:System.Windows.Controls.Button> a la fila final, que representan los eventos **Aceptar**, **Cancelar** y **Examinar**.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.GridUnitType>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)