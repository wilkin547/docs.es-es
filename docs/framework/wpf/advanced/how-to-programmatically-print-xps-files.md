---
title: 'Cómo: Imprimir mediante programación archivos XPS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: 25c0b34bd33bee626df14c8dbedce0b82e895b58
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532821"
---
# <a name="how-to-programmatically-print-xps-files"></a>Cómo: Imprimir mediante programación archivos XPS
Puede usar una sobrecarga de la <xref:System.Printing.PrintQueue.AddJob%2A> método imprimir [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivos sin tener que abrir una <xref:System.Windows.Controls.PrintDialog> o, en principio, cualquier [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] en absoluto.  
  
 También puede imprimir [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivos de los numerosos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos de la <xref:System.Windows.Xps.XpsDocumentWriter>. Para información sobre esto, vea [Imprimir un documento XPS](https://msdn.microsoft.com/library/849555c8-0c4e-48c0-86bc-a5494c69b36c(v=vs.90)).  
  
 Otra forma de impresión [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] consiste en usar el <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> o <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> métodos de la <xref:System.Windows.Controls.PrintDialog> control. Vea [Invocar un cuadro de diálogo de impresión](how-to-invoke-a-print-dialog.md).  
  
## <a name="example"></a>Ejemplo  
 Los pasos principales para utilizar los tres parámetros <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> método son los siguientes. En el ejemplo siguiente se proporciona información detallada.  
  
1.  Determinar si la impresora es una impresora XPSDrv. (Vea [Introducción a la impresión](printing-overview.md) para obtener más información sobre XPSDrv).  
  
2.  Si la impresora no es una impresora XPSDrv, establezca el apartamento del subproceso en un subproceso único.  
  
3.  Crear una instancia de un servidor de impresión y un objeto de cola de impresión.  
  
4.  Llame al método, especifique un nombre de trabajo, el archivo que se imprimen y un <xref:System.Boolean> marca que indica si la impresora es una impresora XPSDrv o no.  
  
 En el ejemplo siguiente se muestra realizar la impresión por lotes de todos los archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] en un directorio. Aunque la aplicación pide al usuario que especifique el directorio, los tres parámetros <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> método no requiere un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Se puede utilizar en cualquier ruta de acceso del código donde haya un nombre de archivo [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] y la ruta de acceso que pueda pasar a ella.  
  
 Los tres parámetros <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> sobrecarga de <xref:System.Printing.PrintQueue.AddJob%2A> debe ejecutar en un apartamento de subproceso único cada vez que el <xref:System.Boolean> parámetro es `false`, que debe ser cuando se utiliza una impresora no XPSDrv. Sin embargo, el estado del apartamento predeterminado de [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] es de varios subprocesos. Este es el valor predeterminado, ya que el en el ejemplo se da por hecho que estamos antes una impresora que no es XPSDrv.  
  
 Existen dos maneras de cambiar el valor predeterminado. Es una manera de agregar simplemente la <xref:System.STAThreadAttribute> (es decir, "`[System.STAThreadAttribute()]`") justo encima de la primera línea de la aplicación `Main` método (normalmente "`static void Main(string[] args)`"). Sin embargo, muchas aplicaciones requieren que el `Main` método tienen un estado de apartamento multiproceso, por lo que hay un segundo método: colocar la llamada a <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> en un subproceso independiente cuyo estado de apartamento se establece en <xref:System.Threading.ApartmentState.STA> con <xref:System.Threading.Thread.SetApartmentState%2A>. El ejemplo siguiente utiliza esta segunda técnica.  
  
 En consecuencia, el ejemplo comienza creando una instancia de un <xref:System.Threading.Thread> objeto y pasándole un **PrintXPS** método como el <xref:System.Threading.ThreadStart> parámetro. (El método **PrintXPS** se define más adelante en el ejemplo). A continuación, el subproceso se establece en un apartamento de subproceso único. El único código restante del método `Main` inicia el nuevo subproceso.  
  
 El grueso del ejemplo está en el método `static`**BatchXPSPrinter.PrintXPS**. Después de crear una cola y un servidor de impresión, el método solicita al usuario un directorio que contenga archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]. Después de comprobar la existencia del directorio y la presencia de \*los archivos .xps en él, el método agrega estos archivos a la cola de impresión. El ejemplo se supone que la impresora no es XPSDrv, por lo que estamos pasando `false` al último parámetro de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> método. Por este motivo, el método validará la marcación [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] en el archivo antes de intentar convertirla en un lenguaje de descripción de la página de la impresora. Si se produce un error validación, se produce una excepción. El código de ejemplo detectará la excepción, la notificará al usuario y, a continuación, continuará con el proceso en el siguiente archivo [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 Si está utilizando una impresora XPSDrv, puede establecer el parámetro final en `true`. En ese caso, puesto que [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] es el idioma de descripción de la página de la impresora, el método enviará el archivo a la impresora sin validarlo o convertirlo en otro idioma de descripción de página. Si no está seguro en tiempo de diseño si la aplicación usa una impresora XPSDrv, puede modificar la aplicación para que lea el <xref:System.Printing.PrintQueue.IsXpsDevice%2A> propiedad y rama de acuerdo con lo que encuentre.  
  
 Puesto que inicialmente habrá pocas impresoras XPSDrv disponibles inmediatamente después del lanzamiento de [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] y Microsoft .NET Framework, es posible que necesite camuflar una impresora no XPSDrv como una impresora XPSDrv. Para ello, agregue Pipelineconfig.xml a la lista de archivos en la siguiente clave del registro del equipo que ejecuta la aplicación:  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\*\<PseudoXPSPrinter>* \DependentFiles  
  
 donde  *\<PseudoXPSPrinter >* es cualquier cola de impresión. El equipo debe reiniciarse a continuación.  
  
 Este camuflaje le permitirá pasar `true` como el último parámetro de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> sin producir una excepción, pero dado que  *\<PseudoXPSPrinter >* no es realmente una impresora XPSDrv, sólo se imprimirá basura.  
  
 **Tenga en cuenta** por motivos de simplicidad, el ejemplo anterior utiliza la presencia de un \*.xps extensión como prueba de que es un archivo [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]. Sin embargo, los archivos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] no tienen necesariamente esta extensión. [isXPS.exe (Herramienta isXPS Conformance)](https://msdn.microsoft.com/library/bfbb433f-7ab6-417a-90f0-71443d76bcb3(v=vs.100)) es una manera de probar la validez de un archivo para [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.AddJob%2A>  
 <xref:System.Threading.ApartmentState>  
 <xref:System.STAThreadAttribute>  
 [XPS](https://www.microsoft.com/xps)  
 [Imprimir un documento XPS](https://msdn.microsoft.com/library/849555c8-0c4e-48c0-86bc-a5494c69b36c(v=vs.90))  
 [Subprocesamiento administrado y](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))  
 [isXPS.exe (Herramienta isXPS Conformance)](https://msdn.microsoft.com/library/bfbb433f-7ab6-417a-90f0-71443d76bcb3(v=vs.100))  
 [Documentos en WPF](documents-in-wpf.md)  
 [Información general sobre impresión](printing-overview.md)
