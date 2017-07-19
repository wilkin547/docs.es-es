---
title: "C&#243;mo: Imprimir mediante programaci&#243;n archivos XPS | Microsoft Docs"
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
  - "imprimir archivos XPS mediante programación"
  - "XPS (archivos), imprimir mediante programación"
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Imprimir mediante programaci&#243;n archivos XPS
Puede utilizar una sobrecarga del método <xref:System.Printing.PrintQueue.AddJob%2A> para imprimir archivos [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] sin abrir un control <xref:System.Windows.Controls.PrintDialog> o, en principio, ninguna [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] en absoluto.  
  
 También puede imprimir archivos [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] usando los diversos métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la clase <xref:System.Windows.Xps.XpsDocumentWriter>.  Para ver más información sobre este tema, [Printing an XPS Document](http://msdn.microsoft.com/es-es/849555c8-0c4e-48c0-86bc-a5494c69b36c).  
  
 Otra manera de imprimir [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] es utilizar los métodos <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> o <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> del control <xref:System.Windows.Controls.PrintDialog>.  Vea [Invocar un cuadro de diálogo de impresión](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md).  
  
## Ejemplo  
 Los pasos principales para utilizar el método de tres parámetros <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> son los siguientes.  El ejemplo siguiente proporciona información detallada.  
  
1.  Determine si la impresora es una impresora XPSDrv.  \(Vea [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md) para obtener más información sobre XPSDrv.\)  
  
2.  Si la impresora no es una impresora XPSDrv, establezca el estado de subprocesamiento en un subproceso único.  
  
3.  Cree una instancia de un servidor de impresión e imprima el objeto de cola.  
  
4.  Llame al método especificando un nombre de trabajo, el archivo que se va a imprimir y un marcador <xref:System.Boolean> que indique si la impresora es una impresora XPSDrv o no.  
  
 El ejemplo siguiente muestra cómo imprimir por lotes todos los archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] de un directorio.  Aunque la aplicación pide al usuario que especifique el directorio, el método de tres parámetros <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> no requiere una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Se puede utilizar en cualquier ruta de acceso de código donde tenga un nombre de archivo [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] y una ruta de acceso que puede pasarle.  
  
 La sobrecarga <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> de tres parámetros de <xref:System.Printing.PrintQueue.AddJob%2A> se debe ejecutar en un subprocesamiento controlado simple cada vez que el parámetro <xref:System.Boolean> sea `false`, que debe ser cuando se utilice una impresora que no sea XPSDrv.  Sin embargo, el estado de subprocesamiento predeterminado para [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] es de varios subprocesos.  Esta opción predeterminada se debe invertir, dado que el ejemplo asume que se trata de una impresora que no es XPSDrv.  
  
 Hay dos maneras de cambiar el valor predeterminado.  Una consiste en agregar simplemente <xref:System.STAThreadAttribute> \(es decir, "`[System.STAThreadAttribute()]`"\) inmediatamente encima de la primera línea del método `Main` de la aplicación \(habitualmente, "`static void Main(string[] args)`"\).  Sin embargo, muchas aplicaciones requieren que el método `Main` tenga un estado subprocesamiento múltiple, así que hay un segundo método: coloque la llamada a <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> en un subproceso independiente cuyo estado subprocesamiento esté establecido en <xref:System.Threading.ApartmentState> con <xref:System.Threading.Thread.SetApartmentState%2A>.  En el ejemplo siguiente se utiliza esta segunda técnica.  
  
 Consecuentemente, el ejemplo comienza creando una instancia de un objeto <xref:System.Threading.Thread> y pasándole un método **PrintXPS** como parámetro <xref:System.Threading.ThreadStart>.  \(El método **PrintXPS** se define más adelante en el ejemplo.\) A continuación, el subproceso se establece en un subprocesamiento controlado simple.  El único código restante del método `Main` inicia el nuevo subproceso.  
  
 La parte interesante del ejemplo está en el método `static` **BatchXPSPrinter.PrintXPS**.  Después de crear un servidor y una cola de impresión, el método pide al usuario un directorio que contenga los archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  Después de validar la existencia del directorio y la presencia en él de archivos \*.xps, el método agrega cada uno de los archivos a la cola de impresión.  En el ejemplo se supone que la impresora no es XPSDrv, por lo que estamos pasando `false` al último parámetro del método <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>.  Por esta razón, el método validará el marcado [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] del archivo antes de intentar convertirlo al lenguaje de descripción de páginas de la impresora.  Si se produce un error de validación, se genera una excepción.  El código de ejemplo detectará la excepción, se la notificará al usuario y, a continuación, continuará procesando el archivo [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] siguiente.  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Si está utilizando una impresora XPSDrv, puede establecer el parámetro final en `true`.  En ese caso, dado que [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] es el lenguaje de descripción de páginas de la impresora, el método enviará el archivo a la impresora sin validarlo ni convertirlo a otro lenguaje de descripción de páginas.  Si no sabe con seguridad en tiempo de diseño si la aplicación utilizará una impresora XPSDrv, puede modificar la aplicación para que lea la propiedad <xref:System.Printing.PrintQueue.IsXpsDevice%2A> y se bifurque en función de lo que encuentre.  
  
 Dado que inicialmente habrá pocas impresoras XPSDrv disponibles inmediatamente después del lanzamiento de [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] y [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], quizá deba hacer que las impresoras  que no sean XPSDrv aparezcan como XPSDrv.  Para ello, agregue Pipelineconfig.xml a la lista de archivos de la siguiente clave del Registro del equipo donde se ejecute la aplicación:  
  
 HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Print\\Environments\\Windows NT x86\\Drivers\\Version\-3\\*\<PseudoXPSPrinter\>*\\DependentFiles  
  
 donde *\<PseudoXPSPrinter\>* es cualquier cola de impresión.  A continuación se debe reiniciar el equipo.  
  
 Este camuflaje le permitirá pasar `true` como último parámetro final de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> sin producir una excepción, pero dado que *\<PseudoXPSPrinter\>* no es realmente una impresora XPSDrv, sólo se imprimirá basura.  
  
 **Nota** Para simplificar, el ejemplo anterior utiliza la presencia de una extensión \*.xps como prueba de que un archivo es [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  Sin embargo, los archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] no tienen necesariamente esta extensión.  [isXPS.exe \(Herramienta isXPS Conformance\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md) es un medio de probar la validez [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] de un archivo.  
  
## Vea también  
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.AddJob%2A>   
 <xref:System.Threading.ApartmentState>   
 <xref:System.STAThreadAttribute>   
 [XPS](http://www.microsoft.com/xps)   
 [Printing an XPS Document](http://msdn.microsoft.com/es-es/849555c8-0c4e-48c0-86bc-a5494c69b36c)   
 [Managed and Unmanaged Threading](http://msdn.microsoft.com/es-es/db425c20-4b2f-4433-bf96-76071c7881e5)   
 [isXPS.exe \(Herramienta isXPS Conformance\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)