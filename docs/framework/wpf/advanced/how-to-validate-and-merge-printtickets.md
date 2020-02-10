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
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="dd2eb-102">Cómo: Validar y combinar elementos PrintTicket</span><span class="sxs-lookup"><span data-stu-id="dd2eb-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="dd2eb-103">El esquema de [impresión](/windows/win32/printdocs/printschema) de Microsoft Windows incluye los elementos <xref:System.Printing.PrintCapabilities> y <xref:System.Printing.PrintTicket> flexibles y extensibles.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-103">The Microsoft Windows [Print Schema](/windows/win32/printdocs/printschema) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="dd2eb-104">En el primero se detallan las capacidades de un dispositivo de impresión y en el último se especifica cómo el dispositivo debe usar esas capacidades con respecto a una secuencia determinada de documentos, documento individual o página individual.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="dd2eb-105">Una secuencia típica de tareas para una aplicación que admite la impresión sería la siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="dd2eb-106">Determinar las capacidades de una impresora.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="dd2eb-107">Configure un <xref:System.Printing.PrintTicket> para usar esas capacidades.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="dd2eb-108">Valide el <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="dd2eb-109">En este artículo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd2eb-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd2eb-110">Example</span></span>  
 <span data-ttu-id="dd2eb-111">En el ejemplo simple siguiente, solo le interesará si una impresora admite la impresión a dos caras.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="dd2eb-112">Los pasos principales son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="dd2eb-113">Obtiene un objeto <xref:System.Printing.PrintCapabilities> con el método <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="dd2eb-114">Compruebe la presencia de la funcionalidad que desee.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="dd2eb-115">En el ejemplo siguiente, se prueba la propiedad <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> del objeto <xref:System.Printing.PrintCapabilities> para la presencia de la capacidad de impresión en ambos lados de una hoja de papel con el "torneado de páginas" a lo largo del lado de la hoja.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="dd2eb-116">Como <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> es una colección, usamos el método `Contains` de <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="dd2eb-117">Este paso no es estrictamente necesario.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-117">This step is not strictly necessary.</span></span> <span data-ttu-id="dd2eb-118">El método <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> que se usa a continuación comprobará cada solicitud del <xref:System.Printing.PrintTicket> con las capacidades de la impresora.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="dd2eb-119">Si la funcionalidad solicitada no es compatible con la impresora, el controlador de impresora sustituirá una solicitud alternativa en el <xref:System.Printing.PrintTicket> devuelto por el método.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="dd2eb-120">Si la impresora admite el dúplex, el código de ejemplo crea un <xref:System.Printing.PrintTicket> que solicita dúplex.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="dd2eb-121">Pero la aplicación no especifica todos los valores posibles de la impresora disponibles en el elemento <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="dd2eb-122">Esto sería una pérdida de tiempo del programa y del programador.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="dd2eb-123">En su lugar, el código solo establece la solicitud de dúplex y, a continuación, combina este <xref:System.Printing.PrintTicket> con un <xref:System.Printing.PrintTicket>existente, completamente configurado y validado, en este caso, la <xref:System.Printing.PrintTicket>predeterminada del usuario.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="dd2eb-124">En consecuencia, el ejemplo llama al método <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> para combinar el nuevo <xref:System.Printing.PrintTicket> mínimo con el <xref:System.Printing.PrintTicket>predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="dd2eb-125">Esto devuelve un <xref:System.Printing.ValidationResult> que incluye el nuevo <xref:System.Printing.PrintTicket> como una de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="dd2eb-126">A continuación, el ejemplo comprueba que el nuevo <xref:System.Printing.PrintTicket> solicita dúplex.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="dd2eb-127">Si lo hace, el ejemplo lo convierte en el nuevo vale de impresión predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="dd2eb-128">Si se ha omitido el paso 2 anterior y la impresora no admitía la impresión dúplex en el lado largo, la prueba habría dado como resultado `false`.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="dd2eb-129">(Vea la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="dd2eb-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="dd2eb-130">El último paso significativo es confirmar el cambio en la propiedad <xref:System.Printing.PrintQueue.UserPrintTicket%2A> de la <xref:System.Printing.PrintQueue> con el método <xref:System.Printing.PrintQueue.Commit%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="dd2eb-131">Para que pueda probar rápidamente este ejemplo, el resto de ellos se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="dd2eb-132">Cree un proyecto y un espacio de nombres y, a continuación, pegue los fragmentos de código de este artículo en el bloque de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dd2eb-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="dd2eb-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd2eb-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="dd2eb-134">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="dd2eb-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="dd2eb-135">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="dd2eb-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="dd2eb-136">Imprimir esquema</span><span class="sxs-lookup"><span data-stu-id="dd2eb-136">Print Schema</span></span>](/windows/win32/printdocs/printschema)
