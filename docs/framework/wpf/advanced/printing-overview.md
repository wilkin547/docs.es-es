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
ms.openlocfilehash: acfc252708bf8be7abacb1adc2968122501315a0
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860198"
---
# <a name="printing-overview"></a>Información general sobre impresión
Con Microsoft .NET Framework, los desarrolladores de aplicaciones con Windows Presentation Foundation (WPF) tienen un rico conjunto nuevo de impresión e impresión las API de administración del sistema. Con [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], algunas de estas mejoras del sistema de impresión también están disponibles para los desarrolladores que crean aplicaciones de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], así como para los que usan código no administrado. La base de esta nueva funcionalidad es el nuevo formato de archivo [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] y la ruta de impresión [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Sobre XPS  
 XPS es un formato de documento electrónico, un formato de archivo de cola de impresión y un lenguaje de descripción de página. Se trata de un formato de documento abierto que usa [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] y otros estándares del sector para crear documentos multiplataforma. XPS simplifica el proceso por el que documentos digitales se creó, compartidos, imprimir, ver y archivados. Para obtener información adicional sobre XPS, consulte [documentos XPS](/windows/desktop/printdocs/documents).  
  
 Varias técnicas para impresión basados en XPS contenido con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se muestran en [impresión de archivos XPS mediante programación](how-to-programmatically-print-xps-files.md). Estos ejemplos le resultarán útil para comprender el contenido de este tema. (Los desarrolladores de código no administrado deben ver la documentación para el [función MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Los desarrolladores de formularios de Windows deben usar la API en el <xref:System.Drawing.Printing> espacio de nombres que no es compatible con las completas [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] ruta de impresión, pero sí admite una ruta de impresión híbrida de GDI a XPS. Consulte el siguiente apartado **Arquitectura de la ruta de impresión**).  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Ruta de impresión XPS  
 La ruta de acceso de impresión de XML Paper Specification (XPS) es un nuevo [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] característica que vuelve a definir cómo se controla la impresión en aplicaciones de Windows. Dado que [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] puede reemplazar un lenguaje de presentación de documento (por ejemplo, RTF), un formato de cola de impresión (como WMF) y un lenguaje de descripción de página (por ejemplo, Postscript o PCL), la nueva ruta de impresión mantiene el formato XPS desde la publicación de aplicaciones para la procesamiento final en el dispositivo o controlador de impresión.  
  
 La ruta de impresión XPS se basa en el modelo de controlador de impresora XPS (XPSDrv), que proporciona varias ventajas para desarrolladores como [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] impresión, soporte de color mejorado y mejorado considerablemente el rendimiento de impresión. (Para obtener más información sobre XPSDrv, vea el [documentación de Windows Driver Kit](/windows-hardware/drivers/).)  
  
 La operación de la cola de impresión de documentos XPS es básicamente igual que en versiones anteriores de Windows. Sin embargo, se ha mejorado para admitir la ruta de impresión XPS aparte de los actuales [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] ruta de impresión. La nueva ruta de impresión usa de forma nativa un archivo de cola de impresión XPS. Mientras que los controladores de impresora de modo de usuario escritos para versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] seguirán funcionando, un controlador de impresora XPS (XPSDrv) es necesario para poder usar la ruta de acceso de impresión de XPS.  
  
 Las ventajas de la ruta de impresión XPS son significativas e incluyen:  
  
- Soporte de impresión [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)].  
  
- Soporte nativo de perfiles de color avanzados, que incluyen 32 bits por canal (bpc), CMYK, colores con nombre, tintas n y soporte nativo de transparencia y degradados.  
  
- Mayor rendimiento de impresión para .NET Framework y [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] aplicaciones basadas en.  
  
- Formato XPS estándar del sector.  
  
 Para escenarios básicos de impresión está disponible con un único punto de entrada para el envío de trabajo, la configuración y la interfaz de usuario una API sencilla e intuitiva. Para los escenarios avanzados se agrega soporte adicional para la personalización de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o sin [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), impresión sincrónica o asincrónica y capacidades de impresión por lotes. Ambas opciones ofrecen soporte de impresión en modo de confianza plena o parcial.  
  
 XPS se diseñó teniendo en cuenta la extensibilidad. Al usar el marco de extensibilidad, características y capacidades pueden agregarse a XPS de manera modular. Las características de extensibilidad incluyen:  
  
- Esquema de impresión. El esquema público se actualiza periódicamente y permite la extensión rápida de las capacidades del dispositivo. (Consulte más abajo **PrintTicket y PrintCapabilities**).  
  
