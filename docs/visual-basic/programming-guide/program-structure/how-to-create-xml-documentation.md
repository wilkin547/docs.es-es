---
title: "Cómo: Crear documentación XML en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 63b6485de5aba2ca49d54a057045bec2062d12dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="31dd2-102">Cómo: Crear documentación XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31dd2-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="31dd2-103">Este ejemplo muestra cómo agregar comentarios de documentación XML en el código.</span><span class="sxs-lookup"><span data-stu-id="31dd2-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="31dd2-104">Para crear documentación XML para un tipo o miembro</span><span class="sxs-lookup"><span data-stu-id="31dd2-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="31dd2-105">En el **Editor de código**, sitúe el cursor en la línea anterior del tipo o miembro para el que desea crear documentación.</span><span class="sxs-lookup"><span data-stu-id="31dd2-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="31dd2-106">Tipo `'''` (tres comillas simples).</span><span class="sxs-lookup"><span data-stu-id="31dd2-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="31dd2-107">Se agrega un esquema XML para el tipo o miembro en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="31dd2-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="31dd2-108">Agregar información descriptiva entre las etiquetas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="31dd2-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31dd2-109">Si agrega líneas adicionales dentro del bloque de documentación XML, cada línea debe comenzar con `'''`.</span><span class="sxs-lookup"><span data-stu-id="31dd2-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="31dd2-110">Agregue código adicional que utiliza el tipo o miembro con los comentarios de documentación XML nuevo.</span><span class="sxs-lookup"><span data-stu-id="31dd2-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="31dd2-111">IntelliSense muestra el texto de la \<resumen > etiqueta para el tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="31dd2-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="31dd2-112">Compile el código para generar un archivo XML que contiene los comentarios de documentación.</span><span class="sxs-lookup"><span data-stu-id="31dd2-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="31dd2-113">Para obtener más información, vea [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="31dd2-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31dd2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="31dd2-114">See Also</span></span>  
 [<span data-ttu-id="31dd2-115">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="31dd2-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="31dd2-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="31dd2-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="31dd2-117">/doc</span><span class="sxs-lookup"><span data-stu-id="31dd2-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
