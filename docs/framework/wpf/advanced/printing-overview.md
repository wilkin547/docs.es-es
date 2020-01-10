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
ms.openlocfilehash: 3f99b0e93e6b16ac66f6869c284c1119ddfc3751
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740308"
---
# <a name="printing-overview"></a>Información general sobre impresión
Con Microsoft .NET Framework, los desarrolladores de aplicaciones que usan Windows Presentation Foundation (WPF) tienen un nuevo conjunto de API de impresión y administración del sistema de impresión. Con Windows Vista, algunas de estas mejoras del sistema de impresión también están disponibles para los desarrolladores que crean [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aplicaciones y desarrolladores que usan código no administrado. La base de esta nueva funcionalidad es el nuevo formato de archivo XML Paper Specification (XPS) y la ruta de impresión XPS.  
  
 En este tema se incluyen las siguientes secciones.  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>Sobre XPS  
 XPS es un formato de documento electrónico, un formato de archivo de cola de impresión y un lenguaje de descripción de página. Es un formato de documento abierto que usa XML, convenciones de empaquetado abierto (OPC) y otros estándares del sector para crear documentos multiplataforma. XPS simplifica el proceso mediante el cual los documentos digitales se crean, comparten, imprimen, ven y archivan. Para obtener información adicional sobre XPS, consulte [documentos XPS](/windows/desktop/printdocs/documents).  
  
 Varias técnicas de impresión de contenido basado en XPS mediante WPF se muestran en [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md). Estos ejemplos le resultarán útil para comprender el contenido de este tema. (Los desarrolladores de código no administrado deben ver la documentación de la [función MXDC_ESCAPE](/windows/desktop/printdocs/mxdc-escape). Windows Forms desarrolladores deben usar la API en el espacio de nombres <xref:System.Drawing.Printing> que no admite la ruta de impresión completa de XPS, pero admite una ruta de impresión híbrida de GDI a XPS. Consulte el siguiente apartado **Arquitectura de la ruta de impresión**).  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>Ruta de impresión XPS  
 La ruta de impresión de XML Paper Specification (XPS) es una nueva característica de Windows que vuelve a definir la forma en que se controla la impresión en aplicaciones de Windows. Dado que XPS puede reemplazar un lenguaje de presentación de documentos (como RTF), un formato de administrador de trabajos de impresión (como WMF) y un lenguaje de descripción de páginas (como PCL o PostScript); la nueva ruta de impresión mantiene el formato XPS de la publicación de la aplicación al procesamiento final en el dispositivo o controlador de impresión.  
  
 La ruta de impresión XPS se basa en el modelo de controlador de impresora XPS (XPSDrv), que proporciona varias ventajas a los desarrolladores, como la impresión de lo que se ve es lo que se obtiene (WYSIWYG), la compatibilidad mejorada con colores y el rendimiento de impresión considerablemente mejorado. (Para obtener más información sobre XPSDrv, consulte la [documentación del kit de controladores de Windows](/windows-hardware/drivers/)).  
  
 La operación del administrador de trabajos de impresión para documentos XPS es esencialmente la misma que en versiones anteriores de Windows. Sin embargo, se ha mejorado para admitir la ruta de impresión XPS además de la ruta de impresión de GDI existente. La nueva ruta de impresión usa de forma nativa un archivo de cola XPS. Aunque los controladores de impresora de modo de usuario escritos para versiones anteriores de Windows seguirán funcionando, es necesario un controlador de impresora XPS (XPSDrv) para poder usar la ruta de impresión XPS.  
  
 Las ventajas de la ruta de impresión XPS son significativas e incluyen:  
  
- Compatibilidad con impresión WYSIWYG  
  
- Soporte nativo de perfiles de color avanzados, que incluyen 32 bits por canal (bpc), CMYK, colores con nombre, tintas n y soporte nativo de transparencia y degradados.  
  
- Rendimiento de impresión mejorado para aplicaciones basadas en .NET Framework y Win32.  
  
- Formato XPS estándar del sector.  
  
 En el caso de los escenarios de impresión básicos, hay disponible una API sencilla e intuitiva con un único punto de entrada para la interfaz de usuario, la configuración y el envío de trabajos. Para los escenarios avanzados se agrega soporte adicional para la personalización de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] (o sin [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]), impresión sincrónica o asincrónica y capacidades de impresión por lotes. Ambas opciones ofrecen soporte de impresión en modo de confianza plena o parcial.  
  
 XPS se diseñó teniendo en cuenta la extensibilidad. Con el marco de extensibilidad, se pueden agregar características y capacidades a XPS de una manera modular. Las características de extensibilidad incluyen:  
  
- Esquema de impresión. El esquema público se actualiza periódicamente y permite la extensión rápida de las capacidades del dispositivo. (Consulte más abajo **PrintTicket y PrintCapabilities**).  
  
- Canalización de filtros extensible. La canalización de filtros del controlador de impresora XPS (XPSDrv) se diseñó para habilitar la impresión directa y escalable de documentos XPS. Para obtener más información, consulte [controladores de impresora XPSDrv](/windows-hardware/drivers/print/xpsdrv-printer-drivers). 
  
