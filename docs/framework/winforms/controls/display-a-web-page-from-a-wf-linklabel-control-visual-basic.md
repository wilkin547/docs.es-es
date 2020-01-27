---
title: Mostrar página web desde el control LinkLabel (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745919"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Cómo: Mostrar una página Web desde un control LinkLabel de formularios Windows Forms (Visual Basic)
En este ejemplo se muestra una página web en el explorador predeterminado cuando un usuario hace clic en un control de <xref:System.Windows.Forms.LinkLabel> de Windows Forms.  
  
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
  
- Un Windows Form denominado `Form1`.  
  
- Control <xref:System.Windows.Forms.LinkLabel> denominado `LinkLabel1`.  
  
- Una conexión a Internet activa.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 La llamada al método <xref:System.Diagnostics.Process.Start%2A> requiere plena confianza. Para obtener más información, vea <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.LinkLabel>
- [LinkLabel (control)](linklabel-control-windows-forms.md)
