---
title: Filtrar Agregar un controlador de eventos mediante código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 05eaae0f5b893f42d421717ac73373d4c79004c4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352196"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Filtrar Agregar un controlador de eventos mediante código
En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.  
  
 Si desea agregar un controlador de eventos para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento y la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código. Como alternativa, si va a crear el árbol de elementos de una aplicación totalmente mediante código y no declara ningún elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede llamar a métodos específicos para agregar controladores de eventos en el árbol de elementos construido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agrega un nuevo <xref:System.Windows.Controls.Button> a una página existente que se define inicialmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo controlador de eventos en el <xref:System.Windows.Controls.Button>.  
  
 El C# en el ejemplo se usa el `+=` operador para asignar un controlador a un evento. Este es el mismo operador que se utiliza para asignar un controlador en el [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] modelo de control de eventos. Microsoft Visual Basic no admite este operador como un medio para agregar controladores de eventos. En su lugar, requiere una de estas dos técnicas:  
  
-   Use la <xref:System.Windows.UIElement.AddHandler%2A> método, junto con un `AddressOf` operador, para hacer referencia a la implementación del controlador de eventos.  
  
-   Use el `Handles` palabra clave como parte de la definición de controlador de eventos. Esta técnica no se muestra aquí; consulte [Visual Basic y control de eventos de WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Agregar un controlador de eventos en el objeto analizado inicialmente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página es mucho más sencilla. Dentro del elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar. A continuación, especifique el valor de ese atributo como el nombre del método de controlador de eventos que ha definido en el archivo de código subyacente de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página. Para obtener más información, consulte [información general sobre XAML (WPF)](xaml-overview-wpf.md) o [Routed Events Overview](routed-events-overview.md).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Temas "Cómo..."](events-how-to-topics.md)
