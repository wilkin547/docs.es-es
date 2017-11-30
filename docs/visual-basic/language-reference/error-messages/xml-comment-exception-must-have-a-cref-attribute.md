---
title: "La excepción del comentario XML debe tener un &#39; cref &#39; atributo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords: BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c22c9cd9415faf17d027c3751d166662a92b50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="41c78-102">La excepción del comentario XML debe tener un &#39; cref &#39; atributo</span><span class="sxs-lookup"><span data-stu-id="41c78-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="41c78-103">El \<excepción > etiqueta proporciona un medio para documentar las excepciones que se pueden iniciar mediante un método.</span><span class="sxs-lookup"><span data-stu-id="41c78-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="41c78-104">Requerido `cref` atributo designa el nombre de un miembro, que comprueba el generador de documentación.</span><span class="sxs-lookup"><span data-stu-id="41c78-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="41c78-105">Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.</span><span class="sxs-lookup"><span data-stu-id="41c78-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="41c78-106">**Id. de error:** BC42319</span><span class="sxs-lookup"><span data-stu-id="41c78-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41c78-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="41c78-107">To correct this error</span></span>  
  
-   <span data-ttu-id="41c78-108">Agregar el `cref` atributo a la excepción como sigue:</span><span class="sxs-lookup"><span data-stu-id="41c78-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="41c78-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="41c78-109">See Also</span></span>  
 [<span data-ttu-id="41c78-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="41c78-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="41c78-111">Crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="41c78-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="41c78-112">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="41c78-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
