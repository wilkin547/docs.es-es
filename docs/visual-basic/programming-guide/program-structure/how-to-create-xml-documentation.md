---
title: Procedimiento Crear documentación XML en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 9380c23ab6cfdbecd519926229b45ed863f07f9e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947715"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="f2073-102">Procedimiento Crear documentación XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2073-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="f2073-103">En este ejemplo se muestra cómo agregar comentarios de documentación XML al código.</span><span class="sxs-lookup"><span data-stu-id="f2073-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="f2073-104">Para crear documentación XML para un tipo o miembro</span><span class="sxs-lookup"><span data-stu-id="f2073-104">To create XML documentation for a type or member</span></span>  
  
1. <span data-ttu-id="f2073-105">En el **Editor de código**, coloque el cursor en la línea sobre el tipo o miembro para el que desea crear la documentación.</span><span class="sxs-lookup"><span data-stu-id="f2073-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2. <span data-ttu-id="f2073-106">Escriba `'''` (tres comillas simples).</span><span class="sxs-lookup"><span data-stu-id="f2073-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="f2073-107">En el **Editor de código**se agrega un esqueleto XML para el tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="f2073-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3. <span data-ttu-id="f2073-108">Agregue información descriptiva entre las etiquetas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="f2073-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f2073-109">Si agrega líneas adicionales en el bloque de documentación XML, cada línea debe comenzar por `'''`.</span><span class="sxs-lookup"><span data-stu-id="f2073-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4. <span data-ttu-id="f2073-110">Agregue código adicional que use el tipo o el miembro con los nuevos comentarios de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="f2073-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="f2073-111">IntelliSense muestra el texto de la \<etiqueta de > de resumen para el tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="f2073-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5. <span data-ttu-id="f2073-112">Compile el código para generar un archivo XML que contenga los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="f2073-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="f2073-113">Para obtener más información, vea [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="f2073-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2073-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2073-114">See also</span></span>

- [<span data-ttu-id="f2073-115">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="f2073-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="f2073-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="f2073-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="f2073-117">/doc</span><span class="sxs-lookup"><span data-stu-id="f2073-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
