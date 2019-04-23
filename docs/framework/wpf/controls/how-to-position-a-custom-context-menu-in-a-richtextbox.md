---
title: Procedimiento Colocar un menú contextual personalizado en un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209429"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="0b302-102">Procedimiento Colocar un menú contextual personalizado en un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0b302-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="0b302-103">En este ejemplo se muestra cómo colocar un menú contextual personalizado para un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0b302-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="0b302-104">Cuando se implementa un menú contextual personalizado para un control **RichTextBox**, es responsable del control de la posición del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="0b302-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="0b302-105">De forma predeterminada, se abre un menú contextual personalizado en el centro del control **RichTextBox**.</span><span class="sxs-lookup"><span data-stu-id="0b302-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b302-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b302-106">Example</span></span>  
 <span data-ttu-id="0b302-107">Para invalidar el comportamiento de colocación predeterminado, agregue un agente de escucha para el <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> eventos.</span><span class="sxs-lookup"><span data-stu-id="0b302-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="0b302-108">En el ejemplo siguiente se muestra hacer esto mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0b302-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="0b302-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b302-109">Example</span></span>  
 <span data-ttu-id="0b302-110">El ejemplo siguiente muestra una implementación correspondiente <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> escucha de eventos.</span><span class="sxs-lookup"><span data-stu-id="0b302-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="0b302-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b302-111">See also</span></span>

- <span data-ttu-id="0b302-112">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="0b302-112">[RichTextBox Overview](richtextbox-overview.md)</span></span>
- [<span data-ttu-id="0b302-113">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="0b302-113">TextBox Overview</span></span>](textbox-overview.md)
