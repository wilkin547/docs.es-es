---
title: 'Cómo: Crear texto con contorno'
ms.date: 03/30/2017
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
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278930"
---
# <a name="how-to-create-outlined-text"></a>Cómo: Crear texto esbozado

En la mayoría de los casos, cuando se [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] agrega ornamentación a cadenas de texto en la aplicación, se utiliza texto en términos de una colección de caracteres discretos o pictogramas. Por ejemplo, podría crear un pincel de <xref:System.Windows.Controls.Control.Foreground%2A> degradado lineal <xref:System.Windows.Controls.TextBox> y aplicarlo a la propiedad de un objeto. Al mostrar o editar el cuadro de texto, el pincel de degradado lineal se aplica automáticamente al conjunto actual de caracteres de la cadena de texto.  
  
 ![Texto que se muestra con un pincel de degradado lineal](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 Sin embargo, también <xref:System.Windows.Media.Geometry> puede convertir texto en objetos, lo que le permite crear otros tipos de texto visualmente enriquecido. Por ejemplo, podría <xref:System.Windows.Media.Geometry> crear un objeto basado en el contorno de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 Cuando el texto <xref:System.Windows.Media.Geometry> se convierte en un objeto, ya no es una colección de caracteres: no se pueden modificar los caracteres de la cadena de texto. Sin embargo, puede afectar a la apariencia del texto convertido modificando sus propiedades de trazo y relleno. El trazo se refiere al contorno del texto convertido; el relleno es el área dentro del contorno del texto convertido.  
  
 Los siguientes ejemplos ilustran varias formas de crear efectos visuales modificando el trazo y el relleno del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Texto con pincel de imagen aplicado a trazo](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 También es posible modificar el rectángulo del cuadro delimitador, o resaltar, del texto convertido. En el ejemplo siguiente se muestra una forma de crear efectos visuales modificando el trazo y el resaltado del texto convertido.  
  
 ![Texto con pincel de imagen aplicado al trazo y resaltado](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>Ejemplo  
 La clave para convertir <xref:System.Windows.Media.Geometry> texto en un <xref:System.Windows.Media.FormattedText> objeto es utilizar el objeto. Una vez creado este objeto, <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> puede <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> utilizar los métodos y para convertir el texto en <xref:System.Windows.Media.Geometry> objetos. El primer método devuelve la geometría del texto con formato; el segundo método devuelve la geometría del cuadro delimitador del texto con formato. En el ejemplo de código <xref:System.Windows.Media.FormattedText> siguiente se muestra cómo crear un objeto y recuperar las geometrías del texto con formato y su cuadro delimitador.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Para mostrar los <xref:System.Windows.Media.Geometry> objetos recuperados, debe <xref:System.Windows.Media.DrawingContext> tener acceso al objeto que muestra el texto convertido. En estos ejemplos de código, este acceso se logra mediante la creación de un objeto de control personalizado que se deriva de una clase que admite la representación definida por el usuario.  
  
 Para <xref:System.Windows.Media.Geometry> mostrar objetos en el control <xref:System.Windows.UIElement.OnRender%2A> personalizado, proporcione una invalidación para el método. El método invalidado <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> debe usar <xref:System.Windows.Media.Geometry> el método para dibujar los objetos.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Para obtener el origen del objeto de control de usuario personalizado de ejemplo, vea [OutlineTextControl.cs para C-](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) y [OutlineTextControl.vb para Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).
  
## <a name="see-also"></a>Consulte también

- [Dibujar texto con formato](drawing-formatted-text.md)
