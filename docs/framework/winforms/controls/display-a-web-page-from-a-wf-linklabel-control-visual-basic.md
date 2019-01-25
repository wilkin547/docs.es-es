---
title: Procedimiento Mostrar una página Web desde un Control LinkLabel de formularios de Windows (Visual Basic)
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
ms.openlocfilehash: 05b127099b85188b0df2f1f7821ceb147cc41e1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698965"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="f4d9c-102">Procedimiento Mostrar una página Web desde un Control LinkLabel de formularios de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4d9c-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="f4d9c-103">En este ejemplo se muestra una página Web en el explorador predeterminado cuando un usuario hace clic en un formulario Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span><span class="sxs-lookup"><span data-stu-id="f4d9c-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4d9c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4d9c-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4d9c-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f4d9c-105">Compiling the Code</span></span>  
 <span data-ttu-id="f4d9c-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="f4d9c-106">This example requires:</span></span>  
  
-   <span data-ttu-id="f4d9c-107">Un formulario de Windows denominado `Form1`.</span><span class="sxs-lookup"><span data-stu-id="f4d9c-107">A Windows Form named `Form1`.</span></span>  
  
-   <span data-ttu-id="f4d9c-108">Control <xref:System.Windows.Forms.LinkLabel> denominado `LinkLabel1`.</span><span class="sxs-lookup"><span data-stu-id="f4d9c-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
-   <span data-ttu-id="f4d9c-109">Una conexión activa a Internet.</span><span class="sxs-lookup"><span data-stu-id="f4d9c-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f4d9c-110">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f4d9c-110">.NET Framework Security</span></span>  
 <span data-ttu-id="f4d9c-111">La llamada a la <xref:System.Diagnostics.Process.Start%2A> método requiere plena confianza.</span><span class="sxs-lookup"><span data-stu-id="f4d9c-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="f4d9c-112">Para obtener más información, consulta <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="f4d9c-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d9c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4d9c-113">See also</span></span>
- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="f4d9c-114">LinkLabel (control)</span><span class="sxs-lookup"><span data-stu-id="f4d9c-114">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
