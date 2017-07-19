---
title: "Display of Asian Characters with the ImeMode Property | Microsoft Docs"
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
  - "Asian languages, displaying with ImeMode"
  - "Chinese characters, displaying with ImeMode"
  - "IME mode"
  - "Japanese characters, displaying with ImeMode"
  - "international applications [Windows Forms], character display"
  - "international characters"
  - "Korean characters"
  - "Asian languages"
  - "Input Method Editor (IME), mode"
  - "localization [Windows Forms], character sets"
  - "IMEMode property"
  - "globalization [Windows Forms], character sets"
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Display of Asian Characters with the ImeMode Property
Los formularios y controles usan la propiedad <xref:System.Windows.Forms.Control.ImeMode%2A> para imponer un modo determinado a un editor de métodos de entrada \(Input Method Editor, IME\).  El IME es un componente esencial para escribir scripts en chino, japonés y coreano, ya que estos sistemas de escritura tienen más caracteres que los que se pueden codificar para un teclado normal.  Por ejemplo, si sólo se desea permitir caracteres ASCII en un cuadro de texto determinado,  se puede establecer la propiedad <xref:System.Windows.Forms.Control.ImeMode%2A> en <xref:System.Windows.Forms.ImeMode> y los usuarios sólo podrán escribir caracteres ASCII en dicho cuadro de texto.  El valor predeterminado de la propiedad <xref:System.Windows.Forms.Control.ImeMode%2A> es <xref:System.Windows.Forms.ImeMode>; por tanto, si se establece la propiedad para un formulario, todos sus controles heredarán esa configuración.  Para obtener más información, vea [Control.ImeMode \(Propiedad\)](frlrfSystemWindowsFormsControlClassImeModeTopic) e [ImeMode \(Enumeración\)](frlrfSystemWindowsFormsImeModeClassTopic).  
  
## Vea también  
 [Globalizing Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)