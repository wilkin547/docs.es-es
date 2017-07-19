---
title: "C&#243;mo: Crear un degradado lineal | Microsoft Docs"
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
  - "colores, crear degradados lineales"
  - "degradados"
  - "degradados, crear lineales"
  - "degradados lineales, crear"
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Crear un degradado lineal
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona degradados lineales horizontales, verticales y diagonales.  De manera predeterminada, el color de un degradado lineal cambia de manera uniforme.  Sin embargo, los degradados lineales se pueden personalizar para que el color cambie de manera no uniforme.  
  
 En el siguiente ejemplo se rellenan una línea, una elipse y un rectángulo con un pincel degradado lineal horizontal:  
  
 El constructor <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> recibe cuatro argumentos: dos puntos y dos colores.  El primer punto \(0, 10\) está asociado al primer color \(rojo\) y el segundo punto \(200, 10\) está asociado al segundo color \(azul\).  Tal como se espera, la línea que se dibuja de \(0, 10\) a \(200, 10\) cambia gradualmente de rojo a azul.  
  
 Las decenas en los puntos \(50, 10\) y \(200, 10\) no tienen importancia.  Lo importante es que los dos puntos tengan la misma segunda coordenada: la línea que los conecta es horizontal.  La elipse y el rectángulo también cambian gradualmente de rojo a azul al pasar la coordenada horizontal de 0 a 200.  
  
 En la siguiente ilustración se muestran la línea, la elipse y el rectángulo.  Observe que el degradado de color se repite cuando la coordenada horizontal aumenta por encima de 200.  
  
 ![Degradado lineal](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### Para utilizar degradados lineales horizontales  
  
-   Pase el rojo opaco y el azul opaco como el tercer y el cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 En el ejemplo anterior, los componentes de color cambian linealmente al desplazarnos de una coordenada horizontal de 0 a una coordenada horizontal de 200.  Por ejemplo, un punto cuya primera coordenada esté a mitad de camino entre 0 y 200 tendrá un componente azul que estará a mitad de camino entre 0 y 255.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] permite ajustar la manera en que cambia un color desde un extremo del degradado al otro.  Supongamos que se desea crear un pincel degradado que cambia de negro a rojo según la tabla siguiente.  
  
|Coordenada horizontal|Componentes RGB|  
|---------------------------|---------------------|  
|0|\(0, 0, 0\)|  
|40|\(128, 0, 0\)|  
|200|\(255, 0, 0\)|  
  
 Observe que el componente rojo tiene la mitad de la intensidad cuando la coordenada horizontal es tan sólo un 20 por ciento del recorrido de 0 a 200.  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> de un objeto <xref:System.Drawing.Drawing2D.LinearGradientBrush> para asociar tres intensidades relativas a tres posiciones relativas.  Como en la tabla anterior, una intensidad relativa de 0,5 está asociada a una posición relativa de 0,2.  El código rellena una elipse y un rectángulo con el pincel degradado.  
  
 En la siguiente ilustración se muestran la elipse y el rectángulo resultantes.  
  
 ![Degradado lineal](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### Para personalizar degradados lineales  
  
-   Pase el negro opaco y el rojo opaco como el tercer y el cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Los degradados de los ejemplos anteriores son horizontales; es decir, el color cambia gradualmente al desplazarnos por cualquier línea horizontal.  También se pueden definir degradados verticales y diagonales.  
  
 En el ejemplo siguiente se pasan los puntos \(0, 0\) y \(200, 100\) a un constructor <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>.  El color azul está asociado a \(0, 0\) y el color verde a \(200, 100\).  Con el pincel degradado lineal se rellenan una línea \(con ancho de lápiz 10\) y una elipse.  
  
 En la siguiente ilustración se muestran la línea y la elipse.  Observe que el color de la elipse cambia gradualmente al desplazarse por cualquier línea paralela a la línea que pasa por los puntos \(0, 0\) y \(200, 100\).  
  
 ![Degradado lineal](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### Para crear degradados lineales diagonales  
  
-   Pase el azul opaco y el verde opaco como el tercer y el cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## Vea también  
 [Utilizar un pincel degradado para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)