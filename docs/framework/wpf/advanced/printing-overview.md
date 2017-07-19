---
title: "Informaci&#243;n general sobre impresi&#243;n | Microsoft Docs"
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
  - "clases, PrintCapabilities"
  - "clases, PrintQueue"
  - "clases, PrintServer"
  - "clases, PrintTicket"
  - "ruta de acceso de impresión de GDI"
  - "ruta de acceso de impresión, XPS"
  - "PrintCapabilities (clase)"
  - "impresoras, basadas en XPSDrv"
  - "imprimir"
  - "PrintQueue y PrintServer (clases)"
  - "PrintTicket (clase)"
  - "XML Paper Specification (XPS) (formato de archivo)"
  - "XPS (XML Paper Specification) (formato de archivo)"
  - "impresoras basadas en XPSDrv"
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Informaci&#243;n general sobre impresi&#243;n
Con [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], los desarrolladores de aplicaciones que usan [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] tienen un nuevo y rico conjunto de [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de impresión y administración del sistema de impresión.  Con [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], algunas de estas mejoras del sistema de impresión también están disponibles para los desarrolladores que crean aplicaciones de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], así como para los que usan código no administrado.  La base de esta nueva funcionalidad es el nuevo formato de archivo [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] y la ruta de impresión [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Sobre XPS](#introduction_to_XPS)  
  
-   [Ruta de impresión XPS](#XPS_print_path_intro)  
  
-   [Ruta de impresión GDI](#GDI_Print_Path_intro)  
  
-   [Modelo de controlador XPSDrv](#XPS_Driver_Model_intro)  
  
-   [Temas relacionados](#seeAlso_Toggle)  
  
<a name="introduction_to_XPS"></a>   
## Sobre XPS  
 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] es un formato de documento electrónico, un formato de archivo de cola de impresión y un lenguaje de descripción de página.  Se trata de un formato de documento abierto que usa [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] y otros estándares del sector para crear documentos multiplataforma.  [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] simplifica el proceso de creación, uso compartido, impresión, visualización y archivo de documentos digitales.  Para obtener más información sobre [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], consulte el [sitio web de XPS](http://www.microsoft.com/xps).  
  
 En el artículo sobre [Imprimir archivos XPS mediante programación](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) se explican diversas técnicas de impresión de contenido basado en [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Estos ejemplos le resultarán útil para comprender el contenido de este tema. \(Los desarrolladores de código no administrado deben ver la ayuda de la *secuencia de escape de impresora del convertidor de documentos XPS de Microsoft*.  Los desarrolladores de [!INCLUDE[TLA2#tla_winforms#initcap](../../../../includes/tla2sharptla-winformssharpinitcap-md.md)] deben usar la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en el espacio de nombres <xref:System.Drawing.Printing> que no admite la ruta de impresión completa de [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)], pero que sí admite una ruta de impresión híbrida de GDI a XPS.  Consulte abajo el apartado **Arquitectura de la ruta de impresión**\).  
  
<a name="XPS_print_path_intro"></a>   
## Ruta de impresión XPS  
 La ruta de impresión [!INCLUDE[TLA#tla_metro](../../../../includes/tlasharptla-metro-md.md)] es una nueva característica de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] que redefine la administración de la impresión en aplicaciones de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  Dado que [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] puede reemplazar un lenguaje de presentación de documento \(por ejemplo, RTF\), un formato de administrador de trabajos en cola de impresión \(como WMF\) y un lenguaje de descripción de página \(por ejemplo, Postscript o PCL\), la nueva ruta de impresión mantiene el formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] desde la publicación en la aplicación hasta el procesamiento final en el dispositivo o controlador de impresora.  
  
 La ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] se basa en el modelo de controlador de impresora [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\), que proporciona varias ventajas a los desarrolladores, como impresión [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)], soporte de color mejorado y rendimiento de impresión considerablemente superior.  \(Para obtener más información sobre XPSDrv, vea el [kit de desarrollo para controladores de Windows](http://msdn.microsoft.com/library/default.asp?url=/library/dnanchor/html/DeviceDriver.asp)\).  
  
 La operación del administrador de trabajos en cola de impresión para documentos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] es esencialmente la misma que en versiones anteriores de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  Sin embargo, se ha mejorado para admitir la ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], que se suma a la ruta de impresión [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] actual.  La nueva ruta de impresión usa de forma nativa un archivo de cola de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  Aunque los controladores de impresora de modo de usuario escritos para versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] continuarán funcionando, es necesario un controlador de impresora [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\) a fin de poder usar la ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  
  
 Las ventajas de la ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] son significativas e incluyen:  
  
-   Soporte de impresión [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)].  
  
-   Soporte nativo de perfiles de color avanzados, que incluyen 32 bits por canal \(bpc\), CMYK, colores con nombre, tintas n y soporte nativo de transparencia y degradados.  
  
-   Mayor rendimiento de impresión para las aplicaciones basadas en [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] y [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)].  
  
-   Formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] estándar del sector.  
  
 Para los escenarios básicos de impresión se dispone de una sencilla e intuitiva [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] con un único punto de entrada para interfaz de usuario, configuración y envío de trabajos.  Para los escenarios avanzados se agrega soporte adicional para la personalización de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] \(o sin [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\), impresión sincrónica o asincrónica y capacidades de impresión por lotes.  Ambas opciones ofrecen soporte de impresión en modo de confianza plena o parcial.  
  
 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] se diseñó teniendo en cuenta la extensibilidad.  Con el marco de extensibilidad se pueden agregar características y capacidades a [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] de manera modular.  Las características de extensibilidad incluyen:  
  
-   Esquema de impresión.  El esquema público se actualiza periódicamente y permite la extensión rápida de las capacidades del dispositivo.  \(Consulte más abajo **PrintTicket y PrintCapabilities**\).  
  
-   Canalización de filtros extensible.  La canalización de filtros del controlador de impresora [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\) se diseñó para habilitar la impresión directa y escalable de documentos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  \(Busque “XPSDrv” en el [kit de desarrollo para controladores de Windows](http://msdn.microsoft.com/library/default.asp?url=/library/dnanchor/html/DeviceDriver.asp)\).  
  
### Arquitectura de la ruta de impresión  
 Aunque tanto las aplicaciones de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] como las de [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] admiten [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], las aplicaciones de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] usan una conversión [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] a [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] a fin de crear contenido con formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] para el controlador de impresora [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\).  Estas aplicaciones no necesitan usar la ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] y pueden seguir utilizando la impresión basada en [!INCLUDE[TLA#tla_emf](../../../../includes/tlasharptla-emf-md.md)].  Sin embargo, la mayoría de características y mejoras de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] solo están disponibles para las aplicaciones destinadas a la ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  
  
 Para habilitar el uso de las impresoras basadas en XPSDrv por parte de aplicaciones de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)], el controlador de impresora [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\) admite la conversión de formato [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] a [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. El modelo XPSDrv también proporciona un convertidor de formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] a [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] para que las aplicaciones de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] puedan imprimir documentos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  Para aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], la conversión de formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] a [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] se realiza de forma automática mediante los métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la clase <xref:System.Windows.Xps.XpsDocumentWriter> siempre que la cola de impresión de destino de la operación de escritura no tenga un controlador de XPSDrv. \(Las aplicaciones de [!INCLUDE[TLA2#tla_winforms#initcap](../../../../includes/tla2sharptla-winformssharpinitcap-md.md)] no pueden imprimir documentos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\).  
  
 En la siguiente ilustración se muestra el subsistema de impresión y se definen las partes proporcionadas por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] y las partes definidas por proveedores de software y hardware.  
  
 ![Sistema de impresión XPS](../../../../docs/framework/wpf/advanced/media/xpsprint.PNG "XPSPrint")  
  
### Impresión XPS básica  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] define una [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] básica y una avanzada.  Para aquellas aplicaciones que no requieren una amplia personalización de impresión o acceso a todo el conjunto de características de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], hay disponible soporte básico de impresión.  El soporte básico de impresión se expone a través de un control de diálogo de impresión que requiere una configuración mínima y presenta una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] reconocible.  Muchas de las características de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] están disponibles a través de este modelo simplificado de impresión.  
  
#### PrintDialog  
 El control <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName> proporciona un único punto de entrada para [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y envío de trabajos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  Para obtener información sobre creación de instancias y uso del control, vea el artículo en el que se explica [Invocar un cuadro de diálogo de impresión](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md).  
  
### Impresión XPS avanzada  
 Para tener acceso a un conjunto completo de características de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], debe usarse la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de impresión avanzada.  A continuación se describen con más detalle varias [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] pertinentes.  Para obtener una lista completa de [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], consulte las referencias de espacio de nombres <xref:System.Windows.Xps> y <xref:System.Printing>.  
  
#### PrintTicket y PrintCapabilities  
 Las clases <xref:System.Printing.PrintTicket> y <xref:System.Printing.PrintCapabilities> constituyen la base de las características avanzadas de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  Ambos tipos de objetos son estructuras con formato [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] de características orientadas a la impresión, como intercalación, impresión a dos caras, grapado, etc.  Estas estructuras se definen mediante el esquema de impresión.  Un <xref:System.Printing.PrintTicket> indica a una impresora cómo procesar un trabajo de impresión.  La clase <xref:System.Printing.PrintCapabilities> define las capacidades de una impresora.  Mediante una consulta de las capacidades de una impresora, se puede crear un <xref:System.Printing.PrintTicket> que aproveche al máximo las características compatibles de una impresora.  De forma similar, se pueden evitar las características no compatibles.  
  
 En el ejemplo siguiente se muestra cómo consultar las <xref:System.Printing.PrintCapabilities> de una impresora y crear un <xref:System.Printing.PrintTicket> mediante código.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](../../../../samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### PrintServer y PrintQueue  
 La clase <xref:System.Printing.PrintServer> representa un servidor de impresión de red y la clase <xref:System.Printing.PrintQueue> representa una impresora y la cola de trabajos de salida asociados a él.  Juntas, estas [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] permiten la administración avanzada de los trabajos de impresión de un servidor.  Un <xref:System.Printing.PrintServer>, o una de sus clases derivadas, se usa para administrar un <xref:System.Printing.PrintQueue>.  El método <xref:System.Printing.PrintQueue.AddJob%2A> se usa para insertar un nuevo trabajo de impresión en la cola.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Printing.LocalPrintServer> y tener acceso a su <xref:System.Printing.PrintQueue> predeterminado mediante código.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### XpsDocumentWriter  
 Un <xref:System.Windows.Xps.XpsDocumentWriter>, con sus métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>, se usa para escribir documentos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] en un <xref:System.Printing.PrintQueue>.  Por ejemplo, el método <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> se usa para generar un documento [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] y <xref:System.Printing.PrintTicket> sincrónicamente.  El método <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> se usa para generar un documento [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] y <xref:System.Printing.PrintTicket> asincrónicamente.  
  
 En el siguiente ejemplo se muestra cómo crear un <xref:System.Windows.Xps.XpsDocumentWriter> mediante código.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Los métodos <xref:System.Printing.PrintQueue.AddJob%2A> también proporcionan formas de imprimir.  Consulte el artículo sobre [Imprimir archivos XPS mediante programación](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) para obtener información detallada.  
  
<a name="GDI_Print_Path_intro"></a>   
## Ruta de impresión GDI  
 Mientras las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] admiten de forma nativa la ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], las aplicaciones de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] también pueden sacar partido de algunas características de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  El controlador de impresora [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\) puede convertir una salida basada en [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] a formato [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  Para escenarios avanzados, se admite la conversión personalizada de contenido mediante la [secuencia de escape de impresora de convertidor de documentos XPS de Microsoft](_win32_MXDC_ESCAPE).  De forma similar, las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] también pueden generar una salida a la ruta de impresión [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] mediante la llamada a uno de los métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> o <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la clase <xref:System.Windows.Xps.XpsDocumentWriter> y la designación de una impresora que no sea XPSDrv como la cola de impresión de destino.  
  
 Para las aplicaciones que no requieren funcionalidad o soporte [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], la ruta de impresión [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] actual se mantiene sin cambios.  
  
