---
title: "Cómo: Enlazar datos a un InkCanvas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c8c4f558386edd8da213f8a8af75b6a4c6a98b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="0876d-102">Cómo: Enlazar datos a un InkCanvas</span><span class="sxs-lookup"><span data-stu-id="0876d-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="0876d-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0876d-103">Example</span></span>  
 <span data-ttu-id="0876d-104">En el ejemplo siguiente se muestra cómo enlazar la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedad de un <xref:System.Windows.Controls.InkCanvas> a otro <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="0876d-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="0876d-105">En el ejemplo siguiente se muestra cómo enlazar el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedad a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0876d-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="0876d-106">En el ejemplo siguiente se declara dos <xref:System.Windows.Controls.InkCanvas> objetos en XAML y establece el enlace de datos entre ellos y otros orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="0876d-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="0876d-107">La primera <xref:System.Windows.Controls.InkCanvas>, llamado `ic`, se enlaza a dos orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="0876d-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="0876d-108">El <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> y <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades `ic` están enlazados a <xref:System.Windows.Controls.ListBox> objetos, que a su vez se enlazan a las matrices definidas en el código XAML.</span><span class="sxs-lookup"><span data-stu-id="0876d-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="0876d-109">El <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, y <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedades del segundo <xref:System.Windows.Controls.InkCanvas> están enlazados al primer <xref:System.Windows.Controls.InkCanvas>, `ic`.</span><span class="sxs-lookup"><span data-stu-id="0876d-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
