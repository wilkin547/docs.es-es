---
title: "C&#243;mo: Crear im&#225;genes en miniatura | Microsoft Docs"
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
  - "imágenes [Windows Forms], crear vistas en miniatura"
  - "imágenes en miniatura, crear"
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# C&#243;mo: Crear im&#225;genes en miniatura
Una imagen en miniatura es la versión reducida de una imagen.  Se pueden crear imágenes en miniatura llamando al método <xref:System.Drawing.Image.GetThumbnailImage%2A> de un objeto <xref:System.Drawing.Image>.  
  
## Ejemplo  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Image> a partir de un archivo JPG.  La imagen original tiene un ancho de 640 píxeles y un alto de 479 píxeles.  Con este código se crea una imagen en miniatura con un ancho de 100 píxeles y un alto de 100 píxeles.  
  
 En la siguiente ilustración se muestra la imagen en miniatura.  
  
 ![Imagen en miniatura](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  En este ejemplo, se declara un método de devolución de llamada se declara, pero nunca se utiliza.  Esto admite todas las versiones de GDI\+.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  Para ejecutar el ejemplo, siga estos pasos:  
  
1.  Crear una nueva aplicación de Windows Forms.  
  
2.  Agregue el código de ejemplo al formulario.  
  
3.  Cree un controlador para el evento <xref:System.Windows.Forms.Control.Paint> del formulario.  
  
4.  En el controlador <xref:System.Windows.Forms.Control.Paint>, llame al método `GetThumbnail` y pase `e` para <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Encuentre un archivo de imagen del que desea realizar una miniatura.  
  
6.  En el método `GetThumbnail`, especifique la ruta de acceso y el nombre de archivo de su imagen.  
  
7.  Presione F5 para ejecutar el ejemplo.  
  
     Aparece una imagen en miniatura 100 por 100 en el formulario.  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)