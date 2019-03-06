---
title: Filtrar Usar colores del sistema en un degradado
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 3148a5901ccf64194717e26664ab8b9cbd57db2a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365963"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>Filtrar Usar colores del sistema en un degradado
Para utilizar un color del sistema en un degradado, se utiliza el  *\<SystemColor >* Color y  *\<SystemColor >* ColorKey propiedades estáticas de la <xref:System.Windows.SystemColors> clase para obtener una referencia al color, donde  *\<SystemColor >* es el nombre del color del sistema deseado. Use la  *\<SystemColor >* propiedades de ColorKey cuando desee crear una referencia dinámica que se actualiza automáticamente a medida que cambia el tema del sistema. En caso contrario, use el  *\<SystemColor >* propiedades de Color.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se usan recursos de color del sistema dinámico para crear un degradado.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 En el siguiente ejemplo se usan recursos de color del sistema estático para crear un degradado.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.SystemColors>
- [Pintar un área con un pincel del sistema](how-to-paint-an-area-with-a-system-brush.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
