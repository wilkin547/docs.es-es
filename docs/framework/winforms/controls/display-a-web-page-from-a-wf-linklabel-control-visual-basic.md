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
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="3e144-102">Cómo: Mostrar una página Web desde un control LinkLabel de formularios Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e144-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="3e144-103">En este ejemplo se muestra una página web en el explorador predeterminado cuando un usuario hace clic en un control de <xref:System.Windows.Forms.LinkLabel> de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3e144-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e144-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e144-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e144-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3e144-105">Compiling the Code</span></span>  
 <span data-ttu-id="3e144-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="3e144-106">This example requires:</span></span>  
  
- <span data-ttu-id="3e144-107">Un Windows Form denominado `Form1`.</span><span class="sxs-lookup"><span data-stu-id="3e144-107">A Windows Form named `Form1`.</span></span>  
  
- <span data-ttu-id="3e144-108">Control <xref:System.Windows.Forms.LinkLabel> denominado `LinkLabel1`.</span><span class="sxs-lookup"><span data-stu-id="3e144-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
- <span data-ttu-id="3e144-109">Una conexión a Internet activa.</span><span class="sxs-lookup"><span data-stu-id="3e144-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3e144-110">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3e144-110">.NET Framework Security</span></span>  
 <span data-ttu-id="3e144-111">La llamada al método <xref:System.Diagnostics.Process.Start%2A> requiere plena confianza.</span><span class="sxs-lookup"><span data-stu-id="3e144-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="3e144-112">Para más información, consulte <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="3e144-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e144-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e144-113">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="3e144-114">LinkLabel (control)</span><span class="sxs-lookup"><span data-stu-id="3e144-114">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
