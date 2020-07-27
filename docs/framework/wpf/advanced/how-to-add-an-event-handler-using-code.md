---
title: 'Cómo: Agregar un controlador de eventos mediante código'
description: Use este ejemplo para aprender a agregar un controlador de eventos a un elemento en Windows Presentation Foundation mediante el uso de código, en lugar de declararlo mediante XAML.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: b36969f7a65ccbf6c9d03b22767d9eacdc177ad1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166364"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Cómo: Agregar un controlador de eventos mediante código
En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.  
  
 Si desea agregar un controlador de eventos a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento y la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código. Como alternativa, si va a crear el árbol de elementos para una aplicación que utiliza el código completamente y no declara ningún elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , puede llamar a métodos específicos para agregar controladores de eventos al árbol de elementos construido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agrega un nuevo <xref:System.Windows.Controls.Button> a una página existente que se define inicialmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo controlador de eventos en <xref:System.Windows.Controls.Button> .  
  
 En el ejemplo de C# `+=` se usa el operador para asignar un controlador a un evento. Es el mismo operador que se utiliza para asignar un controlador en el modelo de control de eventos de Common Language Runtime (CLR). Microsoft Visual Basic no admite este operador como medio para agregar controladores de eventos. En su lugar, requiere una de estas dos técnicas:  
  
- Use el <xref:System.Windows.UIElement.AddHandler%2A> método, junto con un `AddressOf` operador, para hacer referencia a la implementación del controlador de eventos.  
  
- Use la `Handles` palabra clave como parte de la definición del controlador de eventos. Esta técnica no se muestra aquí. vea [control de eventos de Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> Agregar un controlador de eventos en la página analizada inicialmente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es mucho más sencillo. En el elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar. A continuación, especifique el valor de ese atributo como el nombre del método de control de eventos que definió en el archivo de código subyacente de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página. Para obtener más información, vea información general sobre [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) o [información general sobre eventos enrutados](routed-events-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Temas "Cómo..."](events-how-to-topics.md)
