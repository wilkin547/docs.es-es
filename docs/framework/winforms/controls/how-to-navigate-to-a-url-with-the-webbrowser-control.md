---
title: "C&#243;mo: Desplazarse a una direcci&#243;n URL con el control WebBrowser | Microsoft Docs"
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
  - "WebBrowser.Navigate"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], WebBrowser (control)"
  - "direcciones URL, navegar"
  - "WebBrowser (control) [Windows Forms], ejemplos"
  - "WebBrowser (control) [Windows Forms], explorar direcciones URL"
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Desplazarse a una direcci&#243;n URL con el control WebBrowser
En el ejemplo de código siguiente se muestra la forma de navegar por el control <xref:System.Windows.Forms.WebBrowser> a una dirección URL específica.  
  
 Para determinar cuándo se carga el nuevo documento totalmente, controle el evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>.  Para obtener una descripción de este evento, vea [Cómo: Imprimir con un control WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).  
  
## Ejemplo  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.  
  
-   Referencias a los ensamblados `System` y `System.Windows.Forms`.  
  
## Vea también  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=fullName>   
 [WebBrowser \(Control\)](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)   
 [Cómo: Imprimir con un control WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)