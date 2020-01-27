---
title: 'Cómo: extraer el icono asociado a un archivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742544"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="ace1a-102">Cómo: Extraer el icono asociado a un archivo en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ace1a-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="ace1a-103">Muchos archivos tienen iconos incrustados que proporcionan una representación visual del tipo de archivo asociado.</span><span class="sxs-lookup"><span data-stu-id="ace1a-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="ace1a-104">Por ejemplo, los documentos de Microsoft Word contienen un icono que los identifica como documentos de Word.</span><span class="sxs-lookup"><span data-stu-id="ace1a-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="ace1a-105">Al mostrar archivos en un control de lista o en un control de tabla, puede que desee mostrar el icono que representa el tipo de archivo junto a cada nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ace1a-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="ace1a-106">Puede hacerlo fácilmente con el método <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="ace1a-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ace1a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ace1a-107">Example</span></span>  
 <span data-ttu-id="ace1a-108">En el ejemplo de código siguiente se muestra cómo extraer el icono asociado a un archivo y mostrar el nombre de archivo y su icono asociado en un control de <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="ace1a-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ace1a-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ace1a-109">Compiling the Code</span></span>  
 <span data-ttu-id="ace1a-110">Para compilar el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ace1a-110">To compile the example:</span></span>  
  
- <span data-ttu-id="ace1a-111">Pegue el código anterior en un Windows Form y llame al método `ExtractAssociatedIconExample` desde el constructor del formulario o <xref:System.Windows.Forms.Form.Load> método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="ace1a-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="ace1a-112">Tendrá que asegurarse de que el formulario importa el espacio de nombres <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="ace1a-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace1a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ace1a-113">See also</span></span>

- [<span data-ttu-id="ace1a-114">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="ace1a-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="ace1a-115">ListView (control)</span><span class="sxs-lookup"><span data-stu-id="ace1a-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
