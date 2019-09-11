---
title: Procedimiento Detectar cuándo cambia el texto en un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855621"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="dc6cb-102">Procedimiento Detectar cuándo cambia el texto en un control TextBox</span><span class="sxs-lookup"><span data-stu-id="dc6cb-102">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="dc6cb-103">En este ejemplo se muestra una manera de <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> utilizar el evento para ejecutar un método cada vez que <xref:System.Windows.Controls.TextBox> el texto de un control ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="dc6cb-104">En la clase [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de código subyacente del que contiene el <xref:System.Windows.Controls.TextBox> control en el que desea supervisar los cambios, inserte un método al que llamar cada vez <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> que se desencadene el evento.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="dc6cb-105">Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="dc6cb-106">Se llama al controlador de eventos cada vez que se <xref:System.Windows.Controls.TextBox> cambia el contenido del control, ya sea por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="dc6cb-107">Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-107">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="dc6cb-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc6cb-108">Example</span></span>

<span data-ttu-id="dc6cb-109">En que define el control, especifique el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> atributo con un valor que coincida con el nombre del método del controlador de eventos. <xref:System.Windows.Controls.TextBox> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6cb-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="dc6cb-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc6cb-110">Example</span></span>

<span data-ttu-id="dc6cb-111">En la clase [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de código subyacente del que contiene el <xref:System.Windows.Controls.TextBox> control en el que desea supervisar los cambios, inserte un método al que llamar cada vez <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> que se desencadene el evento.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="dc6cb-112">Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="dc6cb-113">Se llama al controlador de eventos cada vez que se <xref:System.Windows.Controls.TextBox> cambia el contenido del control, ya sea por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="dc6cb-114">Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.</span><span class="sxs-lookup"><span data-stu-id="dc6cb-114">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="dc6cb-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc6cb-115">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="dc6cb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc6cb-116">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="dc6cb-117">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="dc6cb-117">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="dc6cb-118">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="dc6cb-118">[RichTextBox Overview](richtextbox-overview.md)</span></span>
