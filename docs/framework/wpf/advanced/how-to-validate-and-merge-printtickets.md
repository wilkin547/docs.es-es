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
ms.openlocfilehash: 37a1c0600b8429158336968507ddc8cfb6d8f98b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485643"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="c58be-102">Cómo: Validar y combinar elementos PrintTicket</span><span class="sxs-lookup"><span data-stu-id="c58be-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="c58be-103">El [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [esquema de impresión](https://go.microsoft.com/fwlink/?LinkId=186397) incluye flexible y extensible <xref:System.Printing.PrintCapabilities> y <xref:System.Printing.PrintTicket> elementos.</span><span class="sxs-lookup"><span data-stu-id="c58be-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="c58be-104">El primero de ellos detalla las capacidades de un dispositivo de impresión y el segundo especifica cómo el dispositivo debe usar esas capacidades con respecto a una secuencia determinada de documentos, documentos individuales o una página individual.</span><span class="sxs-lookup"><span data-stu-id="c58be-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="c58be-105">Una secuencia de tareas para una aplicación que admite la impresión normal sería como sigue.</span><span class="sxs-lookup"><span data-stu-id="c58be-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="c58be-106">Determinar las capacidades de la impresora.</span><span class="sxs-lookup"><span data-stu-id="c58be-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="c58be-107">Configurar un <xref:System.Printing.PrintTicket> usar esas capacidades.</span><span class="sxs-lookup"><span data-stu-id="c58be-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="c58be-108">Validar el <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="c58be-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="c58be-109">En este artículo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="c58be-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c58be-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c58be-110">Example</span></span>  
 <span data-ttu-id="c58be-111">En el ejemplo siguiente, nos interesa solo si una impresora puede admitir la impresión a doble cara: impresión a dos caras.</span><span class="sxs-lookup"><span data-stu-id="c58be-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="c58be-112">Los pasos principales son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="c58be-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="c58be-113">Obtener un <xref:System.Printing.PrintCapabilities> objeto con el <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c58be-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="c58be-114">Comprobar la presencia de la función que desea.</span><span class="sxs-lookup"><span data-stu-id="c58be-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="c58be-115">En el ejemplo siguiente, se prueba el <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> propiedad de la <xref:System.Printing.PrintCapabilities> objeto la presencia de la funcionalidad de impresión en ambas caras de una hoja de papel con la activación"página" en el lado largo de la hoja.</span><span class="sxs-lookup"><span data-stu-id="c58be-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="c58be-116">Puesto que <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> es una colección, utilizamos el `Contains` método <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="c58be-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c58be-117">Este paso no es estrictamente necesario.</span><span class="sxs-lookup"><span data-stu-id="c58be-117">This step is not strictly necessary.</span></span> <span data-ttu-id="c58be-118">El <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método usa a continuación comprobará cada solicitud en el <xref:System.Printing.PrintTicket> frente a las capacidades de la impresora.</span><span class="sxs-lookup"><span data-stu-id="c58be-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="c58be-119">Si la función solicitada no es compatible con la impresora, el controlador de impresora sustituirá por una solicitud alternativa en el <xref:System.Printing.PrintTicket> devuelto por el método.</span><span class="sxs-lookup"><span data-stu-id="c58be-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="c58be-120">Si la impresora admite la impresión a doble cara, el código de ejemplo crea un <xref:System.Printing.PrintTicket> que solicita el dúplex.</span><span class="sxs-lookup"><span data-stu-id="c58be-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="c58be-121">Pero la aplicación no especifica cada posible configuración de impresora disponible en el <xref:System.Printing.PrintTicket> elemento.</span><span class="sxs-lookup"><span data-stu-id="c58be-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="c58be-122">Eso sería un desperdicio de programador y de tiempo del programa.</span><span class="sxs-lookup"><span data-stu-id="c58be-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="c58be-123">En su lugar, el código establece solo en la solicitud de impresión a doble cara y, a continuación, combina este <xref:System.Printing.PrintTicket> con una existente, totalmente configurada y validada, <xref:System.Printing.PrintTicket>, en este caso, la predeterminada del usuario <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="c58be-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="c58be-124">En consecuencia, el ejemplo llama a la <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método para combinar el nuevo mínimo, <xref:System.Printing.PrintTicket> no tiene valor predeterminado del usuario <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="c58be-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="c58be-125">Esto devuelve un <xref:System.Printing.ValidationResult> que incluye el nuevo <xref:System.Printing.PrintTicket> como uno de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="c58be-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="c58be-126">El ejemplo, a continuación, comprueba que el nuevo <xref:System.Printing.PrintTicket> solicitudes de impresión a doble cara.</span><span class="sxs-lookup"><span data-stu-id="c58be-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="c58be-127">Si es así, a continuación, se convierte en la nueva solicitud de impresión predeterminada para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c58be-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="c58be-128">Si tenía ha omitido el paso 2 anterior y la impresora no admitía el dúplex en el lado largo, entonces tendría como resultado la prueba `false`.</span><span class="sxs-lookup"><span data-stu-id="c58be-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="c58be-129">(Consulte la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="c58be-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="c58be-130">Es el último paso significativo confirmar el cambio a la <xref:System.Printing.PrintQueue.UserPrintTicket%2A> propiedad de la <xref:System.Printing.PrintQueue> con el <xref:System.Printing.PrintQueue.Commit%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c58be-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="c58be-131">Por lo que puede probar rápidamente en este ejemplo, a continuación se presenta el resto de la misma.</span><span class="sxs-lookup"><span data-stu-id="c58be-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="c58be-132">Crear un proyecto y un espacio de nombres y, a continuación, pegue ambas los fragmentos de código en este artículo en el bloque de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c58be-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="c58be-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c58be-133">See Also</span></span>  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="c58be-134">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="c58be-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="c58be-135">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="c58be-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="c58be-136">Esquema de impresión</span><span class="sxs-lookup"><span data-stu-id="c58be-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
