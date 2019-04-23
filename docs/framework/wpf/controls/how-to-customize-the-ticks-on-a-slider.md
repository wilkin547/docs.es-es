---
title: Procedimiento Personalizar las marcas de paso en un control Slider
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 3b32bbedb5f654ce75e90a827eb0c4dba1d4d345
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164247"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Procedimiento Personalizar las marcas de paso en un control Slider
En este ejemplo se muestra cómo crear un <xref:System.Windows.Controls.Slider> control que contiene las marcas de graduación.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.Primitives.TickBar> muestra cuando se establece la <xref:System.Windows.Controls.Slider.TickPlacement%2A> propiedad a un valor distinto de <xref:System.Windows.Controls.Primitives.TickPlacement.None>, que es el valor predeterminado.  
  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> que muestra marcas de graduación. El <xref:System.Windows.Controls.Slider.TickPlacement%2A> y <xref:System.Windows.Controls.Slider.TickFrequency%2A> propiedades definen la ubicación de las marcas de graduación y el intervalo entre ellos. Al mover el <xref:System.Windows.Controls.Primitives.Thumb>, información sobre herramientas muestra el valor de la <xref:System.Windows.Controls.Slider>. El <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> propiedad define dónde se producen las informaciones sobre herramientas. El <xref:System.Windows.Controls.Primitives.Thumb> movimientos corresponden a la ubicación de las marcas de graduación porque <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> está establecido en `true`.  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.Slider.Ticks%2A> propiedad que se va a crear a lo largo de las marcas de graduación el <xref:System.Windows.Controls.Slider> a intervalos irregulares.  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [Cómo: Enlazar un control deslizante con un valor de propiedad](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
