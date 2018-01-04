---
title: "Cómo: Validar y combinar elementos PrintTicket"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5cf2091d50433bb936b3d4976d1c3eabea73edc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-and-merge-printtickets"></a>Cómo: Validar y combinar elementos PrintTicket
El [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397) incluye flexible y extensible <xref:System.Printing.PrintCapabilities> y <xref:System.Printing.PrintTicket> elementos. El primero de ellos detalla las capacidades de un dispositivo de impresión y el segundo especifica cómo el dispositivo debe utilizar esas capacidades con respecto a una secuencia determinada de documentos, documentos individuales o una página individual.  
  
 Una secuencia de tareas para una aplicación que admite la impresión típica sería como sigue.  
  
1.  Determinar las capacidades de la impresora.  
  
2.  Configurar un <xref:System.Printing.PrintTicket> a usar esas funciones.  
  
3.  Validar el <xref:System.Printing.PrintTicket>.  
  
 Este artículo muestra cómo hacerlo.  
  
## <a name="example"></a>Ejemplo  
 En el sencillo ejemplo, nos interesa solo si una impresora puede admitir la impresión a doble cara: impresión a dos caras. Los pasos principales son los siguientes.  
  
1.  Obtener un <xref:System.Printing.PrintCapabilities> objeto con el <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> método.  
  
2.  Comprobar la presencia de la función que desea. En el ejemplo siguiente, se probará la <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> propiedad de la <xref:System.Printing.PrintCapabilities> objeto la presencia de la capacidad de impresión en ambas caras de una hoja de papel con "activar de página" en el lado largo de la hoja. Puesto que <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> es una colección, usamos el `Contains` método <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Este paso no es estrictamente necesaria. El <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método usa a continuación comprobará cada solicitud en el <xref:System.Printing.PrintTicket> con las capacidades de la impresora. Si la función solicitada no es compatible con la impresora, el controlador de impresora sustituirá una solicitud alternativa en la <xref:System.Printing.PrintTicket> devuelta por el método.  
  
3.  Si la impresora admite la impresión a doble cara, el código de ejemplo crea un <xref:System.Printing.PrintTicket> que pedirá una impresión a doble cara. Pero la aplicación no especifica cada posible configuración de impresora disponible en el <xref:System.Printing.PrintTicket> elemento. Eso sería innecesarios del programador y la hora de programa. En su lugar, el código establece la solicitud de impresión a doble cara y, a continuación, combina este <xref:System.Printing.PrintTicket> a otra, totalmente configurada y validada, <xref:System.Printing.PrintTicket>, en este caso, la predeterminada del usuario <xref:System.Printing.PrintTicket>.  
  
4.  En consecuencia, el ejemplo llama a la <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método para combinar el nuevo mínimo, <xref:System.Printing.PrintTicket> no tiene valor predeterminado del usuario <xref:System.Printing.PrintTicket>. Esto devuelve un <xref:System.Printing.ValidationResult> que incluye el nuevo <xref:System.Printing.PrintTicket> como uno de sus propiedades.  
  
5.  El ejemplo, a continuación, comprueba que el nuevo <xref:System.Printing.PrintTicket> solicitudes de impresión a doble cara. Si es así, el ejemplo lo pone a la nueva solicitud de impresión de predeterminado para el usuario. Si tenía se han omitido paso 2 anterior y la impresora no admitía la impresión a doble cara en el lado largo, habría provocado que la prueba en `false`. (Vea la nota anterior).  
  
6.  El último paso significativo es confirmar el cambio a la <xref:System.Printing.PrintQueue.UserPrintTicket%2A> propiedad de la <xref:System.Printing.PrintQueue> con el <xref:System.Printing.PrintQueue.Commit%2A> método.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Por lo que puede probar rápidamente en este ejemplo, el resto de los se muestra a continuación. Crear un proyecto y un espacio de nombres y, a continuación, pegue los fragmentos de código de este artículo en el bloque de espacio de nombres.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Esquema de impresión](http://go.microsoft.com/fwlink/?LinkId=186397)
