---
title: Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: bf0d3a64ce8860d67f0dcfd37c780f03fbd7471a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650523"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada
El <xref:System.Drawing> espacio de nombres proporciona la <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> clases para almacenar y manipular imágenes. Mediante el uso de codificadores de imagen en [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede escribir imágenes de la memoria en el disco. Mediante el uso de los descodificadores de imagen en [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede cargar imágenes desde el disco en la memoria. Un codificador convierte los datos en un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> objeto en un formato de archivo de disco designado. Un descodificador convierte los datos en un archivo de disco al formato requerido por el <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> objetos.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] tiene integrados codificadores y descodificadores que admiten los siguientes tipos de archivo:  
  
- BMP  
  
- GIF  
  
- JPEG  
  
- PNG  
  
- TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] También tiene descodificadores integrados que admiten los siguientes tipos de archivo:  
  
- WMF  
  
- EMF  
  
- ICON  
  
 Los temas siguientes describen los codificadores y descodificadores con más detalle:  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Enumerar los codificadores instalados](how-to-list-installed-encoders.md)  
 Describe cómo enumerar los codificadores disponibles en un equipo.  
  
 [Cómo: Enumerar los descodificadores instalados](how-to-list-installed-decoders.md)  
 Describe cómo enumerar los descodificadores disponibles en un equipo.  
  
 [Cómo: Determinar los parámetros admitidos por un codificador](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Describe cómo enumerar los <xref:System.Drawing.Imaging.EncoderParameters> admitidos por un codificador.  
  
 [Cómo: Convertir una imagen BMP en una imagen PNG](how-to-convert-a-bmp-image-to-a-png-image.md)  
 Describe cómo guardar una imagen en un formato de imagen diferente.  
  
 [Cómo: Establecer el nivel de compresión de JPEG](how-to-set-jpeg-compression-level.md)  
 Describe cómo cambiar el nivel de calidad de una imagen.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [About GDI+ Managed Code](about-gdi-managed-code.md) (Acerca del código administrado de GDI+)  
  
 [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
