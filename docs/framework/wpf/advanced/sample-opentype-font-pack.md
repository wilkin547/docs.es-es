---
title: "Paquete de fuentes OpenType de ejemplo | Microsoft Docs"
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
  - "fuentes, paquete de fuentes OpenType"
  - "paquete de fuentes OpenType"
  - "tipografía, paquete de fuentes OpenType"
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Paquete de fuentes OpenType de ejemplo
En este tema se proporciona información general sobre las fuentes de ejemplo de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] distribuidas con [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)].  Las fuentes del ejemplo admiten características [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] extendidas que se pueden utilizar en las aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="overview"></a>   
## Fuentes del paquete de fuentes OpenType  
 [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] proporciona un conjunto de fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] de ejemplo que puede utilizar para crear aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Estas fuentes de ejemplo se proporcionan bajo licencia de Ascender Corporation.  Estas fuentes implementan únicamente un subconjunto de las características totales definidas por el formato [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  En la tabla siguiente se enumeran los nombres de las fuentes de ejemplo de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
|**Name**|**Archivo**|  
|--------------|-----------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 En la ilustración siguiente se muestra la apariencia de las fuentes de ejemplo de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
 ![Lista de nombres de fuentes en paquete de fuentes de ejemplo](../../../../docs/framework/wpf/advanced/media/samplefontpack01.png "samplefontpack01")  
Fuentes del paquete de fuentes OpenType  
  
 Estas fuentes de ejemplo se proporcionan bajo licencia de Ascender Corporation.  Ascender es un proveedor de productos de fuentes avanzados.  Para otorgar licencias extendidas o versiones personalizadas de las fuentes del ejemplo, vea [el sitio web de Ascender Corporation](http://go.microsoft.com/fwlink/?LinkId=182627).  
  
> [!NOTE]
>  Como programador, es su responsabilidad asegurarse de disponer de los derechos de licencia necesarios para cualquier fuente que incruste en una aplicación o redistribuya de cualquier otro modo.  
  
<a name="installing_the_fonts"></a>   
## Instalar las fuentes  
 Si lo desea, puede instalar las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] de ejemplo en el directorio de fuentes predeterminado de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], **~\\WINDOWS\\Fonts**.  Use el panel de control Fuentes para instalar las fuentes.  Una vez instaladas estas fuentes en el equipo, están accesibles para todas las aplicaciones que hacen referencia a las fuentes predeterminadas de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Puede mostrar un juego de caracteres representativo en varios tamaños de fuente haciendo doble clic en el archivo de fuente.  En la captura de pantalla siguiente se muestra el archivo de la fuente Lindsey, Linds.ttf.  
  
 ![Fuente Lindsey &#40;OpenType&#41;](../../../../docs/framework/wpf/advanced/media/typographyinwpf-04.png "TypographyInWPF\_04")  
Mostrar la fuente Lindsey  
  
<a name="using_the_fonts"></a>   
## Utilizar las fuentes  
 Hay dos maneras de usar fuentes en una aplicación.  Puede agregar fuentes a la aplicación como elementos de contenido del proyecto que no están incrustados como recursos dentro de un ensamblado.  Como alternativa, puede agregar las fuentes a la aplicación como elementos de recursos del proyecto incrustados dentro de los archivos de ensamblado de la aplicación.  Para obtener más información, vea [Empaquetar fuentes con aplicaciones](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md).  
  
## Vea también  
 <xref:System.Windows.Documents.Typography>   
 [Características de las fuentes OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [Empaquetar fuentes con aplicaciones](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)