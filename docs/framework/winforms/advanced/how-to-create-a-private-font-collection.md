---
title: "C&#243;mo: Crear una colecci&#243;n de fuentes privada | Microsoft Docs"
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
  - "fuentes, crear colecciones privadas"
  - "colecciones de fuentes privadas, crear"
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Crear una colecci&#243;n de fuentes privada
La clase <xref:System.Drawing.Text.PrivateFontCollection> hereda de la clase base abstracta <xref:System.Drawing.Text.FontCollection>.  Se puede usar un objeto <xref:System.Drawing.Text.PrivateFontCollection> para mantener un conjunto de fuentes específicamente para la aplicación.  Una colección de fuentes privada puede incluir fuentes del sistema instaladas además de fuentes que no se han instalado en el equipo.  Para agregar un archivo de fuente a una colección privada, llame al método <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> de un objeto <xref:System.Drawing.Text.PrivateFontCollection>.  
  
 La propiedad <xref:System.Drawing.Text.FontCollection.Families%2A> de un objeto <xref:System.Drawing.Text.PrivateFontCollection> contiene una matriz de objetos <xref:System.Drawing.FontFamily>.  
  
 El número de familias de fuentes de una colección de fuentes privada no es necesariamente el mismo que el número de archivos de fuente que se han agregado a la colección.  Por ejemplo, supongamos que se agregan los archivos ArialBd.tff, Times.tff y TimesBd.tff a una colección.  En la colección habrá tres archivos pero sólo dos familias porque Times.tff y TimesBd.tff pertenecen a la misma familia.  
  
## Ejemplo  
 En el ejemplo siguiente se agregan los tres archivos de fuente que se muestran a un objeto <xref:System.Drawing.Text.PrivateFontCollection>:  
  
-   C:\\*raízDelSistema*\\Fonts\\Arial.tff \(Arial, normal\)  
  
-   C:\\*raízDelSistema*\\Fonts\\CourBI.tff \(Courier New, negrita cursiva\)  
  
-   C:\\*raízDelSistema*\\Fonts\\TimesBd.tff \(Times New Roman, negrita\)  
  
 El código recupera una matriz de objetos <xref:System.Drawing.FontFamily> de la propiedad <xref:System.Drawing.Text.FontCollection.Families%2A> del objeto <xref:System.Drawing.Text.PrivateFontCollection>.  
  
 Para cada objeto <xref:System.Drawing.FontFamily> de la colección, el código llama al método <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> para determinar si hay disponibles varios estilos \(normal, negrita, cursiva, negrita cursiva, subrayado y tachado\).  Los argumentos que se pasan al método <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> son miembros de la enumeración <xref:System.Drawing.FontStyle>.  
  
 Si una combinación de familia y estilo concreta está disponible, se construye un objeto <xref:System.Drawing.Font> utilizando esa familia y ese estilo.  El primer argumento que se pasa al constructor <xref:System.Drawing.Font.%23ctor%2A> es el nombre de la familia de fuentes \(no un objeto <xref:System.Drawing.FontFamily> como sucede en otras variantes del constructor <xref:System.Drawing.Font.%23ctor%2A>\).  Tras construir el objeto <xref:System.Drawing.Font>, éste se pasa al método <xref:System.Drawing.Graphics.DrawString%2A> de la clase <xref:System.Drawing.Graphics> para mostrar el nombre de la familia junto con el nombre del estilo.  
  
 El resultado del código siguiente es similar al que se muestra en la siguiente ilustración.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Arial.tff \(que se ha agregado a la colección de fuentes privada en el ejemplo de código siguiente\) es el archivo de fuente del estilo normal de Arial.  Observe, sin embargo, que el resultado del programa muestra varios estilos disponibles aparte del normal para la familia de fuentes Arial.  Esto se debe a que [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede simular los estilos negrita, cursiva y negrita cursiva a partir del estilo normal.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] también puede generar subrayados y tachados a partir del estilo normal.  
  
 De manera similar, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede simular el estilo de negrita cursiva a partir del estilo negrita o del estilo cursiva.  El resultado del programa muestra que el estilo de negrita cursiva está disponible para la familia Times a pesar de que TimesBd.tff \(Times New Roman, negrita\) es el único archivo de Times de la colección.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 <xref:System.Drawing.Text.PrivateFontCollection>   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)