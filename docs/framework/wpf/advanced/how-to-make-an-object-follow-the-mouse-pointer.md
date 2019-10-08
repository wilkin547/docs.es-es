---
title: Procedimiento Crear un objeto que siga el puntero del mouse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005069"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Procedimiento Crear un objeto que siga el puntero del mouse
Este ejemplo muestra cómo cambiar las dimensiones de un objeto cuando el puntero del mouse se mueve en la pantalla.  
  
 En el ejemplo se incluye un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y un archivo de código subyacente que crea el controlador de eventos.  
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente crea el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], que consta de un <xref:System.Windows.Shapes.Ellipse> dentro de un <xref:System.Windows.Controls.StackPanel> y asocia el controlador de eventos para el evento <xref:System.Windows.UIElement.MouseMove>.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 El siguiente código subyacente crea el controlador de eventos <xref:System.Windows.UIElement.MouseMove>.  Cuando se mueve el puntero del mouse, el alto y el ancho del <xref:System.Windows.Shapes.Ellipse> aumentan y disminuyen.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
