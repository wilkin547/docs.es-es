---
title: Paquete de fuentes OpenType de ejemplo
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: 93bba86801ec4971e884cb4703d7a6323a2e94fe
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43870024"
---
# <a name="sample-opentype-font-pack"></a>Paquete de fuentes OpenType de ejemplo
En este tema se proporciona información general sobre las fuentes de ejemplo de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] distribuidas con [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]. Las fuentes de ejemplo admiten características de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] extendidas que se pueden usar en las aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
  
<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>Fuentes del paquete de fuentes OpenType  
 [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] proporciona un conjunto de fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] de ejemplo que se pueden usar para crear aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Las fuentes de ejemplo se proporcionan bajo licencia de Ascender Corporation. Estas fuentes implementan únicamente un subconjunto de las características totales definidas por el formato [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]. En la tabla siguiente se enumeran los nombres de las fuentes de ejemplo de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
|**Name**|**Archivo**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 En la ilustración siguiente se muestra la apariencia de las fuentes de ejemplo de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
 ![Lista de nombres de fuentes en paquete de fuentes de ejemplo](../../../../docs/framework/wpf/advanced/media/samplefontpack01.gif "samplefontpack01")  
Fuentes del paquete de fuentes OpenType  
  
 Las fuentes de ejemplo se proporcionan bajo licencia de Ascender Corporation. Ascender es un proveedor de productos de fuentes avanzados. Para asignar licencias extendidas o versiones personalizadas de las fuentes de ejemplo, vea el [sitio web de Ascender Corporation](https://go.microsoft.com/fwlink/?LinkId=182627).  
  
> [!NOTE]
>  Como programador, es su responsabilidad asegurarse de disponer de los derechos de licencia necesarios para cualquier fuente que inserte en una aplicación o redistribuya de cualquier otro modo.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Instalación de las fuentes  
 Tiene la opción de instalar las fuentes [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] de ejemplo en el directorio de fuentes predeterminado de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], **\WINDOWS\Fonts**. Use el panel de control Fuentes para instalar las fuentes. Una vez instaladas estas fuentes en el equipo, son accesibles para todas las aplicaciones que hacen referencia a las fuentes predeterminadas de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Puede mostrar un conjunto de caracteres representativo en varios tamaños de fuente haciendo doble clic en el archivo de fuente. En la captura de pantalla siguiente se muestra el archivo de la fuente Lindsey, Linds.ttf.  
  
 ![Fuente Lindsey &#40;OpenType&#41;](../../../../docs/framework/wpf/advanced/media/typographyinwpf-04.png "TypographyInWPF_04")  
Mostrar la fuente Lindsey  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Uso de las fuentes  
 Hay dos maneras de usar fuentes en una aplicación. Se pueden agregar fuentes a la aplicación como elementos de contenido del proyecto que no están insertados como recursos dentro de un ensamblado. Como alternativa, se pueden agregar las fuentes a la aplicación como elementos de recursos del proyecto insertados dentro de los archivos de ensamblado de la aplicación. Para más información, vea [Empaquetar fuentes con aplicaciones](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Documents.Typography>  
 [Características de las fuentes OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [Empaquetar fuentes con aplicaciones](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
