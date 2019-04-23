---
title: Procedimiento Cambiar el tipo de cursor
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 5c9e6931f6addb62a51e44b06a159d4e7b1e5f8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141211"
---
# <a name="how-to-change-the-cursor-type"></a>Procedimiento Cambiar el tipo de cursor
En este ejemplo se muestra cómo cambiar el <xref:System.Windows.Input.Cursor> del puntero del mouse para un elemento específico y para la aplicación.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
## <a name="example"></a>Ejemplo  
 Se crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.ComboBox> para seleccionar la deseada <xref:System.Windows.Input.Cursor>, un par de <xref:System.Windows.Controls.RadioButton> objetos para determinar si el cambio del cursor se aplica a un solo elemento o se aplica a toda la aplicación y un <xref:System.Windows.Controls.Border> que es el elemento que se aplica el nuevo cursor.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Crea el código siguiente detrás de un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> controlador de eventos que se llama cuando se cambia el tipo de cursor en el <xref:System.Windows.Controls.ComboBox>.  Una instrucción switch se filtra según el nombre del cursor y establece el <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad en el <xref:System.Windows.Controls.Border> que se denomina *DisplayArea*.  
  
 Si el cambio del cursor se establece en "Toda aplicación", la <xref:System.Windows.Input.Mouse.OverrideCursor%2A> propiedad está establecida en el <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad de la <xref:System.Windows.Controls.Border> control.  Esto exige que el cursor a cambiar para toda la aplicación.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