### <a name="print-path-architecture"></a>Arquitectura de la ruta de impresión  
 Aunque tanto las aplicaciones de Win32 como .NET Framework admiten XPS, Win32 y las aplicaciones de Windows Forms usan una conversión de GDI a XPS para crear contenido con formato XPS para el controlador de impresora XPS (XPSDrv). Estas aplicaciones no necesitan usar la ruta de impresión XPS y pueden seguir utilizando la impresión basada en metarchivo mejorado (EMF). Sin embargo, la mayoría de las características y mejoras de XPS solo están disponibles para las aplicaciones que tienen como destino la ruta de impresión XPS.  
  
 Para habilitar el uso de las impresoras basadas en XPSDrv por parte de las aplicaciones de Win32 y Windows Forms, el controlador de impresora XPS (XPSDrv) admite la conversión de GDI al formato XPS. El modelo XPSDrv también proporciona un convertidor para el formato XPS a GDI, de modo que las aplicaciones Win32 puedan imprimir documentos XPS. En el caso de las aplicaciones de WPF, la conversión del formato XPS a GDI se realiza automáticamente mediante los métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la clase <xref:System.Windows.Xps.XpsDocumentWriter> cada vez que la cola de impresión de destino de la operación de escritura no tiene un controlador XPSDrv. (Windows Forms aplicaciones no pueden imprimir documentos XPS).  
  
 En la ilustración siguiente se muestra el subsistema de impresión y se definen las partes proporcionadas por Microsoft y las partes definidas por los proveedores de software y hardware:  
  
 ![Captura de pantalla que muestra el sistema de impresión XPS.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>Impresión XPS básica  
 WPF define una API básica y avanzada. En el caso de las aplicaciones que no requieren una personalización de impresión amplia o el acceso al conjunto completo de características de XPS, está disponible el soporte básico de impresión. El soporte básico de impresión se expone a través de un control de diálogo de impresión que requiere una configuración mínima y presenta una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] reconocible. Muchas características de XPS están disponibles con este modelo de impresión simplificado.  
  
#### <a name="printdialog"></a>PrintDialog  
 El control <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> proporciona un único punto de entrada para el envío de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y trabajo XPS. Para obtener información sobre la creación de instancias y el uso del control, consulte [Invocar un cuadro de diálogo de impresión](how-to-invoke-a-print-dialog.md).  
  
### <a name="advanced-xps-printing"></a>Impresión XPS avanzada  
 Para tener acceso al conjunto completo de características de XPS, se debe usar la API de impresión avanzada. A continuación se describen con más detalle varias API pertinentes. Para obtener una lista completa de las API de ruta de impresión XPS, consulte las referencias de espacio de nombres <xref:System.Windows.Xps> y <xref:System.Printing>.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket y PrintCapabilities  
 Las clases <xref:System.Printing.PrintTicket> y <xref:System.Printing.PrintCapabilities> son la base de las características avanzadas de XPS. Ambos tipos de objetos son estructuras con formato XML de características orientadas a la impresión, como intercalación, impresión a dos caras, grapado, etc. Estas estructuras se definen mediante el esquema de impresión. Un <xref:System.Printing.PrintTicket> indica a una impresora cómo procesar un trabajo de impresión. La clase <xref:System.Printing.PrintCapabilities> define las capacidades de una impresora. Mediante una consulta de las capacidades de una impresora, se puede crear un <xref:System.Printing.PrintTicket> que aproveche al máximo las características compatibles de una impresora. De forma similar, se pueden evitar las características no compatibles.  
  
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
 Un <xref:System.Windows.Xps.XpsDocumentWriter>, con sus diversos métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>, se usa para escribir documentos XPS en un <xref:System.Printing.PrintQueue>. Por ejemplo, el método <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> se usa para generar un documento XPS y <xref:System.Printing.PrintTicket> de forma sincrónica. El método <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> se usa para generar un documento XPS y <xref:System.Printing.PrintTicket> de forma asincrónica.  
  
 En el siguiente ejemplo se muestra cómo crear un <xref:System.Windows.Xps.XpsDocumentWriter> mediante código.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 Los métodos <xref:System.Printing.PrintQueue.AddJob%2A> también proporcionan formas de imprimir. Consulte [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md). para obtener información detallada.  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>Ruta de impresión GDI  
 Aunque las aplicaciones de WPF admiten de forma nativa la ruta de impresión XPS, las aplicaciones Win32 y Windows Forms también pueden aprovechar algunas características de XPS. El controlador de impresora XPS (XPSDrv) puede convertir la salida basada en GDI al formato XPS. En escenarios avanzados, se admite la conversión personalizada de contenido mediante el [convertidor de documentos XPS de Microsoft (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-). Del mismo modo, las aplicaciones WPF también pueden generar resultados en la ruta de impresión GDI llamando a uno de los métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> o <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la clase <xref:System.Windows.Xps.XpsDocumentWriter> y designando una impresora que no sea XpsDrv como cola de impresión de destino.  

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
  
- **Compatibilidad con gráficos avanzados**. La compatibilidad nativa con la transparencia y las primitivas de degradado evita la rasterización del contenido en el documento XPS.  
  
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
