---
title: "Cómo: Recuperar datos del Portapapeles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c009efe743865896341da268bd14bf24158df46d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="a6f80-102">Cómo: Recuperar datos del Portapapeles</span><span class="sxs-lookup"><span data-stu-id="a6f80-102">How to: Retrieve Data from the Clipboard</span></span>
<span data-ttu-id="a6f80-103">La <xref:System.Windows.Forms.Clipboard> clase proporciona métodos que puede usar para interactuar con la característica de Portapapeles del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="a6f80-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="a6f80-104">Muchas aplicaciones utilizan el Portapapeles como repositorio temporal para los datos.</span><span class="sxs-lookup"><span data-stu-id="a6f80-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="a6f80-105">Por ejemplo, procesadores de textos utilizan el Portapapeles durante las operaciones de cortar y pegar.</span><span class="sxs-lookup"><span data-stu-id="a6f80-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="a6f80-106">El Portapapeles también es útil para transferir información desde una aplicación a otra.</span><span class="sxs-lookup"><span data-stu-id="a6f80-106">The Clipboard is also useful for transferring information from one application to another.</span></span>  
  
 <span data-ttu-id="a6f80-107">Algunas aplicaciones almacenan datos en el Portapapeles en varios formatos para aumentar el número de otras aplicaciones que pueden utilizar potencialmente los datos.</span><span class="sxs-lookup"><span data-stu-id="a6f80-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="a6f80-108">Un formato de Portapapeles es una cadena que identifica el formato.</span><span class="sxs-lookup"><span data-stu-id="a6f80-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="a6f80-109">Una aplicación que utiliza el formato identificado puede recuperar los datos asociados en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="a6f80-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="a6f80-110">La <xref:System.Windows.Forms.DataFormats> clase proporciona nombres de formato predefinidos para su uso.</span><span class="sxs-lookup"><span data-stu-id="a6f80-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="a6f80-111">También puede utilizar sus propios nombres de formato o utilizar un tipo de objeto como su formato.</span><span class="sxs-lookup"><span data-stu-id="a6f80-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="a6f80-112">Para obtener información acerca de cómo agregar datos al Portapapeles, vea [Cómo: agregar datos al Portapapeles](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).</span><span class="sxs-lookup"><span data-stu-id="a6f80-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).</span></span>  
  
 <span data-ttu-id="a6f80-113">Para determinar si el Portapapeles contiene datos en un formato determinado, utilice uno de los `Contains` *formato* métodos o <xref:System.Windows.Forms.Clipboard.GetData%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a6f80-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="a6f80-114">Para recuperar datos desde el Portapapeles, utilice uno de los `Get` *formato* métodos o <xref:System.Windows.Forms.Clipboard.GetData%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a6f80-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="a6f80-115">Estos métodos son nuevos en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6f80-115">These methods are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
 <span data-ttu-id="a6f80-116">Para acceder a los datos del Portapapeles con versiones anteriores a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], use la <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> método y llamar a los métodos de devuelto <xref:System.Windows.Forms.IDataObject>.</span><span class="sxs-lookup"><span data-stu-id="a6f80-116">To access data from the Clipboard by using versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="a6f80-117">Para determinar si un formato determinado está disponible en el objeto devuelto, por ejemplo, llamar a la <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a6f80-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6f80-118">Todas las aplicaciones basadas en Windows comparten el Portapapeles del sistema.</span><span class="sxs-lookup"><span data-stu-id="a6f80-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="a6f80-119">Por lo tanto, el contenido está sujeto a cambios cuando se cambia a otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="a6f80-119">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="a6f80-120">La <xref:System.Windows.Forms.Clipboard> clase solo puede usarse en subprocesos establecidos en modo de apartamento de un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="a6f80-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="a6f80-121">Para utilizar esta clase, asegúrese de que su `Main` método está marcado con el <xref:System.STAThreadAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="a6f80-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="a6f80-122">Para recuperar datos del Portapapeles en un solo formato común</span><span class="sxs-lookup"><span data-stu-id="a6f80-122">To retrieve data from the Clipboard in a single, common format</span></span>  
  
1.  <span data-ttu-id="a6f80-123">Use la <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, o <xref:System.Windows.Forms.Clipboard.GetText%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a6f80-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="a6f80-124">También puede utilizar la correspondiente `Contains` *formato* métodos primero para determinar si los datos están disponibles en un formato determinado.</span><span class="sxs-lookup"><span data-stu-id="a6f80-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="a6f80-125">Estos métodos solo están disponibles en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6f80-125">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="a6f80-126">Para recuperar datos del Portapapeles en un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="a6f80-126">To retrieve data from the Clipboard in a custom format</span></span>  
  
1.  <span data-ttu-id="a6f80-127">Use la <xref:System.Windows.Forms.Clipboard.GetData%2A> método con un nombre de formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="a6f80-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="a6f80-128">Este método solo está disponible en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6f80-128">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="a6f80-129">También puede utilizar nombres de formato predefinidos con el <xref:System.Windows.Forms.Clipboard.SetData%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a6f80-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="a6f80-130">Para obtener más información, consulta <xref:System.Windows.Forms.DataFormats>.</span><span class="sxs-lookup"><span data-stu-id="a6f80-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="a6f80-131">Para recuperar datos desde el Portapapeles en varios formatos</span><span class="sxs-lookup"><span data-stu-id="a6f80-131">To retrieve data from the Clipboard in multiple formats</span></span>  
  
1.  <span data-ttu-id="a6f80-132">Utilice el método <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6f80-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="a6f80-133">Debe usar este método para recuperar datos del Portapapeles en versiones anteriores a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6f80-133">You must use this method to retrieve data from the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="a6f80-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6f80-134">See Also</span></span>  
 [<span data-ttu-id="a6f80-135">Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="a6f80-135">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [<span data-ttu-id="a6f80-136">Agregar datos al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="a6f80-136">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
