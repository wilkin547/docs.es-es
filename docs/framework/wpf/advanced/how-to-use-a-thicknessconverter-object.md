---
title: 'Cómo: Utilizar un objeto ThicknessConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 119c4397dee76429e776378ee89fa49747dbfce4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544348"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="0d811-102">Cómo: Utilizar un objeto ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="0d811-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="0d811-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d811-103">Example</span></span>  
 <span data-ttu-id="0d811-104">Este ejemplo muestra cómo crear una instancia de <xref:System.Windows.ThicknessConverter> y usarlo para cambiar el grosor de un borde.</span><span class="sxs-lookup"><span data-stu-id="0d811-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="0d811-105">En el ejemplo se define un método personalizado denominado `changeThickness`; en primer lugar, este método convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Windows.Thickness>y más adelante convierte el contenido en un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="0d811-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="0d811-106">Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.Windows.ThicknessConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="0d811-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="0d811-107">Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.Border.BorderThickness%2A> propiedad de la <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="0d811-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="0d811-108">En este ejemplo no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0d811-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0d811-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d811-109">See Also</span></span>  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [<span data-ttu-id="0d811-110">Cómo: cambiar la propiedad Margin</span><span class="sxs-lookup"><span data-stu-id="0d811-110">How to: Change the Margin Property</span></span>](http://msdn.microsoft.com/library/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [<span data-ttu-id="0d811-111">Cómo: convertir un elemento ListBoxItem en un nuevo tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0d811-111">How to: Convert a ListBoxItem to a new Data Type</span></span>](http://msdn.microsoft.com/library/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [<span data-ttu-id="0d811-112">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="0d811-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
