---
title: Información general sobre impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print path [WPF], XPS
- printers [WPF], XPSDrv-based
- printing [WPF]
- PrintQueue class PrintServer class [WPF]
- XML Paper Specification (XPS) file format
- XPS (XML Paper Specification) file format
- XPSDrv-based printers
- GDI print path [WPF]
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
ms.openlocfilehash: be82b64581ee178b463950d4b8cdae1f98949161
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545306"
---
# <a name="printing-overview"></a>Información general sobre impresión
Con Microsoft .NET Framework, los desarrolladores de aplicaciones que usan Windows Presentation Foundation (WPF) tienen un nuevo conjunto de API de impresión y administración del sistema de impresión. Con [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], algunas de estas mejoras del sistema de impresión también están disponibles para los desarrolladores que crean aplicaciones de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], así como para los que usan código no administrado. La base de esta nueva funcionalidad es el nuevo formato de archivo [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] y la ruta de impresión [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Sobre XPS  
 XPS es un formato de documento electrónico, un formato de archivo de cola de impresión y un lenguaje de descripción de página. Es un formato de documento abierto que usa [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], convenciones de empaquetado abierto (OPC) y otros estándares del sector para crear documentos multiplataforma. XPS simplifica el proceso mediante el cual los documentos digitales se crean, comparten, imprimen, ven y archivan. Para obtener información adicional sobre XPS, consulte [documentos XPS](/windows/desktop/printdocs/documents).  
  
 Varias técnicas para imprimir contenido basado en XPS mediante [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se muestran en [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md). Estos ejemplos le resultarán útil para comprender el contenido de este tema. (Los desarrolladores de código no administrado deben ver la documentación de la [función MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Windows Forms desarrolladores deben usar la API en el <xref:System.Drawing.Printing> espacio de nombres que no admite la [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] ruta de impresión completa, pero admite una ruta de impresión híbrida de GDI a XPS. Consulte el siguiente apartado **Arquitectura de la ruta de impresión**).  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Ruta de impresión XPS  
 La ruta de impresión de XML Paper Specification (XPS) es [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] una nueva característica que redefine la forma en que se controla la impresión en aplicaciones de Windows. Dado [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] que puede reemplazar un lenguaje de presentación de documentos (como RTF), un formato de administrador de trabajos de impresión (como WMF) y un lenguaje de descripción de página (como PCL o PostScript), la nueva ruta de impresión mantiene el formato XPS de la publicación de la aplicación al procesamiento final en el dispositivo o controlador de impresión.  
  
 La ruta de impresión XPS se basa en el modelo de controlador de impresora XPS (XPSDrv), que proporciona varias ventajas a [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] los desarrolladores, como impresión, soporte de color mejorado y rendimiento de impresión considerablemente mejorado. (Para obtener más información sobre XPSDrv, consulte la [documentación del kit de controladores de Windows](/windows-hardware/drivers/)).  
  
 La operación del administrador de trabajos de impresión para documentos XPS es esencialmente la misma que en versiones anteriores de Windows. Sin embargo, se ha mejorado para admitir la ruta de impresión XPS además de la ruta de impresión de GDI existente. La nueva ruta de impresión usa de forma nativa un archivo de cola XPS. Aunque los controladores de impresora de modo de usuario escritos para [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] versiones anteriores de seguirán funcionando, es necesario un controlador de impresora XPS (XPSDrv) para poder usar la ruta de impresión XPS.  
  
 Las ventajas de la ruta de impresión XPS son significativas e incluyen:  
  
- Soporte de impresión [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)].  
  
- Soporte nativo de perfiles de color avanzados, que incluyen 32 bits por canal (bpc), CMYK, colores con nombre, tintas n y soporte nativo de transparencia y degradados.  
  
- Rendimiento de impresión mejorado para aplicaciones .NET Framework [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y basadas en.  
  
- Formato XPS estándar del sector.  
  
 En el caso de los escenarios de impresión básicos, hay disponible una API sencilla e intuitiva con un único punto de entrada para la interfaz de usuario, la configuración y el envío de trabajos. Para los escenarios avanzados se agrega soporte adicional para la personalización de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o sin [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), impresión sincrónica o asincrónica y capacidades de impresión por lotes. Ambas opciones ofrecen soporte de impresión en modo de confianza plena o parcial.  
  
 XPS se diseñó teniendo en cuenta la extensibilidad. Con el marco de extensibilidad, se pueden agregar características y capacidades a XPS de una manera modular. Las características de extensibilidad incluyen:  
  
- Esquema de impresión. El esquema público se actualiza periódicamente y permite la extensión rápida de las capacidades del dispositivo. (Consulte más abajo **PrintTicket y PrintCapabilities**).  
  
- Canalización de filtros extensible. La canalización de filtros del controlador de impresora XPS (XPSDrv) se diseñó para habilitar la impresión directa y escalable de documentos XPS. Para obtener más información, consulte [controladores de impresora XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Arquitectura de la ruta de impresión  
 Aunque las aplicaciones [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dey.NETFrameworkadmitenXPS,ylasaplicacionesdeWindowsFormsusanunaconversióndeGDIaXPSparacrearcontenidoconformatoXPSparaelcontroladordeimpresoraXPS[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] (XPSDrv). Estas aplicaciones no necesitan usar la ruta de impresión XPS y pueden seguir utilizando la impresión basada en metarchivo mejorado (EMF). Sin embargo, la mayoría de las características y mejoras de XPS solo están disponibles para las aplicaciones que tienen como destino la ruta de impresión XPS.  
  
 Para habilitar el uso de las impresoras basadas en XPSDrv [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] por parte de y Windows Forms aplicaciones, el controlador de impresora XPS (XPSDrv) admite la conversión de GDI al formato XPS. El modelo XPSDrv también proporciona un convertidor para el formato de XPS a GDI [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para que las [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] aplicaciones puedan imprimir documentos. En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] el caso de las aplicaciones, los <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> métodos y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la <xref:System.Windows.Xps.XpsDocumentWriter> clase realizan automáticamente la conversión del formato XPS a GDI siempre que la cola de impresión de destino de la operación de escritura no tenga un controlador XPSDrv. (Windows Forms aplicaciones no pueden [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] imprimir documentos).  
  
 En la ilustración siguiente se muestra el subsistema de impresión y se definen las [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]partes proporcionadas por y las partes definidas por los proveedores de software y hardware:  
  
 ![Captura de pantalla que muestra el sistema de impresión XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Impresión XPS básica  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]define una API básica y avanzada. En el caso de las aplicaciones que no requieren una personalización de impresión amplia o el acceso al conjunto completo de características de XPS, está disponible el soporte básico de impresión. El soporte básico de impresión se expone a través de un control de diálogo de impresión que requiere una configuración mínima y presenta una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] reconocible. Muchas características de XPS están disponibles con este modelo de impresión simplificado.  
  
#### <a name="printdialog"></a>PrintDialog  
 El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control proporciona un único punto de entrada [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]para, configuración y envío de trabajos XPS. Para obtener información sobre la creación de instancias y el uso del control, consulte [Invocar un cuadro de diálogo de impresión](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Impresión XPS avanzada  
 Para tener acceso al conjunto completo de características de XPS, se debe usar la API de impresión avanzada. A continuación se describen con más detalle varias API pertinentes. Para obtener una lista completa de las API de ruta de impresión <xref:System.Windows.Xps> XPS <xref:System.Printing> , consulte las referencias de espacio de nombres y.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket y PrintCapabilities  
 Las <xref:System.Printing.PrintTicket> clases <xref:System.Printing.PrintCapabilities> y son la base de las características avanzadas de XPS. Ambos tipos de objetos son estructuras con formato [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] de características orientadas a la impresión, como intercalación, impresión a dos caras, grapado, etc. Estas estructuras se definen mediante el esquema de impresión. Un <xref:System.Printing.PrintTicket> indica a una impresora cómo procesar un trabajo de impresión. La clase <xref:System.Printing.PrintCapabilities> define las capacidades de una impresora. Mediante una consulta de las capacidades de una impresora, se puede crear un <xref:System.Printing.PrintTicket> que aproveche al máximo las características compatibles de una impresora. De forma similar, se pueden evitar las características no compatibles.  
  
 En el ejemplo siguiente se muestra cómo consultar las <xref:System.Printing.PrintCapabilities> de una impresora y crear un <xref:System.Printing.PrintTicket> mediante código.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer y PrintQueue  
 La clase <xref:System.Printing.PrintServer> representa un servidor de impresión de red y la clase <xref:System.Printing.PrintQueue> representa una impresora y la cola de trabajos de salida asociados a él. Juntas, estas API permiten la administración avanzada de los trabajos de impresión de un servidor. Un <xref:System.Printing.PrintServer>, o una de sus clases derivadas, se usa para administrar un <xref:System.Printing.PrintQueue>. El método <xref:System.Printing.PrintQueue.AddJob%2A> se usa para insertar un nuevo trabajo de impresión en la cola.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Printing.LocalPrintServer> y tener acceso a su <xref:System.Printing.PrintQueue> predeterminado mediante código.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 , Con sus <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> numerosos métodos y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> , se usa para escribir documentos XPS en un <xref:System.Printing.PrintQueue>. <xref:System.Windows.Xps.XpsDocumentWriter> Por ejemplo, el <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> método se usa para generar un documento XPS y <xref:System.Printing.PrintTicket> de forma sincrónica. El <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> método se usa para generar un documento XPS y <xref:System.Printing.PrintTicket> de forma asincrónica.  
  
 En el siguiente ejemplo se muestra cómo crear un <xref:System.Windows.Xps.XpsDocumentWriter> mediante código.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Los métodos <xref:System.Printing.PrintQueue.AddJob%2A> también proporcionan formas de imprimir. Consulte [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md). para obtener información detallada.  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Ruta de impresión GDI  
 Aunque [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] las aplicaciones admiten de forma nativa la ruta [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de impresión de XPS, y Windows Forms aplicaciones también pueden aprovechar algunas características de XPS. El controlador de impresora XPS (XPSDrv) puede convertir la salida basada en GDI al formato XPS. En escenarios avanzados, se admite la conversión personalizada de contenido mediante el [convertidor de documentos XPS de Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). Del mismo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] modo, las aplicaciones también pueden generar resultados en la ruta de impresión GDI <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> llamando a uno de <xref:System.Windows.Xps.XpsDocumentWriter> los métodos o <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la clase y designando una impresora que no sea XpsDrv como cola de impresión de destino.  

En el caso de las aplicaciones que no requieren funcionalidad o soporte XPS, la ruta de impresión GDI actual permanece sin cambios.  
  
- Para obtener material de referencia adicional sobre la ruta de impresión GDI y las distintas opciones de conversión de XPS, consulte [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) y [controladores de impresora XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>Modelo de controlador XPSDrv  
 La ruta de impresión XPS mejora la eficacia del administrador de trabajos de impresión mediante el uso de XPS como formato nativo de la cola de impresión cuando se imprime en una impresora o un controlador habilitado para XPS. El proceso de puesta en cola simplificado elimina la necesidad de generar un archivo de cola intermedio, como un archivo de datos EMF, antes de que se pongan en cola el documento. A través de tamaños de archivo de cola más pequeños, la ruta de impresión XPS puede reducir el tráfico de red y mejorar el rendimiento de impresión.  
  
 EMF es un formato cerrado que representa la salida de la aplicación como una serie de llamadas a GDI para los servicios de representación. A diferencia de EMF, el formato de cola XPS representa el documento real sin necesidad de una mayor interpretación cuando se envía a un controlador de impresora basado en XPS (XPSDrv). Los controladores pueden trabajar directamente con los datos en el formato. Esta capacidad elimina las conversiones de espacio de color y datos que son necesarias cuando se usan archivos EMF y controladores de impresión basados en GDI.  
  
 Los tamaños de los archivos de cola de impresión suelen reducirse cuando se usan documentos XPS que tienen como destino un controlador de impresora XPS (XPSDrv) en comparación con sus equivalentes EMF; sin embargo, hay excepciones:  
  
- Un gráfico vectorial muy complejo, con varias capas o escrito de forma ineficaz puede ser mayor que una versión de mapa de bits del mismo gráfico.  
  
- Para la presentación en pantalla, los archivos XPS insertan fuentes del dispositivo y del equipo, mientras que los archivos de cola de impresión GDI no insertan fuentes de dispositivo. Sin embargo, ambos tipos de fuentes se incluyen en un subconjunto (ver abajo) y los controladores de impresora pueden quitar las fuentes de dispositivo antes de transmitir el archivo a la impresora.  
  
 La reducción del tamaño de cola de impresión se consigue a través de varios mecanismos:  
  
- **Creación de un subconjunto de fuentes**. Solo los caracteres usados en el documento real se almacenan en el archivo XPS.  
  
- **Compatibilidad con gráficos avanzados**. El soporte nativo para transparencia y primitivas de degradado evita la rasterización del contenido en el documento [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
- **Identificación de recursos comunes**. Los recursos que se usan varias veces (como una imagen que representa un logotipo corporativo) se tratan como recursos compartidos y se cargan solamente una vez.  
  
- **Compresión ZIP**. Todos los documentos XPS usan la compresión ZIP.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Temas "Cómo..."](printing-how-to-topics.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Documentos XPS](/windows/desktop/printdocs/documents)
- [Almacenamiento y serialización de documentos](document-serialization-and-storage.md)
- [Convertidor de documentos XPS de Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
