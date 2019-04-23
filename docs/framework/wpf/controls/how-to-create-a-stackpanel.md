---
title: Procedimiento Crear un StackPanel
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121815"
---
# <a name="how-to-create-a-stackpanel"></a>Procedimiento Crear un StackPanel
En este ejemplo se muestra cómo crear un <xref:System.Windows.Controls.StackPanel>.  
  
## <a name="example"></a>Ejemplo  
 Un <xref:System.Windows.Controls.StackPanel> permite apilar elementos en una dirección especificada. Mediante las propiedades que se definen en <xref:System.Windows.Controls.StackPanel>, el contenido puede fluir verticalmente, que es el valor predeterminado, horizontal o verticalmente.  
  
 El ejemplo siguiente apila verticalmente cinco <xref:System.Windows.Controls.TextBlock> controla cada uno con otro <xref:System.Windows.Controls.Border> y <xref:System.Windows.Controls.Border.Background%2A>, mediante el uso de <xref:System.Windows.Controls.StackPanel>. Los elementos secundarios que tienen no se especifica <xref:System.Windows.FrameworkElement.Width%2A> se ajustan para rellenar la ventana primaria; sin embargo, los elementos secundarios que tienen un determinado <xref:System.Windows.FrameworkElement.Width%2A>, se centran en la ventana.  
  
 La dirección de la pila predeterminada en un <xref:System.Windows.Controls.StackPanel> es vertical. Para controlar el flujo de contenido en un <xref:System.Windows.Controls.StackPanel>, utilice el <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad. Puede controlar la alineación horizontal mediante el uso de la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.StackPanel>
- [Información general sobre elementos Panel](panels-overview.md)
- [Temas "Cómo..."](stackpanel-how-to-topics.md)
