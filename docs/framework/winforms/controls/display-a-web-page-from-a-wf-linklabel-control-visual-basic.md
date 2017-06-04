---
title: "C&#243;mo: Mostrar una p&#225;gina Web desde un control LinkLabel de formularios Windows Forms (Visual Basic) | Microsoft Docs"
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
  - "LinkLabel1_LinkClicked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], LinkLabel (control)"
  - "vincular, a páginas Web desde formularios"
  - "LinkLabel (control) [Windows Forms], ejemplos"
  - "páginas web, mostrar"
  - "Windows Forms, vincular a páginas Web"
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Mostrar una p&#225;gina Web desde un control LinkLabel de formularios Windows Forms (Visual Basic)
En este ejemplo se muestra una página web en el explorador predeterminado cuando un usuario hace clic en un control <xref:System.Windows.Forms.LinkLabel> de formularios Windows Forms.  
  
## Ejemplo  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un Windows Form denominado `Form1`.  
  
-   Un control <xref:System.Windows.Forms.LinkLabel> denominado `LinkLabel1`.  
  
-   Una conexión a Internet activa.  
  
## Seguridad de .NET Framework  
 La llamada al método <xref:System.Diagnostics.Process.Start%2A> requiere plena confianza.  Para obtener más información, vea <xref:System.Security.SecurityException>.  
  
## Vea también  
 <xref:System.Windows.Forms.LinkLabel>   
 [LinkLabel \(Control\)](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)