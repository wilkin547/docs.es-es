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
ms.openlocfilehash: 902d51341850b5245b9fa6410b1954b2ab373bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187211"
---
# <a name="printing-overview"></a>Información general sobre impresión
Con Microsoft .NET Framework, los desarrolladores de aplicaciones que usan Windows Presentation Foundation (WPF) tienen un nuevo conjunto enriquecido de API de administración del sistema de impresión e impresión. Con Windows Vista, algunas de estas mejoras del sistema de impresión también están disponibles para los desarrolladores que crean aplicaciones de Windows Forms y los desarrolladores que usan código no administrado. El núcleo de esta nueva funcionalidad es el nuevo formato de archivo XML Paper Specification (XPS) y la ruta de impresión XPS.  
  
 Este tema contiene las siguientes secciones.  
  
<a name="introduction_to_XPS"></a>
## <a name="about-xps"></a>Sobre XPS  
 XPS es un formato de documento electrónico, un formato de archivo de cola de impresión y un idioma de descripción de página. Es un formato de documento abierto que utiliza XML, Open Packaging Conventions (OPC) y otros estándares de la industria para crear documentos multiplataforma. XPS simplifica el proceso mediante el cual se crean, comparten, imprimen, visualizan y archivan documentos digitales. Para obtener información adicional sobre XPS, consulte [Documentos XPS](/windows/desktop/printdocs/documents).  
  
 En [Impresión mediante programación](how-to-programmatically-print-xps-files.md)de archivos XPS se muestran varias técnicas para imprimir contenido basado en XPS mediante WPF. Estos ejemplos le resultarán útil para comprender el contenido de este tema. (Los desarrolladores de código no administrado deben ver la documentación de la [función MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Los desarrolladores de Windows <xref:System.Drawing.Printing> Forms deben usar la API en el espacio de nombres que no admite la ruta de acceso de impresión XPS completa, pero sí una ruta de acceso de impresión gDI a XPS híbrida. Consulte el siguiente apartado **Arquitectura de la ruta de impresión**).  
  
<a name="XPS_print_path_intro"></a>
## <a name="xps-print-path"></a>Ruta de impresión XPS  
 La ruta de impresión XML Paper Specification (XPS) es una nueva característica de Windows que redefine cómo se gestiona la impresión en aplicaciones Windows. Dado que XPS puede reemplazar un lenguaje de presentación de documentos (como RTF), un formato de cola de impresión (como WMF) y un lenguaje de descripción de página (como PCL o Postscript); la nueva ruta de impresión mantiene el formato XPS desde la publicación de la aplicación hasta el procesamiento final en el controlador o dispositivo de impresión.  
  
 La ruta de impresión XPS se basa en el modelo de controlador de impresora XPS (XPSDrv), que proporciona varias ventajas para los desarrolladores, como la impresión de "lo que ves es lo que obtienes" (WYSIWYG), la compatibilidad mejorada con color y el rendimiento de impresión significativamente mejorado. (Para obtener más información sobre XPSDrv, consulte la documentación del Kit de [controladores](/windows-hardware/drivers/)de Windows .)  
  
 El funcionamiento de la cola de impresión para documentos XPS es esencialmente el mismo que en versiones anteriores de Windows. Sin embargo, se ha mejorado para admitir la ruta de impresión XPS además de la ruta de impresión GDI existente. La nueva ruta de impresión consume de forma nativa un archivo de cola de impresión XPS. Mientras que los controladores de impresora en modo de usuario escritos para versiones anteriores de Windows seguirán funcionando, se requiere un controlador de impresora XPS (XPSDrv) para utilizar la ruta de impresión XPS.  
  
 Las ventajas de la ruta de impresión XPS son significativas e incluyen:  
  
- Soporte de impresión WYSIWYG  
  
- Soporte nativo de perfiles de color avanzados, que incluyen 32 bits por canal (bpc), CMYK, colores con nombre, tintas n y soporte nativo de transparencia y degradados.  
  
- Se ha mejorado el rendimiento de impresión para las aplicaciones basadas en .NET Framework y Win32.  
  
- Formato XPS estándar de la industria.  
  
 Para escenarios de impresión básicos, una API simple e intuitiva está disponible con un único punto de entrada para la interfaz de usuario, la configuración y el envío de trabajos. Para los escenarios avanzados se agrega soporte adicional para la personalización de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o sin [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), impresión sincrónica o asincrónica y capacidades de impresión por lotes. Ambas opciones ofrecen soporte de impresión en modo de confianza plena o parcial.  
  
 XPS fue diseñado teniendo en cuenta la extensibilidad. Mediante el uso del marco de extensibilidad, las características y capacidades se pueden agregar a XPS de una manera modular. Las características de extensibilidad incluyen:  
  
- Esquema de impresión. El esquema público se actualiza periódicamente y permite la extensión rápida de las capacidades del dispositivo. (Consulte más abajo **PrintTicket y PrintCapabilities**).  
  
- Canalización de filtros extensible. La canalización de filtro del controlador de impresora XPS (XPSDrv) se diseñó para permitir la impresión directa y escalable de documentos XPS. Para obtener más información, consulte Controladores de [impresora XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers).
  
### <a name="print-path-architecture"></a>Arquitectura de la ruta de impresión  
 Aunque las aplicaciones Win32 y .NET Framework admiten XPS, las aplicaciones Win32 y Windows Forms utilizan una conversión de GDI a XPS para crear contenido con formato XPS para el controlador de impresora XPS (XPSDrv). Estas aplicaciones no son necesarias para utilizar la ruta de impresión XPS y pueden seguir utilizando la impresión basada en metarchivo mejorado (EMF). Sin embargo, la mayoría de las características y mejoras de XPS solo están disponibles para las aplicaciones destinadas a la ruta de impresión XPS.  
  
 Para habilitar el uso de impresoras basadas en XPSDrv mediante aplicaciones Win32 y Windows Forms, el controlador de impresora XPS (XPSDrv) admite la conversión de GDI al formato XPS. El modelo XPSDrv también proporciona un convertidor para XPS a formato GDI para que las aplicaciones Win32 puedan imprimir documentos XPS. Para las aplicaciones WPFWPF, la conversión de <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> XPS al formato GDI se realiza automáticamente mediante los métodos y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la <xref:System.Windows.Xps.XpsDocumentWriter> clase siempre que la cola de impresión de destino de la operación de escritura no tenga un controlador XPSDrv. (Las aplicaciones de Formularios Windows Forms no pueden imprimir documentos XPS.)  
  
 La siguiente ilustración muestra el subsistema de impresión y define las partes proporcionadas por Microsoft y las partes definidas por los proveedores de software y hardware:  
  
 ![La captura de pantalla muestra el sistema de impresión XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Impresión XPS básica  
 WPFWPF define una API básica y avanzada. Para aquellas aplicaciones que no requieren una amplia personalización de impresión o acceso al conjunto completo de características XPS, el soporte de impresión básico está disponible. El soporte básico de impresión se expone a través de un control de diálogo de impresión que requiere una configuración mínima y presenta una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] reconocible. Muchas funciones XPS están disponibles utilizando este modelo de impresión simplificado.  
  
#### <a name="printdialog"></a>PrintDialog  
 El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control proporciona un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]único punto de entrada para , configuración y envío de trabajos XPS. Para obtener información sobre la creación de instancias y el uso del control, consulte [Invocar un cuadro de diálogo de impresión](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Impresión XPS avanzada  
 Para acceder al conjunto completo de características de XPS, se debe utilizar la API de impresión avanzada. A continuación se describen varias API relevantes con mayor detalle. Para obtener una lista completa de las <xref:System.Windows.Xps> API <xref:System.Printing> de ruta de impresión XPS, consulte las referencias de espacio de nombres y.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket y PrintCapabilities  
 Las <xref:System.Printing.PrintTicket> <xref:System.Printing.PrintCapabilities> clases y son la base de las características avanzadas de XPS. Ambos tipos de objetos son estructuras con formato XML de características orientadas a la impresión, como la intercalación, la impresión a dos caras, el grapado, etc. Estas estructuras se definen mediante el esquema de impresión. Un <xref:System.Printing.PrintTicket> indica a una impresora cómo procesar un trabajo de impresión. La clase <xref:System.Printing.PrintCapabilities> define las capacidades de una impresora. Mediante una consulta de las capacidades de una impresora, se puede crear un <xref:System.Printing.PrintTicket> que aproveche al máximo las características compatibles de una impresora. De forma similar, se pueden evitar las características no compatibles.  
  
 En el ejemplo siguiente se muestra cómo consultar las <xref:System.Printing.PrintCapabilities> de una impresora y crear un <xref:System.Printing.PrintTicket> mediante código.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer y PrintQueue  
 La clase <xref:System.Printing.PrintServer> representa un servidor de impresión de red y la clase <xref:System.Printing.PrintQueue> representa una impresora y la cola de trabajos de salida asociados a él. Juntos, estas API permiten la administración avanzada de los trabajos de impresión de un servidor. Un <xref:System.Printing.PrintServer>, o una de sus clases derivadas, se usa para administrar un <xref:System.Printing.PrintQueue>. El método <xref:System.Printing.PrintQueue.AddJob%2A> se usa para insertar un nuevo trabajo de impresión en la cola.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Printing.LocalPrintServer> y tener acceso a su <xref:System.Printing.PrintQueue> predeterminado mediante código.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 Un <xref:System.Windows.Xps.XpsDocumentWriter>, con <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> sus <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> muchos los métodos y, <xref:System.Printing.PrintQueue>se utiliza para escribir documentos XPS en un archivo . Por ejemplo, <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> el método se utiliza para <xref:System.Printing.PrintTicket> generar un documento XPS y sincrónicamente. El <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> método se utiliza para generar <xref:System.Printing.PrintTicket> un documento XPS y de forma asincrónica.  
  
 En el siguiente ejemplo se muestra cómo crear un <xref:System.Windows.Xps.XpsDocumentWriter> mediante código.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Los métodos <xref:System.Printing.PrintQueue.AddJob%2A> también proporcionan formas de imprimir. Consulte [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md). para obtener más detalles.  
  
<a name="GDI_Print_Path_intro"></a>
## <a name="gdi-print-path"></a>Ruta de impresión GDI  
 Aunque las aplicaciones WPF admiten de forma nativa la ruta de acceso de impresión XPS, las aplicaciones Win32 y Windows Forms también pueden aprovechar algunas características de XPS. El controlador de impresora XPS (XPSDrv) puede convertir la salida basada en GDI al formato XPS. Para escenarios avanzados, se admite la conversión personalizada de contenido mediante [Microsoft XPS Document Converter (MXDC).](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) De forma similar, las aplicaciones WPFWPF también pueden <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> generar <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> en <xref:System.Windows.Xps.XpsDocumentWriter> la ruta de acceso de impresión DeSG llamando a uno de los métodos o de la clase y designando una impresora que no sea XpsDrv como la cola de impresión de destino.  

Para las aplicaciones que no requieren funcionalidad o compatibilidad con XPS, la ruta de impresión GDI actual permanece sin cambios.  
  
- Para obtener material de referencia adicional en la ruta de impresión GDI y las diversas opciones de conversión de XPS, consulte [Microsoft XPS Document Converter (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) y [XPSDrv Printer Drivers](/windows-hardware/drivers/print/xpsdrv-printer-drivers).  
  
<a name="XPS_Driver_Model_intro"></a>
## <a name="xpsdrv-driver-model"></a>Modelo de controlador XPSDrv  
 La ruta de impresión XPS mejora la eficiencia de la cola al utilizar XPS como formato de cola de impresión nativa al imprimir en una impresora o controlador habilitado para XPS. El proceso de cola simplificada elimina la necesidad de generar un archivo de cola intermedia, como un archivo de datos EMF, antes de que se spoole el documento. A través de tamaños de archivo de cola de impresión más pequeños, la ruta de impresión XPS puede reducir el tráfico de red y mejorar el rendimiento de impresión.  
  
 EMF es un formato cerrado que representa la salida de la aplicación como una serie de llamadas a GDI para los servicios de representación. A diferencia de EMF, el formato de cola XPS representa el documento real sin necesidad de interpretación adicional cuando se envía a un controlador de impresora basado en XPS (XPSDrv). Los controladores pueden trabajar directamente con los datos en el formato. Esta capacidad elimina las conversiones de datos y espacio de color necesarias cuando se utilizan archivos EMF y controladores de impresión basados en GDI.  
  
 Los tamaños de archivo de cola de impresión normalmente se reducen cuando se utilizan documentos XPS destinados a un controlador de impresora XPS (XPSDrv) en comparación con sus equivalentes EMF; sin embargo, hay excepciones:  
  
- Un gráfico vectorial muy complejo, con varias capas o escrito de forma ineficaz puede ser mayor que una versión de mapa de bits del mismo gráfico.  
  
- Para la presentación en pantalla, los archivos XPS insertan fuentes del dispositivo y del equipo, mientras que los archivos de cola de impresión GDI no insertan fuentes de dispositivo. Sin embargo, ambos tipos de fuentes se incluyen en un subconjunto (ver abajo) y los controladores de impresora pueden quitar las fuentes de dispositivo antes de transmitir el archivo a la impresora.  
  
 La reducción del tamaño de cola de impresión se consigue a través de varios mecanismos:  
  
- **Creación de un subconjunto de fuentes**. Solo los caracteres utilizados en el documento real se almacenan en el archivo XPS.  
  
- **Compatibilidad con gráficos avanzados**. La compatibilidad nativa con primitivas de transparencia y degradado evita la rasterización del contenido en el documento XPS.  
  
- **Identificación de recursos comunes**. Los recursos que se usan varias veces (como una imagen que representa un logotipo corporativo) se tratan como recursos compartidos y se cargan solamente una vez.  
  
- **Compresión ZIP**. Todos los documentos XPS utilizan compresión ZIP.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [Temas de información](printing-how-to-topics.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Documentos XPS](/windows/desktop/printdocs/documents)
- [Almacenamiento y serialización de documentos](document-serialization-and-storage.md)
- [Convertidor de documentos de Microsoft XPS (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
