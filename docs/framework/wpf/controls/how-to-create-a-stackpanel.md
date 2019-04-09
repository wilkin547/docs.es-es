---
title: Filtrar Crear un StackPanel
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121815"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="e510e-102">Filtrar Crear un StackPanel</span><span class="sxs-lookup"><span data-stu-id="e510e-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="e510e-103">En este ejemplo se muestra cómo crear un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="e510e-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e510e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e510e-104">Example</span></span>  
 <span data-ttu-id="e510e-105">Un <xref:System.Windows.Controls.StackPanel> permite apilar elementos en una dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="e510e-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="e510e-106">Mediante las propiedades que se definen en <xref:System.Windows.Controls.StackPanel>, el contenido puede fluir verticalmente, que es el valor predeterminado, horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="e510e-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="e510e-107">El ejemplo siguiente apila verticalmente cinco <xref:System.Windows.Controls.TextBlock> controla cada uno con otro <xref:System.Windows.Controls.Border> y <xref:System.Windows.Controls.Border.Background%2A>, mediante el uso de <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="e510e-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="e510e-108">Los elementos secundarios que tienen no se especifica <xref:System.Windows.FrameworkElement.Width%2A> se ajustan para rellenar la ventana primaria; sin embargo, los elementos secundarios que tienen un determinado <xref:System.Windows.FrameworkElement.Width%2A>, se centran en la ventana.</span><span class="sxs-lookup"><span data-stu-id="e510e-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="e510e-109">La dirección de la pila predeterminada en un <xref:System.Windows.Controls.StackPanel> es vertical.</span><span class="sxs-lookup"><span data-stu-id="e510e-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="e510e-110">Para controlar el flujo de contenido en un <xref:System.Windows.Controls.StackPanel>, utilice el <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e510e-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="e510e-111">Puede controlar la alineación horizontal mediante el uso de la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e510e-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e510e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e510e-112">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="e510e-113">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="e510e-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e510e-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e510e-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
