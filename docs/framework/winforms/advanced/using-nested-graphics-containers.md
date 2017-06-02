---
title: "Utilizar contenedores de gr&#225;ficos anidados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "gráficos [formularios Windows Forms], recortar"
  - "gráficos, contenedores anidados"
  - "gráficos, transformaciones en objetos anidados"
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Utilizar contenedores de gr&#225;ficos anidados
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona contenedores que pueden utilizarse para reemplazar o aumentar temporalmente parte del estado de un objeto <xref:System.Drawing.Graphics>.  Para crear un contenedor nuevo hay que llamar al método <xref:System.Drawing.Graphics.BeginContainer%2A> de un objeto <xref:System.Drawing.Graphics>.  Se puede llamar a <xref:System.Drawing.Graphics.BeginContainer%2A> varias veces para formar contenedores anidados.  Cada llamada a <xref:System.Drawing.Graphics.BeginContainer%2A> debe emparejarse con una llamada a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## Transformaciones de los contenedores anidados  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Graphics> y un contenedor dentro de dicho objeto.  La transformación universal del objeto <xref:System.Drawing.Graphics> es una traslación de 100 unidades en la dirección del eje x y de 80 unidades en la dirección del eje y.  La transformación universal del contenedor es una rotación de 30 grados.  El código realiza dos veces la llamada `DrawRectangle(pen, -60, -30, 120, 60)` .  La primera llamada a <xref:System.Drawing.Graphics.DrawRectangle%2A> está dentro del contenedor; es decir, la llamada está entre las llamadas a <xref:System.Drawing.Graphics.BeginContainer%2A> y <xref:System.Drawing.Graphics.EndContainer%2A>.  La segunda llamada a <xref:System.Drawing.Graphics.DrawRectangle%2A> se produce después de la llamada a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 En el fragmento de código anterior, el rectángulo dibujado desde dentro del contenedor es transformado primero por la transformación universal del contenedor \(rotación\) y después por la transformación universal del objeto <xref:System.Drawing.Graphics> \(traslación\).  El rectángulo dibujado desde fuera del contenedor sólo es transformado por la transformación universal del objeto <xref:System.Drawing.Graphics> \(traslación\).  En la siguiente ilustración se muestran los dos rectángulos.  
  
 ![Contenedores anidados](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## Recortar en los contenedores anidados  
 En el siguiente ejemplo se muestra cómo los contenedores anidados controlan las regiones de recorte.  En el código siguiente se crea un objeto <xref:System.Drawing.Graphics> y un contenedor dentro de dicho objeto.  La región de recorte del objeto <xref:System.Drawing.Graphics> es un rectángulo, mientras que la del contenedor es una elipse.  El código hace dos llamadas al método <xref:System.Drawing.Graphics.DrawLine%2A>.  La primera llamada a <xref:System.Drawing.Graphics.DrawLine%2A> está dentro del contenedor y la segunda llamada a <xref:System.Drawing.Graphics.DrawLine%2A> está fuera del contenedor \(después de la llamada a <xref:System.Drawing.Graphics.EndContainer%2A>\).  La primera línea se recorta por la intersección de las dos regiones de recorte.  La segunda línea se recorta únicamente por la región de recorte rectangular del objeto <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 En la siguiente ilustración se muestran las dos líneas recortadas.  
  
 ![Contenedor anidado](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 Cómo se indica en los dos ejemplos anteriores, las transformaciones y las regiones de recorte son acumulativas en los contenedores anidados.  Si se establecen las transformaciones universales del contenedor y del objeto <xref:System.Drawing.Graphics>, ambas se aplicarán a los elementos dibujados desde dentro del contenedor.  Primero se aplicará la transformación del contenedor y la transformación del objeto <xref:System.Drawing.Graphics> se aplicará en segundo lugar.  Si se establecen las regiones de recorte del contenedor y del objeto <xref:System.Drawing.Graphics>, los elementos que se dibujen desde dentro del contenedor se recortarán por la intersección de las dos regiones de recorte.  
  
## Valores de calidad de los contenedores anidados  
 Los valores de calidad \(<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A> y similares\) de los contenedores anidados no son acumulativos, sino que reemplazan de forma temporal a los valores de calidad de un objeto <xref:System.Drawing.Graphics>.  Cuando se crea un contenedor nuevo, los valores de calidad de dicho contenedor se establecen en sus parámetros predeterminados.  Por ejemplo, supongamos que un objeto <xref:System.Drawing.Graphics> tiene un modo de suavizado <xref:System.Drawing.Drawing2D.SmoothingMode>.  Cuando se crea un contenedor, el modo de suavizado dentro del contenedor es el modo de suavizado predeterminado.  El modo de suavizado del contenedor se puede elegir libremente, y los elementos que se dibujen desde dentro del contenedor se ajustarán al modo establecido.  Los elementos dibujados después de la llamada a <xref:System.Drawing.Graphics.EndContainer%2A> se dibujarán según el modo de suavizado \(<xref:System.Drawing.Drawing2D.SmoothingMode>\) establecido antes de la llamada a <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## Varias capas de contenedores anidados  
 Los objetos <xref:System.Drawing.Graphics> no están limitados a un único contenedor.  Se puede crear una secuencia de contenedores, cada uno anidado en el anterior, y especificar la transformación universal, la región de recorte y los valores de calidad de cada uno de estos contenedores anidados.  Si la llamada a un método de dibujo se realiza desde dentro del contenedor más interno, las transformaciones se aplicarán en orden, desde el contenedor más interno hasta el más externo.  Los elementos dibujados desde dentro del contenedor más interno serán recortados por la intersección de todas las regiones de recorte.  
  
 En el ejemplo siguiente se crea un objeto <xref:System.Drawing.Graphics> y se establece la indicación de representación de texto en <xref:System.Drawing.Drawing2D.SmoothingMode>.  El código crea dos contenedores, uno anidado dentro del otro.  La indicación de representación de texto del contenedor exterior se establece en <xref:System.Drawing.Text.TextRenderingHint> y la del contenedor interior en <xref:System.Drawing.Drawing2D.SmoothingMode>.  El código dibuja tres cadenas: una desde el contenedor interior, otra desde el contenedor exterior y otra desde el propio objeto <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 En la siguiente ilustración se muestran las tres cadenas.  Las cadenas dibujadas desde el contenedor interior y desde el objeto <xref:System.Drawing.Graphics> se suavizan mediante el suavizado de contorno.  La cadena dibujada desde el contenedor exterior no se suaviza mediante suavizado de contorno porque la propiedad <xref:System.Drawing.Graphics.TextRenderingHint%2A> está establecida en <xref:System.Drawing.Text.TextRenderingHint>.  
  
 ![Contenedores anidados](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## Vea también  
 <xref:System.Drawing.Graphics>   
 [Administrar el estado de un objeto Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)