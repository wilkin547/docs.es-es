---
title: Filtrar Detectar cuándo cambia el texto en un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 72441e53d21df47d34a0600dafdf0b4b04c11cad
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352378"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="e758a-102">Procedimiento Detectar cuándo cambia el texto en un control TextBox</span><span class="sxs-lookup"><span data-stu-id="e758a-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="e758a-103">En este ejemplo se muestra una forma de usar el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> eventos para ejecutar un método cada vez que el texto en un <xref:System.Windows.Controls.TextBox> control ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="e758a-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="e758a-104">En la clase de código subyacente para el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el <xref:System.Windows.Controls.TextBox> control que desea supervisar para realizar cambios, insertar un método para llamar cada vez que el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadena el evento.</span><span class="sxs-lookup"><span data-stu-id="e758a-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="e758a-105">Este método debe tener una firma que coincida con lo que espera el <xref:System.Windows.Controls.TextChangedEventHandler> delegar.</span><span class="sxs-lookup"><span data-stu-id="e758a-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="e758a-106">Se llama al controlador de eventos cada vez que el contenido de la <xref:System.Windows.Controls.TextBox> control cambian, por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e758a-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="e758a-107">**Nota:** Este evento desencadena cuando el <xref:System.Windows.Controls.TextBox> control se crea y se rellena inicialmente con el texto.</span><span class="sxs-lookup"><span data-stu-id="e758a-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e758a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e758a-108">Example</span></span>  
 <span data-ttu-id="e758a-109">En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define su <xref:System.Windows.Controls.TextBox> controlar, especifique el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> atributo con un valor que coincida con el nombre del método de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="e758a-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="e758a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e758a-110">Example</span></span>  
 <span data-ttu-id="e758a-111">En la clase de código subyacente para el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el <xref:System.Windows.Controls.TextBox> control que desea supervisar para realizar cambios, insertar un método para llamar cada vez que el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadena el evento.</span><span class="sxs-lookup"><span data-stu-id="e758a-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="e758a-112">Este método debe tener una firma que coincida con lo que espera el <xref:System.Windows.Controls.TextChangedEventHandler> delegar.</span><span class="sxs-lookup"><span data-stu-id="e758a-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="e758a-113">Se llama al controlador de eventos cada vez que el contenido de la <xref:System.Windows.Controls.TextBox> control cambian, por un usuario o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e758a-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="e758a-114">**Nota:** Este evento desencadena cuando el <xref:System.Windows.Controls.TextBox> control se crea y se rellena inicialmente con el texto.</span><span class="sxs-lookup"><span data-stu-id="e758a-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="e758a-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e758a-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e758a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e758a-116">See also</span></span>
- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="e758a-117">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="e758a-117">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="e758a-118">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="e758a-118">[RichTextBox Overview](richtextbox-overview.md)</span></span>
