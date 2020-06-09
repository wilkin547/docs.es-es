---
title: Documentar el código con XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: f391fb909cfe4de8f27afb24d6db389e2c8cdfae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590934"
---
# <a name="document-your-code-with-xml-visual-basic"></a><span data-ttu-id="5bb7a-102">Documentar el código con XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bb7a-102">Document your code with XML (Visual Basic)</span></span>

<span data-ttu-id="5bb7a-103">En Visual Basic, puede documentar el código mediante XML.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-103">In Visual Basic, you can document your code using XML.</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="5bb7a-104">Comentarios de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="5bb7a-104">XML documentation comments</span></span>

<span data-ttu-id="5bb7a-105">Visual Basic proporciona una manera sencilla de crear automáticamente documentación XML para los proyectos de.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="5bb7a-106">Puede generar automáticamente un esqueleto XML para los tipos y miembros y, a continuación, proporcionar resúmenes, documentación descriptiva para cada parámetro y otros comentarios.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="5bb7a-107">Con la configuración adecuada, la documentación XML se emite automáticamente en un archivo XML con el mismo nombre de archivo raíz que el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same root file name as your project.</span></span> <span data-ttu-id="5bb7a-108">Para obtener más información, vea [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="5bb7a-108">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="5bb7a-109">El archivo XML se puede consumir o manipular de otra manera como XML.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="5bb7a-110">Este archivo se encuentra en el mismo directorio que el archivo. exe o. dll de salida del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="5bb7a-111">La documentación XML comienza con `'''` .</span><span class="sxs-lookup"><span data-stu-id="5bb7a-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="5bb7a-112">El procesamiento de estos comentarios tiene algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="5bb7a-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="5bb7a-113">La documentación debe ser XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="5bb7a-114">Si el código XML no es correcto, se genera una advertencia y el archivo de documentación contiene un comentario que indica que se ha detectado un error.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="5bb7a-115">Los desarrolladores pueden crear su propio conjunto de etiquetas,</span><span class="sxs-lookup"><span data-stu-id="5bb7a-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="5bb7a-116">Hay un conjunto recomendado de etiquetas (consulte [etiquetas de comentario XML](../../language-reference/xmldoc/index.md)).</span><span class="sxs-lookup"><span data-stu-id="5bb7a-116">There is a recommended set of tags (see [XML Comment Tags](../../language-reference/xmldoc/index.md)).</span></span> <span data-ttu-id="5bb7a-117">Algunas de las etiquetas recomendadas tienen significados especiales:</span><span class="sxs-lookup"><span data-stu-id="5bb7a-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="5bb7a-118">La \<param> etiqueta se usa para describir los parámetros.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="5bb7a-119">Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="5bb7a-120">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="5bb7a-121">El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="5bb7a-122">El compilador comprueba si existe este elemento de código.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="5bb7a-123">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="5bb7a-124">El compilador también respeta cualquier `Imports` instrucción al buscar un tipo descrito en el `cref` atributo.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="5bb7a-125">\<summary>IntelliSense usa la etiqueta en Visual Studio para mostrar información adicional sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="5bb7a-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="5bb7a-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5bb7a-126">Related sections</span></span>

<span data-ttu-id="5bb7a-127">Para obtener más información sobre cómo crear un archivo XML con comentarios de documentación, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5bb7a-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="5bb7a-128">-doc</span><span class="sxs-lookup"><span data-stu-id="5bb7a-128">-doc</span></span>](../../reference/command-line-compiler/doc.md)

- [<span data-ttu-id="5bb7a-129">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="5bb7a-129">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)

- [<span data-ttu-id="5bb7a-130">Procesar el archivo XML</span><span class="sxs-lookup"><span data-stu-id="5bb7a-130">Processing the XML File</span></span>](processing-the-xml-file.md)

- [<span data-ttu-id="5bb7a-131">Procedimiento para crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="5bb7a-131">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)

- [<span data-ttu-id="5bb7a-132">Herramientas XML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5bb7a-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="5bb7a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bb7a-133">See also</span></span>

- [<span data-ttu-id="5bb7a-134">Desarrollo de aplicaciones con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5bb7a-134">Developing Applications with Visual Basic</span></span>](../../developing-apps/index.md)
- [<span data-ttu-id="5bb7a-135">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5bb7a-135">Visual Basic Programming Guide</span></span>](../index.md)
