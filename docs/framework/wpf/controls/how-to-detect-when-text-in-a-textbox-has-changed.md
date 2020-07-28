---
title: 'Cómo: Detectar cuándo cambia el texto en un control TextBox'
description: Aprenda a usar el evento TextChanged para ejecutar un método cada vez que el texto de un control TextBox cambie en una aplicación Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166229"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="a8361-103">Cómo: Detectar cuándo cambia el texto en un control TextBox</span><span class="sxs-lookup"><span data-stu-id="a8361-103">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="a8361-104">En este ejemplo se muestra una manera de utilizar el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento para ejecutar un método cada vez que el texto de un <xref:System.Windows.Controls.TextBox> control ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="a8361-104">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="a8361-105">En la clase de código subyacente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el control en el que <xref:System.Windows.Controls.TextBox> desea supervisar los cambios, inserte un método al que llamar cada vez que se <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadene el evento.</span><span class="sxs-lookup"><span data-stu-id="a8361-105">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="a8361-106">Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.</span><span class="sxs-lookup"><span data-stu-id="a8361-106">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="a8361-107">Se llama al controlador de eventos cada vez que se cambia el contenido del <xref:System.Windows.Controls.TextBox> control, ya sea por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a8361-107">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="a8361-108">Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.</span><span class="sxs-lookup"><span data-stu-id="a8361-108">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="a8361-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8361-109">Example</span></span>

<span data-ttu-id="a8361-110">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define el <xref:System.Windows.Controls.TextBox> control, especifique el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> atributo con un valor que coincida con el nombre del método del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a8361-110">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="a8361-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8361-111">Example</span></span>

<span data-ttu-id="a8361-112">En la clase de código subyacente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el control en el que <xref:System.Windows.Controls.TextBox> desea supervisar los cambios, inserte un método al que llamar cada vez que se <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadene el evento.</span><span class="sxs-lookup"><span data-stu-id="a8361-112">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="a8361-113">Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.</span><span class="sxs-lookup"><span data-stu-id="a8361-113">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="a8361-114">Se llama al controlador de eventos cada vez que se cambia el contenido del <xref:System.Windows.Controls.TextBox> control, ya sea por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a8361-114">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="a8361-115">Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.</span><span class="sxs-lookup"><span data-stu-id="a8361-115">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="a8361-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8361-116">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="a8361-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8361-117">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="a8361-118">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="a8361-118">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="a8361-119">Información general sobre el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a8361-119">RichTextBox Overview</span></span>](richtextbox-overview.md)