-   Para obtener material de referencia adicional sobre la ruta de impresión [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] y las distintas opciones de conversión de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)], consulte la [secuencia de escape de impresora de convertidor de documentos XPS de Microsoft](_win32_MXDC_ESCAPE) y “XPSDrv” en el [kit de desarrollo para controladores de Windows](http://msdn.microsoft.com/library/default.asp?url=/library/dnanchor/html/DeviceDriver.asp).  
  
<a name="XPS_Driver_Model_intro"></a>   
## Modelo de controlador XPSDrv  
 La ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] mejora la eficacia del administrador de trabajos en cola ya que usa [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] como el formato nativo de la cola de impresión cuando se imprime en un controlador o una impresora habilitados para [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  El proceso simplificado de administración de trabajos en cola elimina la necesidad de generar un archivo de cola intermedio, como un archivo de datos [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], antes de poner en cola el documento.  Gracias a tamaños de archivo de cola más pequeños, la ruta de impresión [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] puede reducir el tráfico de red y mejorar el rendimiento de impresión.  
  
 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] es un formato cerrado que representa la salida de la aplicación como una serie de llamadas a [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] para la presentación de servicios.  A diferencia de [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], el formato de la cola [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] representa el documento real sin necesidad de más interpretación al generar una salida a un controlador de impresora basado en [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\).  Los controladores pueden trabajar directamente con los datos en el formato.  Esta capacidad elimina las conversiones de espacio de color y datos que son necesarias cuando se usan archivos [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] y controladores de impresión basados en [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)].  
  
 El tamaño de los archivos de cola de impresión suele reducirse cuando se usan documentos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] cuyo destino es un controlador de impresora [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] \(XPSDrv\) en comparación a sus equivalentes [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)]; sin embargo, hay excepciones:  
  
