---
title: Filtrar Usar la clase FontSizeConverter
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: f33a297ae07d5509d2b4d9a98636086ac433a57f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088189"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="51fb7-102">Filtrar Usar la clase FontSizeConverter</span><span class="sxs-lookup"><span data-stu-id="51fb7-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="51fb7-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51fb7-103">Example</span></span>  
 <span data-ttu-id="51fb7-104">En este ejemplo se muestra cómo crear una instancia de <xref:System.Windows.FontSizeConverter> y usarlo para cambiar el tamaño de fuente.</span><span class="sxs-lookup"><span data-stu-id="51fb7-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="51fb7-105">El ejemplo define un método personalizado llamado `changeSize` que convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Double>y versiones posteriores en un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="51fb7-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="51fb7-106">Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.FontSizeConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="51fb7-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="51fb7-107">Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.TextBlock.FontSize%2A> propiedad de la <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="51fb7-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="51fb7-108">En este ejemplo también define un segundo método personalizado que se denomina `changeFamily`.</span><span class="sxs-lookup"><span data-stu-id="51fb7-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="51fb7-109">Este método convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de la <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.String>y, a continuación, pasa ese valor a la <xref:System.Windows.Controls.TextBlock.FontFamily%2A> propiedad de la <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="51fb7-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="51fb7-110">En este ejemplo no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="51fb7-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="51fb7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="51fb7-111">See also</span></span>

- <xref:System.Windows.FontSizeConverter>
