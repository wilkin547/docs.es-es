---
title: Procedimiento Imprimir archivos XPS mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: 6642fad7d20e60a8b92e5860b763511f4fc0be72
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169179"
---
# <a name="how-to-programmatically-print-xps-files"></a>Procedimiento Imprimir archivos XPS mediante programación
Puede <xref:System.Printing.PrintQueue.AddJob%2A> usar una sobrecarga del método para imprimir [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivos sin abrir <xref:System.Windows.Controls.PrintDialog> o, en principio, ninguno [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .  
  
 También puede imprimir [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivos con los muchos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> métodos y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de <xref:System.Windows.Xps.XpsDocumentWriter>. Para información sobre esto, vea [Imprimir un documento XPS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90)).  
  
 Otra forma de imprimir [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] es usar los <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> métodos o <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> del <xref:System.Windows.Controls.PrintDialog> control. Vea [Invocar un cuadro de diálogo de impresión](how-to-invoke-a-print-dialog.md).  
  
## <a name="example"></a>Ejemplo  
 Los pasos principales para usar el método de tres <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> parámetros son los siguientes. En el ejemplo siguiente se proporciona información detallada.  
  
1. Determinar si la impresora es una impresora XPSDrv. (Vea [Introducción a la impresión](printing-overview.md) para obtener más información sobre XPSDrv).  
  
2. Si la impresora no es una impresora XPSDrv, establezca el apartamento del subproceso en un subproceso único.  
  
3. Crear una instancia de un servidor de impresión y un objeto de cola de impresión.  
  
4. Llame al método, especificando un nombre de trabajo, el archivo que se va a imprimir <xref:System.Boolean> y una marca que indique si la impresora es una impresora XPSDrv.  
  
 En el ejemplo siguiente se muestra realizar la impresión por lotes de todos los archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] en un directorio. Aunque la aplicación pide al usuario que especifique el directorio, el método de tres parámetros <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> no requiere un. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Se puede utilizar en cualquier ruta de acceso del código donde haya un nombre de archivo [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] y la ruta de acceso que pueda pasar a ella.  
  
 La sobrecarga de tres <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> parámetros de <xref:System.Printing.PrintQueue.AddJob%2A> debe ejecutarse en un apartamento de subproceso <xref:System.Boolean> único siempre `false`que el parámetro sea, que debe ser cuando se usa una impresora que no es XPSDrv. Sin embargo, el estado de Apartamento predeterminado para .NET es de varios subprocesos. Este es el valor predeterminado, ya que el en el ejemplo se da por hecho que estamos antes una impresora que no es XPSDrv.  
  
 Existen dos maneras de cambiar el valor predeterminado. Una <xref:System.STAThreadAttribute> forma consiste en agregar simplemente (es decir, "`[System.STAThreadAttribute()]`") justo encima de la primera línea del método de `Main` la aplicación (normalmente "`static void Main(string[] args)`"). Sin embargo, muchas aplicaciones requieren que `Main` el método tenga un estado de apartamento de varios subprocesos, por lo que hay un segundo método: <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> Coloque la llamada en en un subproceso independiente cuyo <xref:System.Threading.ApartmentState.STA> estado <xref:System.Threading.Thread.SetApartmentState%2A>de apartamento esté establecido en con. El ejemplo siguiente utiliza esta segunda técnica.  
  
 En consecuencia, el ejemplo comienza creando una instancia <xref:System.Threading.Thread> de un objeto y pasándole un método **PrintXPS** como <xref:System.Threading.ThreadStart> parámetro. (El método **PrintXPS** se define más adelante en el ejemplo). A continuación, el subproceso se establece en un apartamento de subproceso único. El único código restante del método `Main` inicia el nuevo subproceso.  
  
 El grueso del ejemplo está en el método `static`**BatchXPSPrinter.PrintXPS**. Después de crear una cola y un servidor de impresión, el método solicita al usuario un directorio que contenga archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]. Después de validar la existencia del directorio y la presencia de \*archivos. XPS en él, el método agrega cada uno de estos archivos a la cola de impresión. `false` En el ejemplo se da por supuesto que la impresora no es XPSDrv, por lo que pasamos al último <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> parámetro del método. Por este motivo, el método validará la marcación [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] en el archivo antes de intentar convertirla en un lenguaje de descripción de la página de la impresora. Si se produce un error validación, se produce una excepción. El código de ejemplo detectará la excepción, la notificará al usuario y, a continuación, continuará con el proceso en el siguiente archivo [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Si está utilizando una impresora XPSDrv, puede establecer el parámetro final en `true`. En ese caso, puesto que [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] es el idioma de descripción de la página de la impresora, el método enviará el archivo a la impresora sin validarlo o convertirlo en otro idioma de descripción de página. Si no está seguro en tiempo de diseño si la aplicación va a usar una impresora XPSDrv, puede modificar la aplicación para que lea la propiedad y <xref:System.Printing.PrintQueue.IsXpsDevice%2A> la bifurcación según lo que encuentre.  
  
 Dado que inicialmente habrá pocas impresoras XPSDrv disponibles inmediatamente después de la versión de [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] y Microsoft .NET Framework, puede que tenga que disfrazar una impresora que no sea XPSDrv como impresora XPSDrv. Para ello, agregue Pipelineconfig.xml a la lista de archivos en la siguiente clave del registro del equipo que ejecuta la aplicación:  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles  
  
 donde  *\<PseudoXPSPrinter >* es cualquier cola de impresión. El equipo debe reiniciarse a continuación.  
  
 Esta disfraz le permitirá pasar `true` como el parámetro final de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> sin producir una excepción, pero como  *\<PseudoXPSPrinter >* no es realmente una impresora XPSDrv, solo se imprimirá el elemento no utilizado.  
  
 **Nota:** Para simplificar, en el ejemplo anterior se usa la \*presencia de una extensión. XPS como prueba de que [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]un archivo es. Sin embargo, los archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] no tienen necesariamente esta extensión. [isXPS.exe (Herramienta isXPS Conformance)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) es una manera de probar la validez de un archivo para [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
## <a name="see-also"></a>Vea también

- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.AddJob%2A>
- <xref:System.Threading.ApartmentState>
- <xref:System.STAThreadAttribute>
- [Documentos XPS](/windows/desktop/printdocs/documents)
- [Imprimir un documento XPS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))
- [Subprocesamiento administrado y no administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [isXPS.exe (Herramienta isXPS Conformance)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
