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
ms.openlocfilehash: b9b13b4eec3e42744ba2be6031ec841fb5f215e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051603"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Procedimiento Crear un objeto que siga el puntero del mouse
En este ejemplo se muestra cómo cambiar las dimensiones de un objeto cuando el puntero del mouse se mueve en la pantalla.  
  
 El ejemplo incluye un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo que crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y un archivo de código subyacente que crea el controlador de eventos.  
  
## <a name="example"></a>Ejemplo  
 La siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], que consta de un <xref:System.Windows.Shapes.Ellipse> dentro de un <xref:System.Windows.Controls.StackPanel>y asocia el controlador de eventos para el <xref:System.Windows.UIElement.MouseMove> eventos.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 El código subyacente siguiente crea el <xref:System.Windows.UIElement.MouseMove> controlador de eventos.  Cuando mueve el puntero del mouse, el alto y el ancho de la <xref:System.Windows.Shapes.Ellipse> son incrementado y reducido.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
