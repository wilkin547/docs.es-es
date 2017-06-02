---
title: "C&#243;mo: Validar y combinar elementos PrintTicket | Microsoft Docs"
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
  - "combinar PrintTickets"
  - "PrintTicket, combinar"
  - "PrintTicket, validación"
  - "validación de PrintTickets"
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Validar y combinar elementos PrintTicket
El [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [esquema de impresión](http://go.microsoft.com/fwlink/?LinkId=186397) incluye los elementos <xref:System.Printing.PrintCapabilities> y <xref:System.Printing.PrintTicket> flexibles y extensibles.  El primero de ellos detalla las funciones de un dispositivo de impresión y el segundo especifica se deben usar funciones en el dispositivo con respecto a una secuencia determinada de documentos, un documento individual o una página individual.  
  
 A continuación se indica una secuencia típica de tareas para una aplicación que admite la impresión.  
  
1.  Determinar las funciones de una impresora.  
  
2.  Configurar una <xref:System.Printing.PrintTicket> para utilizar esas funciones.  
  
3.  Validar la solicitud de impresión \(<xref:System.Printing.PrintTicket>\).  
  
 En este artículo se muestra cómo hacerlo.  
  
## Ejemplo  
 En el ejemplo simple siguiente, lo único que nos interesa es saber si una impresora admite la impresión a dos caras.  A continuación se enumeran los pasos principales.  
  
1.  Obtenga un objeto <xref:System.Printing.PrintCapabilities> mediante el método <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>.  
  
2.  Compruebe la presencia de la función que desea.  En el ejemplo siguiente, se prueba la propiedad <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> del objeto <xref:System.Printing.PrintCapabilities> para comprobar si está presente la función de impresión a dos caras girando la página sobre el lado largo de la hoja.  Puesto que <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> es una colección, se usa el método `Contains` de <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Este paso no es estrictamente necesario.  El método <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> que se utiliza a continuación comprueba cada solicitud de <xref:System.Printing.PrintTicket> con respecto a las funciones de la impresora.  Si la impresora no admite la función solicitada, en su lugar el controlador de impresora utiliza una solicitud alternativa en la <xref:System.Printing.PrintTicket> devuelto por el método.  
  
3.  Si la impresora admite la impresión a dos caras, el ejemplo de código crea una <xref:System.Printing.PrintTicket>, que solicita la impresión a dos caras.  Pero la aplicación no especifica cada posible configuración de impresora disponible en el elemento <xref:System.Printing.PrintTicket>.  Esto malgastaría tiempo de programación y tiempo de ejecución del programa.  En lugar de ello, en el código se establece únicamente la solicitud de impresión a dos caras y, a continuación, se combina <xref:System.Printing.PrintTicket> con otra <xref:System.Printing.PrintTicket> totalmente configurada y validada. En este caso, se utiliza la <xref:System.Printing.PrintTicket> predeterminada del usuario.  
  
4.  En consecuencia, en el ejemplo se llama al método <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> para combinar la nueva <xref:System.Printing.PrintTicket> mínima con la <xref:System.Printing.PrintTicket> predeterminada del usuario.  Esto devuelve un <xref:System.Printing.ValidationResult> que incluye la nueva <xref:System.Printing.PrintTicket> como una de sus propiedades.  
  
5.  A continuación, en el ejemplo se comprueba que la nueva <xref:System.Printing.PrintTicket> solicita la impresión a dos caras.  Si lo hace, entonces se convierte en la nueva solicitud de impresión predeterminada del usuario.  Si se omitiera el paso 2 anterior y la impresora no admite la impresión a dos caras con giro en el lado largo, entonces el resultado de la prueba sería `false`.  \(Consulte la nota anterior.\)  
  
6.  El último paso significativo es confirmar el cambio a la propiedad <xref:System.Printing.PrintQueue.UserPrintTicket%2A> de <xref:System.Printing.PrintQueue> con el método <xref:System.Printing.PrintQueue.Commit%2A>.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Para que pueda probar rápidamente este ejemplo, se presenta el resto del mismo a continuación.  Cree un proyecto y un espacio de nombres y, a continuación, pegue los dos fragmentos de código de este artículo en el bloque de espacio de nombres.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## Vea también  
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