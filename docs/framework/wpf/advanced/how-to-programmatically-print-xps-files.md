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
ms.openlocfilehash: cc86a7e7c6a816af37c3d063825ed62583afa78a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966999"
---
# <a name="how-to-programmatically-print-xps-files"></a>Cómo: Imprimir mediante programación archivos XPS

Puede usar una sobrecarga del método <xref:System.Printing.PrintQueue.AddJob%2A> para imprimir archivos XML Paper Specification (XPS) sin abrir un <xref:System.Windows.Controls.PrintDialog> o, en principio, cualquier [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] en absoluto.

También puede imprimir archivos XPS mediante los muchos métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A?displayProperty=nameWithType> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A?displayProperty=nameWithType>. Para obtener más información, vea [imprimir un documento XPS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90)).

Otra forma de imprimir XPS es usar los métodos <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A?displayProperty=nameWithType> o <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A?displayProperty=nameWithType>. Vea [Invocar un cuadro de diálogo de impresión](how-to-invoke-a-print-dialog.md).

## <a name="example"></a>Ejemplo

Los pasos principales para usar el método de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> de tres parámetros son los siguientes. En el ejemplo siguiente se proporciona información detallada.

1. Determinar si la impresora es una impresora XPSDrv. Consulte [información general sobre impresión](printing-overview.md) para obtener más información sobre XPSDrv.

2. Si la impresora no es una impresora XPSDrv, establezca el apartamento del subproceso en un subproceso único.

3. Crear una instancia de un servidor de impresión y un objeto de cola de impresión.

4. Llame al método, especificando un nombre de trabajo, el archivo que se va a imprimir y una marca de <xref:System.Boolean> que indica si la impresora es una impresora XPSDrv.

En el ejemplo siguiente se muestra cómo procesar por lotes todos los archivos XPS de un directorio. Aunque la aplicación pide al usuario que especifique el directorio, el método de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> de tres parámetros no requiere un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Se puede usar en cualquier ruta de código donde tenga un nombre de archivo XPS y una ruta de acceso que pueda pasar a él.

La sobrecarga de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> de tres parámetros de <xref:System.Printing.PrintQueue.AddJob%2A> debe ejecutarse en un apartamento de subproceso único cada vez que se `false`el parámetro de <xref:System.Boolean>, que debe ser cuando se usa una impresora que no es XPSDrv. Sin embargo, el estado de Apartamento predeterminado para .NET es de varios subprocesos. Este es el valor predeterminado, ya que el en el ejemplo se da por hecho que estamos antes una impresora que no es XPSDrv.

Existen dos maneras de cambiar el valor predeterminado. Una de ellas consiste simplemente en agregar el <xref:System.STAThreadAttribute> (es decir, "`[System.STAThreadAttribute()]`") justo encima de la primera línea del método `Main` de la aplicación (normalmente "`static void Main(string[] args)`"). Sin embargo, muchas aplicaciones requieren que el método `Main` tenga un estado de apartamento de varios subprocesos, por lo que hay un segundo método: poner la llamada a <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> en un subproceso independiente cuyo estado de apartamento esté establecido en <xref:System.Threading.ApartmentState.STA> con <xref:System.Threading.Thread.SetApartmentState%2A>. El ejemplo siguiente utiliza esta segunda técnica.

En consecuencia, el ejemplo comienza creando una instancia de un objeto <xref:System.Threading.Thread> y pasándole un método **PrintXPS** como parámetro <xref:System.Threading.ThreadStart>. (El método **PrintXPS** se define más adelante en el ejemplo). Después, el subproceso se establece en un apartamento de subproceso único. El único código restante del método `Main` inicia el nuevo subproceso.

El grueso del ejemplo está en el método `static`**BatchXPSPrinter.PrintXPS**. Después de crear un servidor de impresión y una cola, el método solicita al usuario un directorio que contiene archivos XPS. Después de validar la existencia del directorio y la presencia de archivos \*. XPS en él, el método agrega cada uno de estos archivos a la cola de impresión. En el ejemplo se da por supuesto que la impresora no es XPSDrv, por lo que pasamos `false` al último parámetro de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> método. Por esta razón, el método validará el marcado XPS en el archivo antes de intentar convertirlo en el idioma de descripción de la página de la impresora. Si se produce un error validación, se produce una excepción. El código de ejemplo detectará la excepción, lo notificará al usuario y, después, continuará para procesar el siguiente archivo XPS.

[!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
[!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]

Si está utilizando una impresora XPSDrv, puede establecer el parámetro final en `true`. En ese caso, como XPS es el idioma de descripción de la página de la impresora, el método enviará el archivo a la impresora sin validarlo ni convertirlo en otro lenguaje de descripción de página. Si no está seguro en tiempo de diseño si la aplicación va a usar una impresora XPSDrv, puede modificar la aplicación para que lea la propiedad <xref:System.Printing.PrintQueue.IsXpsDevice%2A> y la bifurcación según lo que encuentre.

Dado que inicialmente habrá pocas impresoras XPSDrv disponibles inmediatamente después del lanzamiento de Windows Vista y Microsoft .NET Framework, puede que tenga que disfrazar una impresora que no sea XPSDrv como una impresora XPSDrv. Para ello, agregue Pipelineconfig.xml a la lista de archivos en la siguiente clave del registro del equipo que ejecuta la aplicación:

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles

donde  *\<PseudoXPSPrinter >* es cualquier cola de impresión. El equipo debe reiniciarse a continuación.

Esta disfraz le permitirá pasar `true` como el último parámetro de <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> sin producir una excepción, pero como *\<PseudoXPSPrinter >* no es realmente una impresora XPSDrv, solo se imprimirán los elementos no utilizados.

> [!NOTE]
> Para simplificar, en el ejemplo anterior se usa la presencia de una extensión \*. XPS como prueba de que un archivo es XPS. Sin embargo, los archivos XPS no tienen que tener esta extensión. [IsXPS. exe (herramienta de cumplimiento isXPS)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) es una manera de probar un archivo para comprobar la validez del XPS.

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
