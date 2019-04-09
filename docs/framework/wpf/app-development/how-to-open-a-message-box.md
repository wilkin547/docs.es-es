---
title: Filtrar Abrir un cuadro de mensaje
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: cf7534cdee5e17d53e95294573023d660135e395
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101112"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="50919-102">Filtrar Abrir un cuadro de mensaje</span><span class="sxs-lookup"><span data-stu-id="50919-102">How to: Open a Message Box</span></span>
<span data-ttu-id="50919-103">En este ejemplo se muestra cómo abrir un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="50919-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50919-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50919-104">Example</span></span>  
 <span data-ttu-id="50919-105">Un cuadro de mensaje es un cuadro de diálogo modal prefabricado para mostrar información a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="50919-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="50919-106">Se abre un cuadro de mensaje mediante una llamada a estático <xref:System.Windows.MessageBox.Show%2A> método de la <xref:System.Windows.MessageBox> clase.</span><span class="sxs-lookup"><span data-stu-id="50919-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="50919-107">Cuando <xref:System.Windows.MessageBox.Show%2A> es llama, el mensaje se pasa mediante un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="50919-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="50919-108">Varias sobrecargas de <xref:System.Windows.MessageBox.Show%2A> le permiten configurar cómo aparecerá un cuadro de mensaje (consulte <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="50919-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="50919-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="50919-109">See also</span></span>

- [<span data-ttu-id="50919-110">Ejemplo de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="50919-110">MessageBox Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160023)
