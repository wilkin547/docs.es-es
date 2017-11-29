---
title: "Cómo: Animar en un estilo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10cd243c633e7a7e458d2026fc5e3d91d2996427
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-in-a-style"></a>Cómo: Animar en un estilo
En este ejemplo se muestra cómo animar propiedades dentro de un estilo. Al animar dentro de un estilo, se puede destinar solo el elemento de marco de trabajo para el que se define el estilo directamente. Que tenga como destino un objeto freezable, debe "establecer una relación" desde una propiedad del elemento de estilo.  
  
 En el ejemplo siguiente, se define dentro de un estilo varias animaciones y se aplican a un <xref:System.Windows.Controls.Button>. Cuando el usuario mueve el mouse sobre el botón, fundido de opaco a parcialmente translúcido y viceversa, repetidamente. Cuando el usuario mueve el mouse fuera del botón, se vuelve completamente opaco. Cuando se hace clic en el botón, su color de fondo cambia de color naranja en blanco y vuelva a hacer. Dado que la <xref:System.Windows.Media.SolidColorBrush> utilizado para pintar el botón no se puede establecer como destino directamente, se tiene acceso estableciendo una relación en el botón <xref:System.Windows.Controls.Control.Background%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Tenga en cuenta que al animar dentro de un estilo, es posible a los objetos de destino que no existen. Por ejemplo, supongamos que usa su estilo de un <xref:System.Windows.Media.SolidColorBrush> establecer la propiedad de fondo de un botón, pero en algún momento el estilo se invalida y se establece el fondo del botón con un <xref:System.Windows.Media.LinearGradientBrush>.  Si intenta animar el <xref:System.Windows.Media.SolidColorBrush> , no se iniciará una excepción; la animación simplemente se producirá un error en modo silencioso.  
  
 Para obtener más información acerca de la sintaxis de destino de guión gráfico, vea el [información general de guiones gráficos](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md). Para obtener más información acerca de la animación, consulte el [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Para obtener más información sobre los estilos, vea el [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).
