---
title: Procedimiento para extraer el icono asociado a un archivo en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: c3173a3fa756a3294154217f5cf0a13dbc8721f3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645398"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="668ff-102">Procedimiento para extraer el icono asociado a un archivo en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="668ff-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="668ff-103">Muchos archivos tienen iconos incrustados que proporcionan una representación visual del tipo de archivo asociado.</span><span class="sxs-lookup"><span data-stu-id="668ff-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="668ff-104">Por ejemplo, documentos de Microsoft Word contienen un icono que se identifica como documentos de Word.</span><span class="sxs-lookup"><span data-stu-id="668ff-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="668ff-105">Al mostrar los archivos en un control de lista o tabla, desea mostrar el icono que representa el tipo de archivo junto a cada nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="668ff-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="668ff-106">Puede hacerlo fácilmente utilizando el <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> método.</span><span class="sxs-lookup"><span data-stu-id="668ff-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="668ff-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="668ff-107">Example</span></span>  
 <span data-ttu-id="668ff-108">En el ejemplo de código siguiente se muestra cómo extraer el icono asociado a un archivo y mostrar el nombre de archivo y el icono asociado en un <xref:System.Windows.Forms.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="668ff-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="668ff-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="668ff-109">Compiling the Code</span></span>  
 <span data-ttu-id="668ff-110">Para compilar el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="668ff-110">To compile the example:</span></span>  
  
- <span data-ttu-id="668ff-111">Pegue el código anterior en un formulario de Windows y llaman a la `ExtractAssociatedIconExample` método desde el constructor del formulario o <xref:System.Windows.Forms.Form.Load> el método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="668ff-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="668ff-112">Deberá asegurarse de que el formulario se importa el <xref:System.IO> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="668ff-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668ff-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="668ff-113">See also</span></span>

- [<span data-ttu-id="668ff-114">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="668ff-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="668ff-115">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="668ff-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
