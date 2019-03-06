---
title: Filtrar Enlazar datos a un InkCanvas
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 5d3fc0ed7b6176d7bc68bf20af42c311b5563908
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372950"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="c7b46-102">Filtrar Enlazar datos a un InkCanvas</span><span class="sxs-lookup"><span data-stu-id="c7b46-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="c7b46-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7b46-103">Example</span></span>  
 <span data-ttu-id="c7b46-104">En el ejemplo siguiente se muestra cómo enlazar la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedad de un <xref:System.Windows.Controls.InkCanvas> a otro <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="c7b46-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="c7b46-105">En el ejemplo siguiente se muestra cómo enlazar la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedad a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c7b46-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="c7b46-106">En el ejemplo siguiente se declara dos <xref:System.Windows.Controls.InkCanvas> objetos en XAML y establece el enlace de datos entre ellos y otros orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="c7b46-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="c7b46-107">La primera <xref:System.Windows.Controls.InkCanvas>, llamado `ic`, está enlazado a dos orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="c7b46-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="c7b46-108">El <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> y <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades `ic` están enlazados a <xref:System.Windows.Controls.ListBox> objetos, que a su vez están enlazados a las matrices definidas en el XAML.</span><span class="sxs-lookup"><span data-stu-id="c7b46-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="c7b46-109">El <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, y <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedades del segundo <xref:System.Windows.Controls.InkCanvas> están enlazadas al primer <xref:System.Windows.Controls.InkCanvas>, `ic`.</span><span class="sxs-lookup"><span data-stu-id="c7b46-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
