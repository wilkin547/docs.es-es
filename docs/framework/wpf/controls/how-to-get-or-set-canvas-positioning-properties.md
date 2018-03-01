---
title: "Cómo: Obtener o establecer propiedades de situación de Canvas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2b01657088c388ad09037716278dc0788de2abb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="2c2e4-102">Cómo: Obtener o establecer propiedades de situación de Canvas</span><span class="sxs-lookup"><span data-stu-id="2c2e4-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="2c2e4-103">Este ejemplo muestra cómo utilizar los métodos de colocación de la <xref:System.Windows.Controls.Canvas> elemento que se va a colocar el contenido secundario.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="2c2e4-104">Este ejemplo utiliza el contenido de un <xref:System.Windows.Controls.ListBoxItem> para representar valores de posición y convierte los valores a las instancias de <xref:System.Double>, que es un argumento necesario para determinar la posición.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="2c2e4-105">Los valores, a continuación, se convierten en cadenas y se muestran como texto en un <xref:System.Windows.Controls.TextBlock> elemento mediante la <xref:System.Windows.Controls.Canvas.GetLeft%2A> método.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c2e4-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c2e4-106">Example</span></span>  
 <span data-ttu-id="2c2e4-107">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> elemento que tiene once seleccionable <xref:System.Windows.Controls.ListBoxItem> elementos.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="2c2e4-108">El <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> desencadenadores de eventos el `ChangeLeft` método personalizado, que define el bloque de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="2c2e4-109">Cada <xref:System.Windows.Controls.ListBoxItem> representa un <xref:System.Double> valor, que es uno de los argumentos que el <xref:System.Windows.Controls.Canvas.SetLeft%2A> método <xref:System.Windows.Controls.Canvas> acepta.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="2c2e4-110">Para poder usar un <xref:System.Windows.Controls.ListBoxItem> para representar una instancia de <xref:System.Double>, primero debe convertir el <xref:System.Windows.Controls.ListBoxItem> para el tipo de datos correcto.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="2c2e4-111">Cuando un usuario cambia el <xref:System.Windows.Controls.ListBox> selección, invoca el `ChangeLeft` método personalizado.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="2c2e4-112">Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.Windows.LengthConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Double> (tenga en cuenta que este valor ya se ha convertido en un <xref:System.String> mediante el uso de la <xref:System.Windows.Controls.Control.ToString%2A> método).</span><span class="sxs-lookup"><span data-stu-id="2c2e4-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="2c2e4-113">Este valor, a continuación, se ha pasado a la <xref:System.Windows.Controls.Canvas.SetLeft%2A> y <xref:System.Windows.Controls.Canvas.GetLeft%2A> métodos de <xref:System.Windows.Controls.Canvas> con el fin de cambiar la posición de la `text1` objeto.</span><span class="sxs-lookup"><span data-stu-id="2c2e4-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2c2e4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c2e4-114">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [<span data-ttu-id="2c2e4-115">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="2c2e4-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
