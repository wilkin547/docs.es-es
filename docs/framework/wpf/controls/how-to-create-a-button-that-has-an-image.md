---
title: 'Cómo: Crear un botón que tenga una imagen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 9fb871aa39461329654c0289f00bd3080a633913
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Cómo: Crear un botón que tenga una imagen
Este ejemplo muestra cómo puede incluir una imagen en un <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea dos <xref:System.Windows.Controls.Button> controles. Una <xref:System.Windows.Controls.Button> contiene texto y el otro contiene una imagen. La imagen está en una carpeta denominada data, que es una subcarpeta de la carpeta del proyecto del ejemplo. Cuando un usuario hace clic en el <xref:System.Windows.Controls.Button> que tiene la imagen, el fondo y el texto de la otra <xref:System.Windows.Controls.Button> cambiar.  
  
 Este ejemplo se crea <xref:System.Windows.Controls.Button> controla mediante el uso de marcado, pero se usa código para escribir el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controladores de eventos.  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Vea también  
 [Controles](../../../../docs/framework/wpf/controls/index.md)  
 [Biblioteca de controles](../../../../docs/framework/wpf/controls/control-library.md)