- Canalización de filtros extensible. La canalización de filtro XPS (XPSDrv) del controlador de impresora se diseñó para habilitar la impresión directa y escalable de documentos XPS. Para obtener más información, consulte [controladores de impresora XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Arquitectura de la ruta de impresión  
 Aunque tanto [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y las aplicaciones de .NET Framework admiten XPS, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y usan las aplicaciones de Windows Forms un [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] para XPS conversión con el fin de crear XPS con el formato de contenido para el controlador de impresora XPS (XPSDrv). Estas aplicaciones no son necesarios para usar la ruta de impresión de XPS y puede seguir usando [!INCLUDE[TLA#tla_emf](../../../../includes/tlasharptla-emf-md.md)] en función de impresión. Sin embargo, la mayoría de las características XPS y mejoras solo están disponibles para las aplicaciones que tienen como destino la ruta de acceso de impresión de XPS.  
  
 Para habilitar el uso de las impresoras basadas en XPSDrv por [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y aplicaciones de Windows Forms, el controlador de impresora XPS (XPSDrv) admite la conversión de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] a XPS dar formato. El modelo XPSDrv también proporciona un convertidor para XPS para [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] formato para que [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicaciones pueden imprimir [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] documentos. Para [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones, la conversión de XPS para [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] formato se realiza de forma automática el <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos de la <xref:System.Windows.Xps.XpsDocumentWriter> clase cada vez que la cola de impresión de destino de la operación de escritura no tiene ningún controlador de XPSDrv. (Aplicaciones de Windows Forms no se pueden imprimir [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] documentos.)  
  
 La siguiente ilustración muestra el subsistema de impresión y define las partes proporcionadas por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]y las partes definidas por proveedores de software y hardware:  
  
 ![Captura de pantalla muestra el que sistema de impresión XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Impresión XPS básica  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] define una [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] básica y una avanzada. Para aquellas aplicaciones que no requieren personalización extensa de impresión o acceso a la característica XPS completa compatibilidad con la impresión básica, establezca está disponible. El soporte básico de impresión se expone a través de un control de diálogo de impresión que requiere una configuración mínima y presenta una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] reconocible. Muchas características XPS están disponibles con este modelo simplificado de impresión.  
  
#### <a name="printdialog"></a>PrintDialog  
 El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control proporciona un único punto de entrada para [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y envío de trabajos XPS. Para obtener información sobre la creación de instancias y el uso del control, consulte [Invocar un cuadro de diálogo de impresión](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Impresión XPS avanzada  
 Para acceder al conjunto completo de características XPS, se debe usar la API de impresión avanzada. Varias API relevantes se describen con más detalle a continuación. Para obtener una lista completa de la ruta de impresión XPS API, consulte el <xref:System.Windows.Xps> y <xref:System.Printing> referencias de espacio de nombres.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket y PrintCapabilities  
 El <xref:System.Printing.PrintTicket> y <xref:System.Printing.PrintCapabilities> clases constituyen el fundamento de las características avanzadas de XPS. Ambos tipos de objetos son estructuras con formato [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] de características orientadas a la impresión, como intercalación, impresión a dos caras, grapado, etc. Estas estructuras se definen mediante el esquema de impresión. Un <xref:System.Printing.PrintTicket> indica a una impresora cómo procesar un trabajo de impresión. La clase <xref:System.Printing.PrintCapabilities> define las capacidades de una impresora. Mediante una consulta de las capacidades de una impresora, se puede crear un <xref:System.Printing.PrintTicket> que aproveche al máximo las características compatibles de una impresora. De forma similar, se pueden evitar las características no compatibles.  
  
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
 Un <xref:System.Windows.Xps.XpsDocumentWriter>, con sus el <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos, se utiliza para escribir documentos XPS en un <xref:System.Printing.PrintQueue>. Por ejemplo, el <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> método se usa para generar un documento XPS y <xref:System.Printing.PrintTicket> sincrónicamente. El <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> método se usa para generar un documento XPS y <xref:System.Printing.PrintTicket> asincrónicamente.  
  
 En el siguiente ejemplo se muestra cómo crear un <xref:System.Windows.Xps.XpsDocumentWriter> mediante código.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Los métodos <xref:System.Printing.PrintQueue.AddJob%2A> también proporcionan formas de imprimir. Consulte [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md). para obtener información detallada.  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Ruta de impresión GDI  
 Mientras [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones admiten de forma nativa la ruta de acceso de impresión de XPS, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y aplicaciones de Windows Forms también pueden sacar partido de algunas características XPS. Puede convertir el controlador de impresora XPS (XPSDrv) [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] en función de salida en formato XPS. Para escenarios avanzados, se admite la conversión personalizada de contenido mediante el [convertidor de documentos XPS de Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). De forma similar, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones también pueden generar el [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] ruta de impresión mediante una llamada a uno de los <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> o <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos de la <xref:System.Windows.Xps.XpsDocumentWriter> clase y designar una impresora no XpsDrv como destino de la cola de impresión.  

Para las aplicaciones que no requieren la funcionalidad XPS o soporte técnico, actual [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] ruta de impresión permanece sin cambios.  
  
- Para obtener material de referencia adicional sobre la [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] imprimir la ruta de acceso y las diversas opciones de conversión de XPS, consulte [convertidor de documentos XPS de Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) y [controladores de impresora XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>Modelo de controlador XPSDrv  
 La ruta de impresión XPS mejora la eficacia de la cola de impresión mediante el uso de XPS como el formato nativo de cola de impresión al imprimir en un XPS-habilitado impresora o el controlador. El proceso simplificado de administración de trabajos en cola elimina la necesidad de generar un archivo de cola intermedio, como un archivo de datos [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], antes de poner en cola el documento. A través de la cola de impresión archivos más pequeños, la ruta de impresión XPS puede reducir el tráfico de red y mejorar el rendimiento de impresión.  
  
 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] es un formato cerrado que representa la salida de la aplicación como una serie de llamadas a [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] para la presentación de servicios. A diferencia de [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], el formato de la cola de impresión XPS representa el documento real sin necesidad de más interpretación al generar un controlador de impresora basados en XPS (XPSDrv). Los controladores pueden trabajar directamente con los datos en el formato. Esta capacidad elimina las conversiones de espacio de color y datos que son necesarias cuando se usan archivos [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] y controladores de impresión basados en [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)].  
  
 Tamaños de archivo de cola de impresión suele reducirse cuando utilice documentos de XPS que tienen como destino un controlador de impresora XPS (XPSDrv) en comparación con sus [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] equivalentes; sin embargo, hay excepciones:  
  
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
- [(MXDC) de convertidor de documentos XPS de Microsoft](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
