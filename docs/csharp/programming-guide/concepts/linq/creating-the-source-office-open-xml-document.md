---
title: Crear el documento de origen de Office Open XML (C#)
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: d6c4d8866bba58e86735099a62041894a9faa9b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204160"
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="65462-102">Crear el documento de origen de Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="65462-102">Creating the Source Office Open XML Document (C#)</span></span>

<span data-ttu-id="65462-103">En este tema se muestra cómo crear el documento WordprocessingML XML abierto de Office que usan los otros ejemplos de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="65462-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="65462-104">Si sigue estas instrucciones, su resultado coincidirá con el resultado proporcionado en cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="65462-104">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="65462-105">No obstante, los ejemplos de este tutorial funcionarán con cualquier documento WordprocessingML válido.</span><span class="sxs-lookup"><span data-stu-id="65462-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="65462-106">Para crear el documento que se usa en este tutorial, debe tener Microsoft Office 2007 o posterior instalado o bien tener Microsoft Office 2003 con el paquete de compatibilidad de Microsoft Office para formatos de archivo de Word, Excel y PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="65462-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="65462-107">Crear el documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="65462-107">Creating the WordprocessingML Document</span></span>

#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="65462-108">Para crear el documento WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="65462-108">To create the WordprocessingML document</span></span>

1. <span data-ttu-id="65462-109">Cree un nuevo documento de Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="65462-109">Create a new Microsoft Word document.</span></span>

2. <span data-ttu-id="65462-110">Pegue el siguiente texto en el nuevo documento:</span><span class="sxs-lookup"><span data-stu-id="65462-110">Paste the following text into the new document:</span></span>

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

3. <span data-ttu-id="65462-111">Dé formato a la primera línea con el estilo "Título 1".</span><span class="sxs-lookup"><span data-stu-id="65462-111">Format the first line with the style "Heading 1".</span></span>

4. <span data-ttu-id="65462-112">Seleccione las líneas que contienen el código C#.</span><span class="sxs-lookup"><span data-stu-id="65462-112">Select the lines that contain the C# code.</span></span> <span data-ttu-id="65462-113">La primera línea empieza con la palabra clave `using`.</span><span class="sxs-lookup"><span data-stu-id="65462-113">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="65462-114">La última línea es la última llave de cierre.</span><span class="sxs-lookup"><span data-stu-id="65462-114">The last line is the last closing brace.</span></span> <span data-ttu-id="65462-115">Dé formato a las líneas con la fuente Courier.</span><span class="sxs-lookup"><span data-stu-id="65462-115">Format the lines with the courier font.</span></span> <span data-ttu-id="65462-116">Déles formato con un nuevo estilo y llame a ese nuevo estilo "Code".</span><span class="sxs-lookup"><span data-stu-id="65462-116">Format them with a new style, and name the new style "Code".</span></span>

5. <span data-ttu-id="65462-117">Finalmente, seleccione toda la línea que contiene el resultado y déle formato con el estilo `Code`.</span><span class="sxs-lookup"><span data-stu-id="65462-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>

6. <span data-ttu-id="65462-118">Guarde el documento y déle el nombre SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="65462-118">Save the document, and name it SampleDoc.docx.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65462-119">Si está usando Microsoft Word 2003, seleccione **Documento de Word 2007** en la lista desplegable **Guardar como tipo**.</span><span class="sxs-lookup"><span data-stu-id="65462-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>
