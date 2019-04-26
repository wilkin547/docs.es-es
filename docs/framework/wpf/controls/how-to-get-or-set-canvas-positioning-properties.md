---
title: Procedimiento Obtener o establecer propiedades de situación de Canvas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910486"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="9476f-102">Procedimiento Obtener o establecer propiedades de situación de Canvas</span><span class="sxs-lookup"><span data-stu-id="9476f-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="9476f-103">En este ejemplo se muestra cómo usar los métodos de posición el <xref:System.Windows.Controls.Canvas> elemento que se va a colocar el contenido secundario.</span><span class="sxs-lookup"><span data-stu-id="9476f-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="9476f-104">Este ejemplo usa el contenido de un <xref:System.Windows.Controls.ListBoxItem> para representar valores de posición y convierte los valores en las instancias de <xref:System.Double>, que es un argumento necesario para el posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="9476f-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="9476f-105">Los valores, a continuación, se convierten en cadenas y se muestran como texto en un <xref:System.Windows.Controls.TextBlock> elemento utilizando el <xref:System.Windows.Controls.Canvas.GetLeft%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9476f-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9476f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9476f-106">Example</span></span>  
 <span data-ttu-id="9476f-107">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> elemento que tiene once seleccionable <xref:System.Windows.Controls.ListBoxItem> elementos.</span><span class="sxs-lookup"><span data-stu-id="9476f-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="9476f-108">El <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> desencadenadores de eventos el `ChangeLeft` método personalizado, que define el bloque de código subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="9476f-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="9476f-109">Cada <xref:System.Windows.Controls.ListBoxItem> representa un <xref:System.Double> valor, que es uno de los argumentos que el <xref:System.Windows.Controls.Canvas.SetLeft%2A> método <xref:System.Windows.Controls.Canvas> acepta.</span><span class="sxs-lookup"><span data-stu-id="9476f-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="9476f-110">Para poder usar un <xref:System.Windows.Controls.ListBoxItem> para representar una instancia de <xref:System.Double>, primero debe convertir el <xref:System.Windows.Controls.ListBoxItem> al tipo de datos correcto.</span><span class="sxs-lookup"><span data-stu-id="9476f-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="9476f-111">Cuando un usuario cambia el <xref:System.Windows.Controls.ListBox> selección, invoca el `ChangeLeft` método personalizado.</span><span class="sxs-lookup"><span data-stu-id="9476f-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="9476f-112">Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.LengthConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Double> (tenga en cuenta que este valor ya se ha convertido en un <xref:System.String> utilizando el <xref:System.Windows.Controls.Control.ToString%2A> método).</span><span class="sxs-lookup"><span data-stu-id="9476f-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="9476f-113">Este valor se pasa a continuación, volver a la <xref:System.Windows.Controls.Canvas.SetLeft%2A> y <xref:System.Windows.Controls.Canvas.GetLeft%2A> métodos de <xref:System.Windows.Controls.Canvas> con el fin de cambiar la posición de la `text1` objeto.</span><span class="sxs-lookup"><span data-stu-id="9476f-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9476f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9476f-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="9476f-115">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="9476f-115">Panels Overview</span></span>](panels-overview.md)
