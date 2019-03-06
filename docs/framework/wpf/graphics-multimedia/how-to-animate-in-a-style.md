---
title: Cómo animar en un estilo (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 5fb18a2d927746c3437ec01d2a19327be373cae3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373964"
---
# <a name="how-to-animate-in-a-style"></a>Cómo animar en un estilo

En este ejemplo se muestra cómo animar propiedades dentro de un estilo. Al animar dentro de un estilo, se puede destinar solo el elemento de marco para el que está definido el estilo directamente. Para establecer el destino de un objeto freezable, debe "punto hacia abajo" de una propiedad del elemento de estilo.

En el ejemplo siguiente, se definen dentro de un estilo y se aplica a varias animaciones una <xref:System.Windows.Controls.Button>. Cuando el usuario mueve el mouse sobre el botón, se desvanece de opaco a parcialmente translúcido y viceversa, repetidamente. Cuando el usuario mueve el mouse fuera del botón, se vuelve completamente opaco. Cuando se hace clic en el botón, cambia su color de fondo de color naranja a blanco y viceversa. Dado que el <xref:System.Windows.Media.SolidColorBrush> se usa para pintar el botón no se puede establecer como destino directamente, se tiene acceso a estableciendo una relación en el botón <xref:System.Windows.Controls.Control.Background%2A> propiedad.

## <a name="example"></a>Ejemplo

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

Tenga en cuenta que al animar dentro de un estilo, es posible a los objetos de destino que no existen. Por ejemplo, suponga que usa el estilo de un <xref:System.Windows.Media.SolidColorBrush> se invalida establecer la propiedad de fondo de un botón, pero en algún momento el estilo y el fondo del botón se establece con un <xref:System.Windows.Media.LinearGradientBrush>.  Intentar animar el <xref:System.Windows.Media.SolidColorBrush> no arrojará una excepción; la animación simplemente se producirá un error en modo silencioso.

Para obtener más información acerca de guión gráfico como destino la sintaxis, vea el [Storyboards Overview](storyboards-overview.md). Para obtener más información acerca de la animación, vea el [información general sobre animaciones](animation-overview.md). Para obtener más información sobre los estilos, vea el [aplicar estilos y plantillas](../controls/styling-and-templating.md).
