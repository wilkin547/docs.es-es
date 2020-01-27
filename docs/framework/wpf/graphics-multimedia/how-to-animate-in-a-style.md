---
title: Cómo animar en un estilo
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 0b29648bf15f0046adcdee610f9565f7deb24972
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744880"
---
# <a name="how-to-animate-in-a-style"></a>Cómo animar en un estilo

En este ejemplo se muestra cómo animar las propiedades dentro de un estilo. Al animar dentro de un estilo, solo se puede destinar directamente el elemento de marco para el que se define el estilo. Para establecer como destino un objeto Freezable, debe "punto inactivo" desde una propiedad del elemento con estilo.

En el ejemplo siguiente, se definen varias animaciones dentro de un estilo y se aplican a un <xref:System.Windows.Controls.Button>. Cuando el usuario mueve el mouse sobre el botón, lo atenúa de forma repetida y viceversa. Cuando el usuario mueve el mouse fuera del botón, se vuelve completamente opaco. Al hacer clic en el botón, el color de fondo cambia de naranja a blanco y viceversa. Dado que el <xref:System.Windows.Media.SolidColorBrush> que se usa para pintar el botón no se puede destinar directamente, se obtiene acceso a él mediante el uso de puntos hacia abajo desde la propiedad <xref:System.Windows.Controls.Control.Background%2A> del botón.

## <a name="example"></a>Ejemplo

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

Tenga en cuenta que al animar dentro de un estilo, es posible tener como destino objetos que no existen. Por ejemplo, suponga que el estilo usa un <xref:System.Windows.Media.SolidColorBrush> para establecer la propiedad de fondo de un botón, pero en algún momento se invalida el estilo y el fondo del botón se establece con un <xref:System.Windows.Media.LinearGradientBrush>.  Al intentar animar el <xref:System.Windows.Media.SolidColorBrush> no se producirá una excepción; la animación simplemente producirá un error de forma silenciosa.

Para obtener más información sobre la sintaxis de destino de guion gráfico, vea la [información general sobre los guiones gráficos](storyboards-overview.md). Para obtener más información acerca de la animación, consulte [información general sobre animaciones](animation-overview.md). Para obtener más información sobre los estilos, vea el [estilo y la plantilla](../../../desktop-wpf/fundamentals/styles-templates-overview.md).
