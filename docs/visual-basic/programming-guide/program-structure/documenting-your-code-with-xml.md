---
title: Documentar el código con XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d132fa514008d072158a0e6bedaff511c55b18c0
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="81e9e-102">Documentar el código con XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81e9e-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="81e9e-103">En Visual Basic, puede documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="81e9e-103">In Visual Basic, you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="81e9e-104">Comentarios de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="81e9e-104">XML Documentation Comments</span></span>  
 <span data-ttu-id="81e9e-105">Visual Basic proporciona una manera sencilla para crear automáticamente documentación XML para los proyectos.</span><span class="sxs-lookup"><span data-stu-id="81e9e-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="81e9e-106">Puede generar automáticamente un esquema XML para los tipos y miembros y, a continuación, proporcionar resúmenes, documentación descriptiva para cada parámetro y otros comentarios.</span><span class="sxs-lookup"><span data-stu-id="81e9e-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="81e9e-107">Con la configuración apropiada, la documentación XML se emite automáticamente en un archivo XML con el mismo nombre que el proyecto y la extensión .xml.</span><span class="sxs-lookup"><span data-stu-id="81e9e-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="81e9e-108">Para obtener más información, vea [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="81e9e-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="81e9e-109">El archivo XML puede ser consumido o manipularse como XML.</span><span class="sxs-lookup"><span data-stu-id="81e9e-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="81e9e-110">Este archivo se encuentra en el mismo directorio que el archivo de salida .exe o .dll del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81e9e-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="81e9e-111">Documentación XML empieza con `'''`.</span><span class="sxs-lookup"><span data-stu-id="81e9e-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="81e9e-112">El procesamiento de estos comentarios tiene algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="81e9e-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="81e9e-113">La documentación debe ser XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="81e9e-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="81e9e-114">Si el código XML no está bien formado, se genera una advertencia y el archivo de documentación contiene un comentario que indica que se detectó un error.</span><span class="sxs-lookup"><span data-stu-id="81e9e-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="81e9e-115">Los desarrolladores pueden crear su propio conjunto de etiquetas,</span><span class="sxs-lookup"><span data-stu-id="81e9e-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="81e9e-116">Hay un conjunto recomendado de etiquetas (vea "Secciones relacionadas" en este tema).</span><span class="sxs-lookup"><span data-stu-id="81e9e-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="81e9e-117">Algunas de las etiquetas recomendadas tienen significados especiales:</span><span class="sxs-lookup"><span data-stu-id="81e9e-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="81e9e-118">La etiqueta \<param> se usa para describir parámetros.</span><span class="sxs-lookup"><span data-stu-id="81e9e-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="81e9e-119">Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación.</span><span class="sxs-lookup"><span data-stu-id="81e9e-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="81e9e-120">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="81e9e-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="81e9e-121">El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código.</span><span class="sxs-lookup"><span data-stu-id="81e9e-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="81e9e-122">El compilador comprueba que existe este elemento de código.</span><span class="sxs-lookup"><span data-stu-id="81e9e-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="81e9e-123">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="81e9e-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="81e9e-124">El compilador también respeta cualquier `Imports` instrucciones cuando se busca un tipo descrito en el `cref` atributo.</span><span class="sxs-lookup"><span data-stu-id="81e9e-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="81e9e-125">El \<resumen > etiqueta se usa por IntelliSense en Visual Studio para mostrar información adicional sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="81e9e-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="81e9e-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="81e9e-126">Related Sections</span></span>  
 <span data-ttu-id="81e9e-127">Para obtener más información sobre cómo crear un archivo XML con los comentarios de documentación, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="81e9e-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="81e9e-128">/doc</span><span class="sxs-lookup"><span data-stu-id="81e9e-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="81e9e-129">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="81e9e-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="81e9e-130">Procesamiento del archivo XML</span><span class="sxs-lookup"><span data-stu-id="81e9e-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="81e9e-131">Crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="81e9e-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="81e9e-132">Herramientas XML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="81e9e-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="81e9e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="81e9e-133">See Also</span></span>  
 [<span data-ttu-id="81e9e-134">Desarrollo de aplicaciones con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81e9e-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)  
 [<span data-ttu-id="81e9e-135">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81e9e-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
