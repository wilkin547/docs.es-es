---
title: Filtrar Pintar un área con un pincel del sistema
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 7beaf4370f115a3995c9ca23bb0022bd5b269193
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364117"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>Filtrar Pintar un área con un pincel del sistema
El <xref:System.Windows.SystemColors> clase proporciona acceso a los pinceles del sistema y los colores, como <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, y <xref:System.Windows.SystemColors.DesktopBrush%2A>. Un pincel del sistema es un <xref:System.Windows.Media.SolidColorBrush> objeto que pinta un área con el color del sistema especificado. Un pincel del sistema siempre produce un relleno sólido; no puede usarse para crear un degradado.  
  
 Puede utilizar los pinceles del sistema como un recurso estático o dinámico. Utilice un recurso dinámico si desea que el pincel se actualice automáticamente si el usuario cambia el pincel del sistema mientras se ejecuta la aplicación; de lo contrario, utilice un recurso estático. La clase SystemColors contiene varias propiedades estáticas que siguen una convención de nomenclatura estricta:  
  
-   *\<SystemColor>* Brush  
  
     Obtiene una referencia estática a un <xref:System.Windows.Media.SolidColorBrush> del color del sistema especificado.  
  
-   *\<SystemColor>* BrushKey  
  
     Obtiene una referencia dinámica a un <xref:System.Windows.Media.SolidColorBrush> del color del sistema especificado.  
  
-   *\<SystemColor>* Color  
  
     Obtiene una referencia estática a una <xref:System.Windows.Media.Color> estructura de color del sistema especificado.  
  
-   *\<SystemColor>* ColorKey  
  
     Obtiene una referencia dinámica a la <xref:System.Windows.Media.Color> estructura de color del sistema especificado.  
  
 Un color del sistema es un <xref:System.Windows.Media.Color> estructura que se puede usar para configurar un pincel. Por ejemplo, puede crear un degradado con los colores del sistema estableciendo el <xref:System.Windows.Media.GradientStop.Color%2A> las propiedades de un <xref:System.Windows.Media.LinearGradientBrush> delimitadores de degradado del objeto con los colores del sistema. Para obtener un ejemplo, vea [usar colores del sistema en un degradado](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza una referencia dinámica de pincel del sistema para establecer el fondo de un botón.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 En el ejemplo siguiente se utiliza una referencia estática de pincel del sistema para establecer el fondo de un botón.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Para obtener un ejemplo que muestra cómo utilizar un color del sistema en un degradado, vea [usar colores del sistema en un degradado](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="see-also"></a>Vea también
- [Usar colores del sistema en un degradado](how-to-use-system-colors-in-a-gradient.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
