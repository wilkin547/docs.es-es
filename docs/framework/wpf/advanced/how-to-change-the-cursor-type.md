---
title: 'Cómo: Cambiar el tipo de cursor'
description: Cambiar el cursor del puntero del mouse para un elemento y para una aplicación en Windows Presentation Foundation. Este ejemplo consta de XAML y un archivo de código subyacente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165962"
---
# <a name="how-to-change-the-cursor-type"></a>Cómo: Cambiar el tipo de cursor
En este ejemplo se muestra cómo cambiar el <xref:System.Windows.Input.Cursor> del puntero del mouse para un elemento específico y para la aplicación.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
## <a name="example"></a>Ejemplo  
 Se crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.ComboBox> para seleccionar el <xref:System.Windows.Input.Cursor> objeto deseado, un par de <xref:System.Windows.Controls.RadioButton> objetos para determinar si el cambio de cursor se aplica solo a un único elemento o se aplica a toda la aplicación, y, <xref:System.Windows.Controls.Border> que es el elemento al que se aplica el nuevo cursor.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 En el código subyacente siguiente se crea un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> controlador de eventos al que se llama cuando se cambia el tipo de cursor en <xref:System.Windows.Controls.ComboBox> .  Una instrucción switch filtra por el nombre del cursor y establece la <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad en <xref:System.Windows.Controls.Border> que se denomina *DisplayArea*.  
  
 Si el cambio del cursor se establece en "toda la aplicación", la <xref:System.Windows.Input.Mouse.OverrideCursor%2A> propiedad se establece en la <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad del <xref:System.Windows.Controls.Border> control.  Esto obliga al cursor a cambiar para toda la aplicación.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
