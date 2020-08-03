---
title: Crear el documento de origen de Office Open XML (C#)
description: Cree un documento WordprocessingML de Office Open XML para usarlo con tutoriales de C#. En este artículo se requiere Microsoft Office.
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: e6d6908ee6560218793454f3871705e74095f543
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103998"
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="107ae-104">Crear el documento de origen de Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="107ae-104">Creating the Source Office Open XML Document (C#)</span></span>

<span data-ttu-id="107ae-105">En este tema se muestra cómo crear el documento WordprocessingML XML abierto de Office que usan los otros ejemplos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="107ae-105">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="107ae-106">Si sigue estas instrucciones, su resultado coincidirá con el resultado proporcionado en cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="107ae-106">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="107ae-107">No obstante, los ejemplos de este tutorial funcionarán con cualquier documento WordprocessingML válido.</span><span class="sxs-lookup"><span data-stu-id="107ae-107">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="107ae-108">Para crear el documento que se usa en este tutorial, debe tener Microsoft Office 2007 o posterior instalado o bien tener Microsoft Office 2003 con el paquete de compatibilidad de Microsoft Office para formatos de archivo de Word, Excel y PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="107ae-108">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="107ae-109">Crear el documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="107ae-109">Creating the WordprocessingML Document</span></span>

#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="107ae-110">Para crear el documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="107ae-110">To create the WordprocessingML document</span></span>

1. <span data-ttu-id="107ae-111">Cree un nuevo documento de Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="107ae-111">Create a new Microsoft Word document.</span></span>

2. <span data-ttu-id="107ae-112">Pegue el siguiente texto en el nuevo documento:</span><span class="sxs-lookup"><span data-stu-id="107ae-112">Paste the following text into the new document:</span></span>

    ```text
    Parsing WordprocessingML with LINQ to XML

    The following example prints to the console.

    using System;

    class Program {
        public static void Main(string[] args) {
            Console.WriteLine("Hello World");
        }
    }

    This example produces the following output:

    Hello World
    ```

3. <span data-ttu-id="107ae-113">Dé formato a la primera línea con el estilo "Título 1".</span><span class="sxs-lookup"><span data-stu-id="107ae-113">Format the first line with the style "Heading 1".</span></span>

4. <span data-ttu-id="107ae-114">Seleccione las líneas que contienen el código C#.</span><span class="sxs-lookup"><span data-stu-id="107ae-114">Select the lines that contain the C# code.</span></span> <span data-ttu-id="107ae-115">La primera línea empieza con la palabra clave `using`.</span><span class="sxs-lookup"><span data-stu-id="107ae-115">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="107ae-116">La última línea es la última llave de cierre.</span><span class="sxs-lookup"><span data-stu-id="107ae-116">The last line is the last closing brace.</span></span> <span data-ttu-id="107ae-117">Dé formato a las líneas con la fuente Courier.</span><span class="sxs-lookup"><span data-stu-id="107ae-117">Format the lines with the courier font.</span></span> <span data-ttu-id="107ae-118">Déles formato con un nuevo estilo y llame a ese nuevo estilo "Code".</span><span class="sxs-lookup"><span data-stu-id="107ae-118">Format them with a new style, and name the new style "Code".</span></span>

5. <span data-ttu-id="107ae-119">Finalmente, seleccione toda la línea que contiene el resultado y déle formato con el estilo `Code`.</span><span class="sxs-lookup"><span data-stu-id="107ae-119">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>

6. <span data-ttu-id="107ae-120">Guarde el documento y déle el nombre SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="107ae-120">Save the document, and name it SampleDoc.docx.</span></span>

    > [!NOTE]
    > <span data-ttu-id="107ae-121">Si está usando Microsoft Word 2003, seleccione **Documento de Word 2007** en la lista desplegable **Guardar como tipo**.</span><span class="sxs-lookup"><span data-stu-id="107ae-121">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>
