---
title: 'Cómo: Agregar un controlador de eventos mediante código'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460433"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Cómo: Agregar un controlador de eventos mediante código
En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.  
  
 Si desea agregar un controlador de eventos a un elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código. Como alternativa, si va a crear el árbol de elementos para una aplicación que usa el código completamente y no declara ningún elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede llamar a métodos específicos para agregar controladores de eventos al árbol de elementos construido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agrega un nuevo <xref:System.Windows.Controls.Button> a una página existente que se define inicialmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo controlador de eventos en el <xref:System.Windows.Controls.Button>.  
  
 En C# el ejemplo se usa el operador `+=` para asignar un controlador a un evento. Es el mismo operador que se utiliza para asignar un controlador en el modelo de control de eventos de Common Language Runtime (CLR). Microsoft Visual Basic no admite este operador como medio para agregar controladores de eventos. En su lugar, requiere una de estas dos técnicas:  
  
- Utilice el método <xref:System.Windows.UIElement.AddHandler%2A>, junto con un operador `AddressOf`, para hacer referencia a la implementación del controlador de eventos.  
  
- Use la palabra clave `Handles` como parte de la definición del controlador de eventos. Esta técnica no se muestra aquí. vea [control de eventos de Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> Agregar un controlador de eventos en la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] analizada inicialmente es mucho más sencillo. En el elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar. A continuación, especifique el valor de ese atributo como el nombre del método de control de eventos que definió en el archivo de código subyacente de la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Para obtener más información, vea información general sobre [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) o [información general sobre eventos enrutados](routed-events-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Temas "Cómo..."](events-how-to-topics.md)
