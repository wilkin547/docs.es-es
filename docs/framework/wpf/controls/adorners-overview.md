---
title: Información general sobre adornos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111184"
---
# <a name="adorners-overview"></a>Información general sobre adornos

Los adornos son <xref:System.Windows.FrameworkElement>un tipo especial de , que se utiliza para proporcionar señales visuales a un usuario. Entre otros usos, los Adorners se pueden utilizar para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.

## <a name="about-adorners"></a>Acerca de Adorners

Un <xref:System.Windows.Documents.Adorner> es <xref:System.Windows.FrameworkElement> una costumbre que <xref:System.Windows.UIElement>está enlazada a un archivo . Los adornos se <xref:System.Windows.Documents.AdornerLayer>representan en un , que es una superficie de representación que siempre está encima del elemento adornado o una colección de elementos adornados. La representación de un adorno <xref:System.Windows.UIElement> es independiente de la representación de la que está enlazado el adorno. Normalmente, un adorno se coloca en relación con el elemento al que está enlazado, utilizando el origen de coordenadas 2D estándar situado en la parte superior izquierda del elemento adornado.

Algunas aplicaciones comunes de adornos son:

- Agregar identificadores <xref:System.Windows.UIElement> funcionales a un que permiten a un usuario manipular el elemento de alguna manera (cambiar el tamaño, rotar, cambiar la posición, etc.).
- Proporcionar comentarios visuales para indicar diversos estados, o en respuesta a distintos eventos.
- Superponer decoraciones <xref:System.Windows.UIElement>visuales en un archivo .
- Enmascarar visualmente o reemplazar parte <xref:System.Windows.UIElement>o la totalidad de un archivo .

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un marco básico para adornar elementos visuales. En la tabla siguiente se muestra una lista de los tipos principales utilizados al adornar objetos y su finalidad. A continuación se muestran varios ejemplos de uso:

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Una clase base abstracta de la que heredan todas las implementaciones de adornos contextuales concretas.|
|<xref:System.Windows.Documents.AdornerLayer>|Una clase que representa una capa de representación para los adornos de uno o más elementos adornados.|
|<xref:System.Windows.Documents.AdornerDecorator>|Una clase que permite asociar una capa de adornos a una colección de elementos.|

## <a name="implementing-a-custom-adorner"></a>Implementación de un adorno personalizado

El marco de adornos que proporciona [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado principalmente para admitir la creación de adornos personalizados. Un adorno personalizado se crea mediante la implementación de una clase que hereda de la clase abstracta. <xref:System.Windows.Documents.Adorner>

> [!NOTE]
> El elemento <xref:System.Windows.Documents.Adorner> primario <xref:System.Windows.Documents.AdornerLayer> de un <xref:System.Windows.Documents.Adorner>es el que representa el , no el elemento que se está adornando.

En el ejemplo siguiente se muestra una clase que implementa un adorno simple. El adorno de ejemplo simplemente <xref:System.Windows.UIElement> adorna las esquinas de un con círculos.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
La siguiente imagen muestra el SimpleCircleAdorner aplicado a un <xref:System.Windows.Controls.TextBox>:

![Captura de pantalla que muestra un cuadro de texto adornado.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Comportamiento de representación de los adornos

Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno. Una forma común de implementar el <xref:System.Windows.UIElement.OnRender%2A> comportamiento de representación es invalidar el método y usar uno o varios <xref:System.Windows.Media.DrawingContext> objetos para representar los objetos visuales del adorno según sea necesario (como se muestra en el ejemplo anterior).

> [!NOTE]
> Todo aquello que se coloca en la capa de los adornos se representa encima del resto de estilos que se han establecido. En otras palabras, los adornos siempre están visualmente encima y no pueden invalidar utilizando el orden z.

## <a name="events-and-hit-testing"></a>Eventos y pruebas de posicionamiento

Los adornos reciben eventos <xref:System.Windows.FrameworkElement>de entrada como cualquier otro .  Dado que un adorno siempre tiene un orden z más alto que el elemento <xref:System.Windows.UIElement.Drop> <xref:System.Windows.UIElement.MouseMove>que adorna, el adorno recibe eventos de entrada (como o ) que pueden estar pensados para el elemento adornado subyacente.  Un adorno puede realizar escuchas para ciertos eventos de entrada y pasárselos al elemento adornado subyacente volviendo a provocar el evento.

Para habilitar la prueba de posicionación de paso a <xref:System.Windows.UIElement.IsHitTestVisible%2A> través de elementos debajo de un adorno, establezca la propiedad de prueba de posicionación en **false** en el adorno.  Para obtener más información acerca de las pruebas de posicionamiento, consulte Pruebas de [posicionamiento en la capa visual](../graphics-multimedia/hit-testing-in-the-visual-layer.md).

## <a name="adorning-a-single-uielement"></a>Adorno de un solo elemento de la interfaz de usuario

Para enlazar un adorno <xref:System.Windows.UIElement>a un adorno determinado, siga estos pasos:

1. Llame al <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> método estático <xref:System.Windows.Documents.AdornerLayer> para <xref:System.Windows.UIElement> obtener un objeto para que se va a adornar. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>camina por el árbol visual, comenzando en el <xref:System.Windows.UIElement>, y devuelve la primera capa de adorno que encuentra. (Si no se encuentra ninguna capa de adornos, el método devuelve null).

2. Llame <xref:System.Windows.Documents.AdornerLayer.Add%2A> al método para enlazar el <xref:System.Windows.UIElement>adorno al destino .

 En el ejemplo siguiente se enlaza un SimpleCircleAdorner (mostrado arriba) a un <xref:System.Windows.Controls.TextBox> *myTextBox*con nombre:

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.

## <a name="adorning-the-children-of-a-panel"></a>Adornamiento de elementos secundarios de un panel

Para enlazar un adorno a <xref:System.Windows.Controls.Panel>los hijos de un , siga estos pasos:

1. Llame `static` al <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> método para buscar una capa de adorno para el elemento cuyos elementos secundarios se van a adornar.

2. Enumerar a través de los elementos secundarios del elemento primario y llamar al <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar un adorno a cada elemento secundario.

En el ejemplo siguiente se enlaza un SimpleCircleAdorner <xref:System.Windows.Controls.StackPanel> (mostrado arriba) a los elementos secundarios de un *myStackPanel*con nombre:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Información general sobre formas y dibujo básico en WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Información general sobre objetos Drawing](../graphics-multimedia/drawing-objects-overview.md)
- [Temas de información](adorners-how-to-topics.md)
