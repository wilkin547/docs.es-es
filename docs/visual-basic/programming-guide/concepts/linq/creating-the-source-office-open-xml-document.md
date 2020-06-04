---
title: Crear el documento de origen de Office Open XML
ms.date: 07/20/2015
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
ms.openlocfilehash: 9f44c8d0f4080224c461736fdbdf3acd854e4a89
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410843"
---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a><span data-ttu-id="db5a8-102">Crear el documento de origen de Office Open XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db5a8-102">Creating the Source Office Open XML Document (Visual Basic)</span></span>
<span data-ttu-id="db5a8-103">En este tema se muestra cómo crear el documento WordprocessingML XML abierto de Office que usan los otros ejemplos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="db5a8-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="db5a8-104">Si sigue estas instrucciones, su resultado coincidirá con el resultado proporcionado en cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="db5a8-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="db5a8-105">No obstante, los ejemplos de este tutorial funcionarán con cualquier documento WordprocessingML válido.</span><span class="sxs-lookup"><span data-stu-id="db5a8-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="db5a8-106">Para crear el documento que se usa en este tutorial, debe tener Microsoft Office 2007 o posterior instalado o bien tener Microsoft Office 2003 con el paquete de compatibilidad de Microsoft Office para formatos de archivo de Word, Excel y PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="db5a8-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="db5a8-107">Crear el documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="db5a8-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="db5a8-108">Para crear el documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="db5a8-108">To create the WordprocessingML document</span></span>  
  
1. <span data-ttu-id="db5a8-109">Cree un nuevo documento de Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="db5a8-109">Create a new Microsoft Word document.</span></span>  
  
2. <span data-ttu-id="db5a8-110">Pegue el siguiente texto en el nuevo documento:</span><span class="sxs-lookup"><span data-stu-id="db5a8-110">Paste the following text into the new document:</span></span>  
  
    ```text  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3. <span data-ttu-id="db5a8-111">Dé formato a la primera línea con el estilo "Título 1".</span><span class="sxs-lookup"><span data-stu-id="db5a8-111">Format the first line with the style "Heading 1".</span></span>  
  
4. <span data-ttu-id="db5a8-112">Seleccione las líneas que contienen el código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="db5a8-112">Select the lines that contain the Visual Basic code.</span></span> <span data-ttu-id="db5a8-113">La primera línea empieza con la palabra clave `Imports`.</span><span class="sxs-lookup"><span data-stu-id="db5a8-113">The first line starts with the `Imports` keyword.</span></span> <span data-ttu-id="db5a8-114">La última línea es "End Class".</span><span class="sxs-lookup"><span data-stu-id="db5a8-114">The last line is "End Class".</span></span> <span data-ttu-id="db5a8-115">Dé formato a las líneas con la fuente Courier.</span><span class="sxs-lookup"><span data-stu-id="db5a8-115">Format the lines with the courier font.</span></span> <span data-ttu-id="db5a8-116">Déles formato con un nuevo estilo y llame a ese nuevo estilo "Code".</span><span class="sxs-lookup"><span data-stu-id="db5a8-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5. <span data-ttu-id="db5a8-117">Finalmente, seleccione toda la línea que contiene el resultado y déle formato con el estilo `Code`.</span><span class="sxs-lookup"><span data-stu-id="db5a8-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6. <span data-ttu-id="db5a8-118">Guarde el documento y déle el nombre SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="db5a8-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="db5a8-119">Si está usando Microsoft Word 2003, seleccione **Documento de Word 2007** en la lista desplegable **Guardar como tipo**.</span><span class="sxs-lookup"><span data-stu-id="db5a8-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db5a8-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db5a8-120">See also</span></span>

- [<span data-ttu-id="db5a8-121">Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db5a8-121">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