-   Un gráfico vectorial muy complejo, con varias capas o escrito de forma ineficaz puede ser mayor que una versión de mapa de bits del mismo gráfico.  
  
-   Para la presentación en pantalla, los archivos XPS insertan fuentes del dispositivo y del equipo, mientras que los archivos de cola de impresión GDI no insertan fuentes de dispositivo.  Sin embargo, ambos tipos de fuentes se incluyen en un subconjunto \(ver abajo\) y los controladores de impresora pueden quitar las fuentes de dispositivo antes de transmitir el archivo a la impresora.  
  
 La reducción del tamaño de cola de impresión se consigue a través de varios mecanismos:  
  
-   **Creación de un subconjunto de fuentes**.  Solo los caracteres usados en el documento real se almacenan en el archivo [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  
  
-   **Soporte de gráficos avanzados**.  El soporte nativo para transparencia y primitivas de degradado evita la rasterización del contenido en el documento [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
-   **Identificación de recursos comunes**.  Los recursos que se usan varias veces \(como una imagen que representa un logotipo corporativo\) se tratan como recursos compartidos y se cargan solamente una vez.  
  
-   **Compresión ZIP**.  Todos los documentos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] usan la compresión ZIP.  
  
## Vea también  
 <xref:System.Windows.Controls.PrintDialog>   
 <xref:System.Windows.Xps.XpsDocumentWriter>   
 <xref:System.Windows.Xps.Packaging.XpsDocument>   
 <xref:System.Printing.PrintTicket>   
 <xref:System.Printing.PrintCapabilities>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.PrintQueue>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/printing-how-to-topics.md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [XPS](http://www.microsoft.com/xps)   
 [Almacenamiento y serialización de documentos](../../../../docs/framework/wpf/advanced/document-serialization-and-storage.md)   
 [Secuencia de escape de impresora de convertidor de documentos XPS de Microsoft](_win32_MXDC_ESCAPE)