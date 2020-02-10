---
title: 'Cómo: Validar y combinar elementos PrintTicket'
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
ms.openlocfilehash: bd7f399555b343a52ec6f36aa3b8c706747d8b06
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094532"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Cómo: Validar y combinar elementos PrintTicket
El esquema de [impresión](/windows/win32/printdocs/printschema) de Microsoft Windows incluye los elementos <xref:System.Printing.PrintCapabilities> y <xref:System.Printing.PrintTicket> flexibles y extensibles. En el primero se detallan las capacidades de un dispositivo de impresión y en el último se especifica cómo el dispositivo debe usar esas capacidades con respecto a una secuencia determinada de documentos, documento individual o página individual.  
  
 Una secuencia típica de tareas para una aplicación que admite la impresión sería la siguiente.  
  
1. Determinar las capacidades de una impresora.  
  
2. Configure un <xref:System.Printing.PrintTicket> para usar esas capacidades.  
  
3. Valide el <xref:System.Printing.PrintTicket>.  
  
 En este artículo se muestra cómo hacerlo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo simple siguiente, solo le interesará si una impresora admite la impresión a dos caras. Los pasos principales son los siguientes.  
  
1. Obtiene un objeto <xref:System.Printing.PrintCapabilities> con el método <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>.  
  
2. Compruebe la presencia de la funcionalidad que desee. En el ejemplo siguiente, se prueba la propiedad <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> del objeto <xref:System.Printing.PrintCapabilities> para la presencia de la capacidad de impresión en ambos lados de una hoja de papel con el "torneado de páginas" a lo largo del lado de la hoja. Como <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> es una colección, usamos el método `Contains` de <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    > Este paso no es estrictamente necesario. El método <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> que se usa a continuación comprobará cada solicitud del <xref:System.Printing.PrintTicket> con las capacidades de la impresora. Si la funcionalidad solicitada no es compatible con la impresora, el controlador de impresora sustituirá una solicitud alternativa en el <xref:System.Printing.PrintTicket> devuelto por el método.  
  
3. Si la impresora admite el dúplex, el código de ejemplo crea un <xref:System.Printing.PrintTicket> que solicita dúplex. Pero la aplicación no especifica todos los valores posibles de la impresora disponibles en el elemento <xref:System.Printing.PrintTicket>. Esto sería una pérdida de tiempo del programa y del programador. En su lugar, el código solo establece la solicitud de dúplex y, a continuación, combina este <xref:System.Printing.PrintTicket> con un <xref:System.Printing.PrintTicket>existente, completamente configurado y validado, en este caso, la <xref:System.Printing.PrintTicket>predeterminada del usuario.  
  
4. En consecuencia, el ejemplo llama al método <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> para combinar el nuevo <xref:System.Printing.PrintTicket> mínimo con el <xref:System.Printing.PrintTicket>predeterminado del usuario. Esto devuelve un <xref:System.Printing.ValidationResult> que incluye el nuevo <xref:System.Printing.PrintTicket> como una de sus propiedades.  
  
5. A continuación, el ejemplo comprueba que el nuevo <xref:System.Printing.PrintTicket> solicita dúplex. Si lo hace, el ejemplo lo convierte en el nuevo vale de impresión predeterminado para el usuario. Si se ha omitido el paso 2 anterior y la impresora no admitía la impresión dúplex en el lado largo, la prueba habría dado como resultado `false`. (Vea la nota anterior).  
  
6. El último paso significativo es confirmar el cambio en la propiedad <xref:System.Printing.PrintQueue.UserPrintTicket%2A> de la <xref:System.Printing.PrintQueue> con el método <xref:System.Printing.PrintQueue.Commit%2A>.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Para que pueda probar rápidamente este ejemplo, el resto de ellos se muestra a continuación. Cree un proyecto y un espacio de nombres y, a continuación, pegue los fragmentos de código de este artículo en el bloque de espacio de nombres.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
- [Imprimir esquema](/windows/win32/printdocs/printschema)
