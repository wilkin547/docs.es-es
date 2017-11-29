---
title: "Cómo: Mostrar una página Web desde un control LinkLabel de formularios Windows Forms (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38ef165dc655fedbf682a21220d6a76532b18f6a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Cómo: Mostrar una página Web desde un control LinkLabel de formularios Windows Forms (Visual Basic)
Este ejemplo muestra una página Web en el explorador predeterminado cuando un usuario hace clic en un formulario Windows Forms <xref:System.Windows.Forms.LinkLabel> control.  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un formulario de Windows denominado `Form1`.  
  
-   Un control <xref:System.Windows.Forms.LinkLabel> llamado `LinkLabel1`.  
  
-   Una conexión a Internet activa.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 La llamada a la <xref:System.Diagnostics.Process.Start%2A> método requiere plena confianza. Para obtener más información, consulta <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.LinkLabel>  
 [LinkLabel (control)](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
