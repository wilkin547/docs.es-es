---
title: "C&#243;mo: Crear texto con sombreado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "efectos de sombra en el texto"
  - "texto, sombreados"
  - "tipografía, efectos de sombra"
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Crear texto con sombreado
En los ejemplos de esta sección se muestra cómo crear un efecto de sombra para el texto mostrado.  
  
## Ejemplo  
 El objeto <xref:System.Windows.Media.Effects.DropShadowEffect> permite crear diversos de efectos de sombra para los objetos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En el ejemplo siguiente se muestra un efecto de sombra paralela aplicada al texto.  En este caso, la sombra es una sombra suave, lo que significa que su color está desenfocado.  
  
 ![Sombra de texto con Suavidad &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.png "ShadowText01")  
Ejemplo de texto con una sombra suave  
  
 Puede controlar el ancho de una sombra estableciendo la propiedad <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>.  El valor `4.0` indica un ancho de la sombra de 4 píxeles.  Puede controlar la suavidad, o desenfoque, de una sombra modificando la propiedad <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>.  El valor `0.0` indica ausencia de desenfoque.  En el ejemplo de código siguiente se muestra cómo se crea una sombra suave.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Estos efectos de sombra no atraviesan la canalización de representación de texto de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Como resultado, ClearType se deshabilita al utilizar estos efectos.  
  
 En el ejemplo siguiente se muestra un efecto de sombra paralela nítida aplicada al texto.  En este caso, la sombra no está desenfocada.  
  
 ![Sombra de texto con Suavidad &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.png "ShadowText02")  
Ejemplo de texto con una sombra nítida  
  
 Puede crear una sombra nítida estableciendo la propiedad <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> en `0.0`, que indica que no se utiliza ningún desenfoque.  Puede controlar la dirección de la sombra modificando la propiedad <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>.  Establezca el valor direccional de esta propiedad en un valor de grados comprendido entre `0` y `360`.  En la ilustración siguiente se muestran los valores direccionales del valor de la propiedad <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>.  
  
 ![Valor de grado de sombra paralela de una sombra](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
Diagrama de dirección de DropShadow  
  
 En el ejemplo de código siguiente se muestra cómo se crea una sombra nítida.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## Utilizar un efecto de desenfoque  
 Se puede utilizar un <xref:System.Windows.Media.Effects.BlurBitmapEffect> para crear un efecto similar a la sombra que se pueda colocar tras un objeto de texto.  Un efecto de imagen de desenfoque aplicado al texto lo desenfoca de manera uniforme en todas direcciones.  
  
 En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.  
  
 ![Sombra de texto usando BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.png "ShadowText06")  
Ejemplo de texto con un efecto de desenfoque  
  
 En el ejemplo de código siguiente se muestra cómo se crea un efecto de desenfoque.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## Utilizar una transformación de traslación  
 Un <xref:System.Windows.Media.TranslateTransform> se puede utilizar para crear un efecto similar a la sombra que se puede colocar detrás de un objeto de texto.  
  
 En el ejemplo de código siguiente se utiliza un objeto <xref:System.Windows.Media.TranslateTransform> para desplazar texto.  En este ejemplo, una copia del texto primario ligeramente desplazada crea un efecto de sombra.  
  
 ![Sombra de texto usando TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.png "ShadowText07")  
Ejemplo de texto que utiliza una transformación para un efecto de sombra  
  
 En el ejemplo de código siguiente se muestra cómo crear una transformación para un efecto de sombra.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]