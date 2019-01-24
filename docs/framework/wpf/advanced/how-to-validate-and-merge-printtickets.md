---
title: Procedimiento Validar y combinar elementos PrintTicket
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 0b9f7b101ea4f06c86f66f8e4e16d1ffeabaa9e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671946"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Procedimiento Validar y combinar elementos PrintTicket
El [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [esquema de impresión](https://go.microsoft.com/fwlink/?LinkId=186397) incluye flexible y extensible <xref:System.Printing.PrintCapabilities> y <xref:System.Printing.PrintTicket> elementos. El primero de ellos detalla las capacidades de un dispositivo de impresión y el segundo especifica cómo el dispositivo debe usar esas capacidades con respecto a una secuencia determinada de documentos, documentos individuales o una página individual.  
  
 Una secuencia de tareas para una aplicación que admite la impresión normal sería como sigue.  
  
1.  Determinar las capacidades de la impresora.  
  
2.  Configurar un <xref:System.Printing.PrintTicket> usar esas capacidades.  
  
3.  Validar el <xref:System.Printing.PrintTicket>.  
  
 En este artículo se muestra cómo hacerlo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, nos interesa solo si una impresora puede admitir la impresión a doble cara: impresión a dos caras. Los pasos principales son los siguientes.  
  
1.  Obtener un <xref:System.Printing.PrintCapabilities> objeto con el <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> método.  
  
2.  Comprobar la presencia de la función que desea. En el ejemplo siguiente, se prueba el <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> propiedad de la <xref:System.Printing.PrintCapabilities> objeto la presencia de la funcionalidad de impresión en ambas caras de una hoja de papel con la activación"página" en el lado largo de la hoja. Puesto que <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> es una colección, utilizamos el `Contains` método <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Este paso no es estrictamente necesario. El <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método usa a continuación comprobará cada solicitud en el <xref:System.Printing.PrintTicket> frente a las capacidades de la impresora. Si la función solicitada no es compatible con la impresora, el controlador de impresora sustituirá por una solicitud alternativa en el <xref:System.Printing.PrintTicket> devuelto por el método.  
  
3.  Si la impresora admite la impresión a doble cara, el código de ejemplo crea un <xref:System.Printing.PrintTicket> que solicita el dúplex. Pero la aplicación no especifica cada posible configuración de impresora disponible en el <xref:System.Printing.PrintTicket> elemento. Eso sería un desperdicio de programador y de tiempo del programa. En su lugar, el código establece solo en la solicitud de impresión a doble cara y, a continuación, combina este <xref:System.Printing.PrintTicket> con una existente, totalmente configurada y validada, <xref:System.Printing.PrintTicket>, en este caso, la predeterminada del usuario <xref:System.Printing.PrintTicket>.  
  
4.  En consecuencia, el ejemplo llama a la <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método para combinar el nuevo mínimo, <xref:System.Printing.PrintTicket> no tiene valor predeterminado del usuario <xref:System.Printing.PrintTicket>. Esto devuelve un <xref:System.Printing.ValidationResult> que incluye el nuevo <xref:System.Printing.PrintTicket> como uno de sus propiedades.  
  
5.  El ejemplo, a continuación, comprueba que el nuevo <xref:System.Printing.PrintTicket> solicitudes de impresión a doble cara. Si es así, a continuación, se convierte en la nueva solicitud de impresión predeterminada para el usuario. Si tenía ha omitido el paso 2 anterior y la impresora no admitía el dúplex en el lado largo, entonces tendría como resultado la prueba `false`. (Consulte la nota anterior).  
  
6.  Es el último paso significativo confirmar el cambio a la <xref:System.Printing.PrintQueue.UserPrintTicket%2A> propiedad de la <xref:System.Printing.PrintQueue> con el <xref:System.Printing.PrintQueue.Commit%2A> método.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Por lo que puede probar rápidamente en este ejemplo, a continuación se presenta el resto de la misma. Crear un proyecto y un espacio de nombres y, a continuación, pegue ambas los fragmentos de código en este artículo en el bloque de espacio de nombres.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)
- [Esquema de impresión](https://go.microsoft.com/fwlink/?LinkId=186397)
