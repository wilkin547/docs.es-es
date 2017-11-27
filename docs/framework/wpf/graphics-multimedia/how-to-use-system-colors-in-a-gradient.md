---
title: "Cómo: Usar colores del sistema en un degradado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 105e22588f68d999811f5482342d53851a4d25eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>Cómo: Usar colores del sistema en un degradado
Para utilizar un color del sistema en un degradado, se utiliza el  *\<SystemColor >*Color y  *\<SystemColor >*ColorKey propiedades estáticas de la <xref:System.Windows.SystemColors> clase para obtener una referencia al color, donde  *\<SystemColor >* es el nombre del color del sistema deseado. Use la  *\<SystemColor >*ColorKey propiedades cuando desea crear una referencia dinámica que se actualiza automáticamente a medida que los cambios de tema del sistema. De lo contrario, utilice la  *\<SystemColor >*propiedades de Color.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se usan recursos de color del sistema dinámico para crear un degradado.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 En el siguiente ejemplo se usan recursos de color del sistema estático para crear un degradado.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.SystemColors>  
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
