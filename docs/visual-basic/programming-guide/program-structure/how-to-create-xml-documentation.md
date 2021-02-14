---
description: 'Más información acerca de cómo: crear documentación XML en Visual Basic'
title: Procedimiento para crear documentación XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: d54c79d820a170b246e5c85d7562487fbe66f39c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475960"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="52c0a-103">Cómo: Crear documentación XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52c0a-103">How to: Create XML Documentation in Visual Basic</span></span>

<span data-ttu-id="52c0a-104">En este ejemplo se muestra cómo agregar comentarios de documentación XML al código.</span><span class="sxs-lookup"><span data-stu-id="52c0a-104">This example shows how to add XML documentation comments to your code.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="52c0a-105">Para crear documentación XML para un tipo o miembro</span><span class="sxs-lookup"><span data-stu-id="52c0a-105">To create XML documentation for a type or member</span></span>

1. <span data-ttu-id="52c0a-106">En el **Editor de código**, coloque el cursor en la línea sobre el tipo o miembro para el que desea crear la documentación.</span><span class="sxs-lookup"><span data-stu-id="52c0a-106">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>

2. <span data-ttu-id="52c0a-107">Escriba `'''` (tres comillas simples).</span><span class="sxs-lookup"><span data-stu-id="52c0a-107">Type `'''` (three single-quotation marks).</span></span>

    <span data-ttu-id="52c0a-108">En el **Editor de código** se agrega un esqueleto XML para el tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="52c0a-108">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>

3. <span data-ttu-id="52c0a-109">Agregue información descriptiva entre las etiquetas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="52c0a-109">Add descriptive information between the appropriate tags.</span></span>

    > [!NOTE]
    > <span data-ttu-id="52c0a-110">Si agrega líneas adicionales en el bloque de documentación XML, cada línea debe comenzar por `'''` .</span><span class="sxs-lookup"><span data-stu-id="52c0a-110">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>

4. <span data-ttu-id="52c0a-111">Agregue código adicional que use el tipo o el miembro con los nuevos comentarios de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="52c0a-111">Add additional code that uses the type or member with the new XML documentation comments.</span></span>

    <span data-ttu-id="52c0a-112">IntelliSense muestra el texto de la \<summary> etiqueta para el tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="52c0a-112">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>

5. <span data-ttu-id="52c0a-113">Compile el código para generar un archivo XML que contenga los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="52c0a-113">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="52c0a-114">Para obtener más información, vea [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="52c0a-114">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52c0a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="52c0a-115">See also</span></span>

- [<span data-ttu-id="52c0a-116">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="52c0a-116">Documenting Your Code with XML</span></span>](documenting-your-code-with-xml.md)
- [<span data-ttu-id="52c0a-117">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="52c0a-117">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)
- [<span data-ttu-id="52c0a-118">-doc</span><span class="sxs-lookup"><span data-stu-id="52c0a-118">-doc</span></span>](../../reference/command-line-compiler/doc.md)
