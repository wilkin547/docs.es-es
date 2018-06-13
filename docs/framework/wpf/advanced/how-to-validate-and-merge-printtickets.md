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
ms.openlocfilehash: 11160d7ec59914afbe501ba731c0c04a85ffc4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548498"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="9bb44-102">Cómo: Validar y combinar elementos PrintTicket</span><span class="sxs-lookup"><span data-stu-id="9bb44-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="9bb44-103">El [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397) incluye flexible y extensible <xref:System.Printing.PrintCapabilities> y <xref:System.Printing.PrintTicket> elementos.</span><span class="sxs-lookup"><span data-stu-id="9bb44-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="9bb44-104">El primero de ellos detalla las capacidades de un dispositivo de impresión y el segundo especifica cómo el dispositivo debe utilizar esas capacidades con respecto a una secuencia determinada de documentos, documentos individuales o una página individual.</span><span class="sxs-lookup"><span data-stu-id="9bb44-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="9bb44-105">Una secuencia de tareas para una aplicación que admite la impresión típica sería como sigue.</span><span class="sxs-lookup"><span data-stu-id="9bb44-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="9bb44-106">Determinar las capacidades de la impresora.</span><span class="sxs-lookup"><span data-stu-id="9bb44-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="9bb44-107">Configurar un <xref:System.Printing.PrintTicket> a usar esas funciones.</span><span class="sxs-lookup"><span data-stu-id="9bb44-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="9bb44-108">Validar el <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="9bb44-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="9bb44-109">Este artículo muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="9bb44-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bb44-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bb44-110">Example</span></span>  
 <span data-ttu-id="9bb44-111">En el sencillo ejemplo, nos interesa solo si una impresora puede admitir la impresión a doble cara: impresión a dos caras.</span><span class="sxs-lookup"><span data-stu-id="9bb44-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="9bb44-112">Los pasos principales son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="9bb44-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="9bb44-113">Obtener un <xref:System.Printing.PrintCapabilities> objeto con el <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9bb44-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="9bb44-114">Comprobar la presencia de la función que desea.</span><span class="sxs-lookup"><span data-stu-id="9bb44-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="9bb44-115">En el ejemplo siguiente, se probará la <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> propiedad de la <xref:System.Printing.PrintCapabilities> objeto la presencia de la capacidad de impresión en ambas caras de una hoja de papel con "activar de página" en el lado largo de la hoja.</span><span class="sxs-lookup"><span data-stu-id="9bb44-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="9bb44-116">Puesto que <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> es una colección, usamos el `Contains` método <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="9bb44-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9bb44-117">Este paso no es estrictamente necesaria.</span><span class="sxs-lookup"><span data-stu-id="9bb44-117">This step is not strictly necessary.</span></span> <span data-ttu-id="9bb44-118">El <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método usa a continuación comprobará cada solicitud en el <xref:System.Printing.PrintTicket> con las capacidades de la impresora.</span><span class="sxs-lookup"><span data-stu-id="9bb44-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="9bb44-119">Si la función solicitada no es compatible con la impresora, el controlador de impresora sustituirá una solicitud alternativa en la <xref:System.Printing.PrintTicket> devuelta por el método.</span><span class="sxs-lookup"><span data-stu-id="9bb44-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="9bb44-120">Si la impresora admite la impresión a doble cara, el código de ejemplo crea un <xref:System.Printing.PrintTicket> que pedirá una impresión a doble cara.</span><span class="sxs-lookup"><span data-stu-id="9bb44-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="9bb44-121">Pero la aplicación no especifica cada posible configuración de impresora disponible en el <xref:System.Printing.PrintTicket> elemento.</span><span class="sxs-lookup"><span data-stu-id="9bb44-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="9bb44-122">Eso sería innecesarios del programador y la hora de programa.</span><span class="sxs-lookup"><span data-stu-id="9bb44-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="9bb44-123">En su lugar, el código establece la solicitud de impresión a doble cara y, a continuación, combina este <xref:System.Printing.PrintTicket> a otra, totalmente configurada y validada, <xref:System.Printing.PrintTicket>, en este caso, la predeterminada del usuario <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="9bb44-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="9bb44-124">En consecuencia, el ejemplo llama a la <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> método para combinar el nuevo mínimo, <xref:System.Printing.PrintTicket> no tiene valor predeterminado del usuario <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="9bb44-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="9bb44-125">Esto devuelve un <xref:System.Printing.ValidationResult> que incluye el nuevo <xref:System.Printing.PrintTicket> como uno de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9bb44-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="9bb44-126">El ejemplo, a continuación, comprueba que el nuevo <xref:System.Printing.PrintTicket> solicitudes de impresión a doble cara.</span><span class="sxs-lookup"><span data-stu-id="9bb44-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="9bb44-127">Si es así, el ejemplo lo pone a la nueva solicitud de impresión de predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9bb44-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="9bb44-128">Si tenía se han omitido paso 2 anterior y la impresora no admitía la impresión a doble cara en el lado largo, habría provocado que la prueba en `false`.</span><span class="sxs-lookup"><span data-stu-id="9bb44-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="9bb44-129">(Vea la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="9bb44-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="9bb44-130">El último paso significativo es confirmar el cambio a la <xref:System.Printing.PrintQueue.UserPrintTicket%2A> propiedad de la <xref:System.Printing.PrintQueue> con el <xref:System.Printing.PrintQueue.Commit%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9bb44-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="9bb44-131">Por lo que puede probar rápidamente en este ejemplo, el resto de los se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="9bb44-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="9bb44-132">Crear un proyecto y un espacio de nombres y, a continuación, pegue los fragmentos de código de este artículo en el bloque de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="9bb44-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="9bb44-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bb44-133">See Also</span></span>  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="9bb44-134">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="9bb44-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="9bb44-135">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="9bb44-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="9bb44-136">Esquema de impresión</span><span class="sxs-lookup"><span data-stu-id="9bb44-136">Print Schema</span></span>](http://go.microsoft.com/fwlink/?LinkId=186397)
