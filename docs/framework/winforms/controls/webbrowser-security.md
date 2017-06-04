---
title: "Seguridad de WebBrowser | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "seguridad [Windows Forms], WebBrowser (control)"
  - "WebBrowser (control) [Windows Forms], seguridad"
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Seguridad de WebBrowser
El control <xref:System.Windows.Forms.WebBrowser> está diseñado para funcionar sólo en plena confianza.  El contenido HTML mostrado en el control puede proceder de servidores Web externos y puede contener código no administrado en forma de scripts o controles Web.  El uso del control <xref:System.Windows.Forms.WebBrowser> en esta situación no es menos seguro que utilizar Internet Explorer, pero el control <xref:System.Windows.Forms.WebBrowser> administrado no evita que se ejecute el código no administrado.  
  
 Para obtener más información sobre los problemas de seguridad relativos al control ActiveX `WebBrowser` subyacente, vea el tema referente al [control WebBrowser](http://go.microsoft.com/fwlink/?LinkId=198812).  
  
## Vea también  
 <xref:System.Windows.Forms.WebBrowser>   
 [Información general sobre el control WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [WebBrowser \(Control\)](http://go.microsoft.com/fwlink/?LinkId=198812)