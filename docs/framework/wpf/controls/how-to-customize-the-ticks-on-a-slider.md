---
title: 'Cómo: Personalizar las marcas de paso en un control Slider'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 667ec5d5504e18449800598f0b14548b7463bdf3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550883"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Cómo: Personalizar las marcas de paso en un control Slider
Este ejemplo muestra cómo crear un <xref:System.Windows.Controls.Slider> control que contiene las marcas de graduación.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.Primitives.TickBar> muestra cuando se establece la <xref:System.Windows.Controls.Slider.TickPlacement%2A> propiedad en un valor distinto de <xref:System.Windows.Controls.Primitives.TickPlacement.None>, que es el valor predeterminado.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> que muestra marcas de graduación. El <xref:System.Windows.Controls.Slider.TickPlacement%2A> y <xref:System.Windows.Controls.Slider.TickFrequency%2A> propiedades definen la ubicación de las marcas de graduación y el intervalo entre ellos. Al mover el <xref:System.Windows.Controls.Primitives.Thumb>, información sobre herramientas muestra el valor de la <xref:System.Windows.Controls.Slider>. El <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> propiedad define dónde se producen las informaciones sobre herramientas. El <xref:System.Windows.Controls.Primitives.Thumb> movimientos corresponden a la ubicación de las marcas de graduación porque <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> está establecido en `true`.  
  
 En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Controls.Slider.Ticks%2A> propiedad que se va a crear a lo largo de las marcas de graduación el <xref:System.Windows.Controls.Slider> a intervalos irregulares.  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [Temas de procedimientos sobre un control Slider](http://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
