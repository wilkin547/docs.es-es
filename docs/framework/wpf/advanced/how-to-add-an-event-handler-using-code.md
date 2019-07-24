---
title: Procedimiento Agregar un controlador de eventos mediante código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 00b12d9dc25e0704eb73d8bc727ae6647493f494
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401171"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Procedimiento Agregar un controlador de eventos mediante código
En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.  
  
 Si desea agregar un controlador de eventos a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento y la página de marcado que contiene el elemento ya se ha cargado, debe agregar el controlador mediante código. Como alternativa, si va a crear el árbol de elementos para una aplicación que utiliza el código completamente y no declara ningún elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]mediante, puede llamar a métodos específicos para agregar controladores de eventos al árbol de elementos construido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agrega <xref:System.Windows.Controls.Button> un nuevo a una página existente que se define [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]inicialmente en. Un archivo de código subyacente implementa un método de controlador de eventos y, a continuación, agrega ese método como un nuevo <xref:System.Windows.Controls.Button>controlador de eventos en.  
  
 En C# el ejemplo se `+=` usa el operador para asignar un controlador a un evento. Es el mismo operador que se utiliza para asignar un controlador en el modelo de control de eventos de Common Language Runtime (CLR). Microsoft Visual Basic no admite este operador como medio para agregar controladores de eventos. En su lugar, requiere una de estas dos técnicas:  
  
- Use el <xref:System.Windows.UIElement.AddHandler%2A> método, junto con un `AddressOf` operador, para hacer referencia a la implementación del controlador de eventos.  
  
- Use la `Handles` palabra clave como parte de la definición del controlador de eventos. Esta técnica no se muestra aquí. vea [control de eventos de Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Agregar un controlador de eventos en la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página analizada inicialmente es mucho más sencillo. En el elemento de objeto en el que desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar. A continuación, especifique el valor de ese atributo como el nombre del método de control de eventos que definió en el archivo de código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] subyacente de la página. Para obtener más información, vea información general sobre [XAML (WPF)](xaml-overview-wpf.md) o [información general sobre eventos](routed-events-overview.md)enrutados.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Temas "Cómo..."](events-how-to-topics.md)
