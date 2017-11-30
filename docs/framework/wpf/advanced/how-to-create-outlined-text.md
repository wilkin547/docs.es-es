---
title: "Cómo: Crear texto con contorno"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76d0dcf63f9d8a66106f4bcdc52a2bf98c75cdc4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-outlined-text"></a>Cómo: Crear texto con contorno
En la mayoría de los casos, al agregar ornamentación a las cadenas de texto en su [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación, se utiliza el texto considerándolo una colección de caracteres discretos, o glifos. Por ejemplo, podría crear un pincel de degradado lineal y aplicarlo a la <xref:System.Windows.Controls.Control.Foreground%2A> propiedad de un <xref:System.Windows.Controls.TextBox> objeto. Al mostrar o editar el cuadro de texto, el pincel de degradado lineal se aplica automáticamente al conjunto actual de caracteres de la cadena de texto.  
  
 ![Texto mostrado con un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
Ejemplo de un pincel de degradado lineal que se aplica a un cuadro de texto  
  
 Sin embargo, también puede convertir texto en <xref:System.Windows.Media.Geometry> objetos, lo que le permite crear otros tipos de texto visualmente enriquecido. Por ejemplo, podría crear un <xref:System.Windows.Media.Geometry> objeto basado en el esquema de una cadena de texto.  
  
 ![Contorno al texto mediante un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Ejemplo de un pincel de degradado lineal que se aplica a la geometría del contorno del texto  
  
 Cuando el texto se convierte en un <xref:System.Windows.Media.Geometry> de objeto, ya no es una colección de caracteres, no se puede modificar los caracteres de la cadena de texto. Sin embargo, puede afectar a la apariencia del texto convertido modificando sus propiedades de trazo y relleno. El trazo se refiere al contorno del texto convertido; el relleno es el área dentro del contorno del texto convertido.  
  
 Los ejemplos siguientes ilustran varias maneras de crear efectos visuales modificando el trazo y el relleno del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Ejemplo de configuración de relleno y trazo en diferentes colores  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Ejemplo de pincel de imagen aplicado al trazo  
  
 También es posible modificar el rectángulo delimitador o el resaltado del texto convertido. En el ejemplo siguiente se muestra una manera de crear efectos visuales modificando el trazo y el resaltado del texto convertido.  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Ejemplo de pincel de imagen aplicado al trazo y el resaltado  
  
## <a name="example"></a>Ejemplo  
 La clave para convertir texto en una <xref:System.Windows.Media.Geometry> objeto consiste en usar la <xref:System.Windows.Media.FormattedText> objeto. Una vez que ha creado este objeto, puede usar el <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> y <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> métodos para convertir el texto en <xref:System.Windows.Media.Geometry> objetos. El primer método devuelve la geometría del texto con formato; el segundo método devuelve que la geometría del texto con formato del cuadro de límite. En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Media.FormattedText> objeto y recuperar las geometrías del texto con formato y su cuadro de límite.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Para mostrar el objeto recuperado el <xref:System.Windows.Media.Geometry> objetos, necesita tener acceso a la <xref:System.Windows.Media.DrawingContext> del objeto que se muestra el texto convertido. En estos ejemplos de código, esto se realiza mediante la creación de un objeto de control personalizado que se deriva de una clase que admite el procesamiento definido por el usuario.  
  
 Para mostrar <xref:System.Windows.Media.Geometry> objetos en el control personalizado, proporcione un nombre para invalidar el <xref:System.Windows.UIElement.OnRender%2A> método. Debe usar el método invalidado la <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> método para dibujar el <xref:System.Windows.Media.Geometry> objetos.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a>Vea también  
 [Dibujar texto con formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
