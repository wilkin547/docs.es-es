---
title: "C&#243;mo: Buscar datos en un control DataRepeater (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, implementar la búsqueda"
  - "DataRepeater, buscar datos"
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Buscar datos en un control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Cuando utiliza un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> que contiene muchos registros, es posible que desee permitir a los usuarios buscar un registro concreto.  En lugar de buscar los datos en el propio control, puede implementar una búsqueda consultando el <xref:System.Windows.Forms.BindingSource> subyacente.  Si se encuentra el elemento, puede utilizar la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> para seleccionarlo y desplazarlo en la vista.  
  
### Para implementar la búsqueda  
  
1.  Arrastre un control <xref:System.Windows.Forms.TextBox> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
2.  En la ventana Propiedades, cambie la propiedad **Name** a SearchTextBox.  
  
3.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
4.  En la ventana Propiedades, cambie la propiedad **Name** a SearchButton.  Cambie la propiedad **Text** a Search.  
  
5.  Haga doble clic en el control <xref:System.Windows.Forms.Button> para abrir el Editor de código y agregue el código siguiente al controlador de eventos `SearchButton_Click`.  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-cs[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     Reemplace *ProductsBindingSource* por el nombre de <xref:System.Windows.Forms.BindingSource> para <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> y *ProductID* por el nombre del campo que desea buscar.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Cómo: Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)