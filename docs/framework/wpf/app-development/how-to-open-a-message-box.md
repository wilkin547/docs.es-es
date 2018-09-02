---
title: 'Cómo: abrir un cuadro de mensaje'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: f05190030ed6324917348fa1926abd5385e30f7e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425817"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="6e44c-102">Cómo: abrir un cuadro de mensaje</span><span class="sxs-lookup"><span data-stu-id="6e44c-102">How to: Open a Message Box</span></span>
<span data-ttu-id="6e44c-103">En este ejemplo se muestra cómo abrir un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="6e44c-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e44c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e44c-104">Example</span></span>  
 <span data-ttu-id="6e44c-105">Un cuadro de mensaje es un cuadro de diálogo modal prefabricado para mostrar información a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6e44c-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="6e44c-106">Se abre un cuadro de mensaje mediante una llamada a estático <xref:System.Windows.MessageBox.Show%2A> método de la <xref:System.Windows.MessageBox> clase.</span><span class="sxs-lookup"><span data-stu-id="6e44c-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="6e44c-107">Cuando <xref:System.Windows.MessageBox.Show%2A> es llama, el mensaje se pasa mediante un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="6e44c-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="6e44c-108">Varias sobrecargas de <xref:System.Windows.MessageBox.Show%2A> le permiten configurar cómo aparecerá un cuadro de mensaje (consulte <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="6e44c-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="6e44c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e44c-109">See Also</span></span>  
 [<span data-ttu-id="6e44c-110">Ejemplo de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="6e44c-110">MessageBox Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160023)
