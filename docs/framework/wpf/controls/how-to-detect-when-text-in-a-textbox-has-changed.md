---
title: "Cómo: Detectar cuándo cambia el texto en un control TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ef1da879026d8cbefd6ef1baeb6c315e0ea1c02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="c6ff4-102">Cómo: Detectar cuándo cambia el texto en un control TextBox</span><span class="sxs-lookup"><span data-stu-id="c6ff4-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="c6ff4-103">Este ejemplo muestra cómo usar la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento para ejecutar un método cada vez que el texto de un <xref:System.Windows.Controls.TextBox> control ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="c6ff4-104">En la clase de código subyacente para la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el <xref:System.Windows.Controls.TextBox> control que desea supervisar para realizar cambios, inserte un método al que llamar cuando la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadena el evento.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="c6ff4-105">Este método debe tener una firma que coincida con lo que se espera por el <xref:System.Windows.Controls.TextChangedEventHandler> delegar.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="c6ff4-106">Se llama al controlador de eventos cada vez que el contenido de la <xref:System.Windows.Controls.TextBox> control se cambian, por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="c6ff4-107">**Nota:** este evento desencadena cuando el <xref:System.Windows.Controls.TextBox> control se crea y se rellena inicialmente con el texto.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ff4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6ff4-108">Example</span></span>  
 <span data-ttu-id="c6ff4-109">En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define su <xref:System.Windows.Controls.TextBox> controlar, especifique la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> atributo con un valor que coincida con el nombre del método de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="c6ff4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6ff4-110">Example</span></span>  
 <span data-ttu-id="c6ff4-111">En la clase de código subyacente para la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el <xref:System.Windows.Controls.TextBox> control que desea supervisar para realizar cambios, inserte un método al que llamar cuando la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadena el evento.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="c6ff4-112">Este método debe tener una firma que coincida con lo que se espera por el <xref:System.Windows.Controls.TextChangedEventHandler> delegar.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="c6ff4-113">Se llama al controlador de eventos cada vez que el contenido de la <xref:System.Windows.Controls.TextBox> control se cambian, por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="c6ff4-114">**Nota:** este evento desencadena cuando el <xref:System.Windows.Controls.TextBox> control se crea y se rellena inicialmente con el texto.</span><span class="sxs-lookup"><span data-stu-id="c6ff4-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="c6ff4-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6ff4-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ff4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6ff4-116">See Also</span></span>  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [<span data-ttu-id="c6ff4-117">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="c6ff4-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="c6ff4-118">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="c6ff4-118">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
