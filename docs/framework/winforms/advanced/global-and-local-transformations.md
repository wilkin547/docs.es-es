---
title: "Transformaciones globales y locales | Microsoft Docs"
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
  - "matrices, con transformaciones"
  - "transformaciones, globales"
  - "transformaciones, locales"
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Transformaciones globales y locales
Una transformación global es una transformación que se aplica a todos los elementos dibujados por un objeto <xref:System.Drawing.Graphics> determinado.  Por el contrario, una transformación local es una transformación que se aplica a un elemento específico que se va a dibujar.  
  
## Transformaciones globales  
 Para crear una transformación global hay que construir un objeto <xref:System.Drawing.Graphics> y, después, manipular su propiedad <xref:System.Drawing.Graphics.Transform%2A>.  La propiedad <xref:System.Drawing.Graphics.Transform%2A> es un objeto <xref:System.Drawing.Drawing2D.Matrix>, por lo que puede almacenar cualquier secuencia de transformaciones afines.  La transformación que se almacena en la propiedad <xref:System.Drawing.Graphics.Transform%2A> se denomina transformación de coordenadas universales.  La clase <xref:System.Drawing.Graphics> proporciona varios métodos para compilar una transformación universal compuesta: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A> y <xref:System.Drawing.Graphics.TranslateTransform%2A>.  En el siguiente ejemplo se dibuja una elipse dos veces: una, antes de crear una transformación de coordenadas universales y otra, después.  La transformación, en primer lugar, ajusta la escala de la elipse en un factor de 0,5 en la dirección del eje, después, traslada 50 unidades la elipse en la dirección del eje x y, por último, rota la elipse 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 En la siguiente ilustración se muestran las matrices que forman parte de la transformación.  
  
 ![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05\_art14")  
  
> [!NOTE]
>  En el ejemplo anterior se rota la elipse alrededor del origen del sistema de coordenadas, que está en la esquina superior izquierda del área de cliente.  Esto produce un resultado diferente al de la rotación de la elipse alrededor de su propio centro.  
  
## Transformaciones locales  
 Una transformación local se aplica a un elemento específico que se va a dibujar.  Por ejemplo, un objeto <xref:System.Drawing.Drawing2D.GraphicsPath> tiene un método <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> que permite transformar los puntos de datos de ese trazado.  En el siguiente ejemplo se dibuja un rectángulo sin transformación y un trazado con una transformación de rotación.  Se supone que no hay transformación de coordenadas universales.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 La transformación de coordenadas universales puede combinarse con transformaciones locales para conseguir resultados diversos.  Por ejemplo, la transformación de coordenadas universales puede utilizarse para revisar el sistema de coordenadas, y las transformaciones locales pueden utilizarse para rotar y ajustar la escala de objetos dibujados en el nuevo sistema de coordenadas.  
  
 Supongamos que desea que el sistema de coordenadas tenga el origen a 200 píxeles del borde izquierdo del área de cliente y a 150 píxeles de la parte superior del área de cliente.  Además, supongamos que desea que la unidad de medida sea el píxel, con el eje x apuntando hacia la derecha y el eje y hacia arriba.  El sistema de coordenadas predeterminado tiene el eje y apuntando hacia abajo, así que es necesario realizar una reflexión a través del eje horizontal.  En la siguiente ilustración se muestra la matriz de dicha reflexión.  
  
 ![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.png "AboutGdip05\_art15")  
  
 A continuación, supongamos que es necesario realizar una traslación de 200 unidades hacia la derecha y 150 unidades hacia abajo.  
  
 En el siguiente ejemplo se establece el sistema de coordenadas descrito mediante el establecimiento de la transformación de coordenadas universales de un objeto <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 En el siguiente código \(ubicado al final del ejemplo anterior\) se crea un trazado formado por un rectángulo único con la esquina inferior izquierda en el origen del nuevo sistema de coordenadas.  El rectángulo se ha rellenado una vez sin transformación local y otra vez con una transformación local.  La transformación local está compuesta por un ajuste de escala horizontal en un factor de 2 seguido de una rotación de 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 En la siguiente ilustración se muestra el nuevo sistema de coordenadas y los dos rectángulos.  
  
 ![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.png "AboutGdip05\_art16")  
  
## Vea también  
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Usar transformaciones en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)