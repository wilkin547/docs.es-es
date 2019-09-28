---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592040"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="a81a8-102">La excepción del comentario XML debe tener un atributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="a81a8-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="a81a8-103">La etiqueta \<exception > proporciona una manera de documentar las excepciones que puede producir un método.</span><span class="sxs-lookup"><span data-stu-id="a81a8-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="a81a8-104">El atributo `cref` necesario designa el nombre de un miembro, que se comprueba en el generador de documentación.</span><span class="sxs-lookup"><span data-stu-id="a81a8-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="a81a8-105">Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.</span><span class="sxs-lookup"><span data-stu-id="a81a8-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="a81a8-106">**IDENTIFICADOR de error:** BC42319</span><span class="sxs-lookup"><span data-stu-id="a81a8-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a81a8-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a81a8-107">To correct this error</span></span>  
  
- <span data-ttu-id="a81a8-108">Agregue el atributo `cref` a la excepción como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a81a8-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    <span data-ttu-id="a81a8-109">xml</span><span class="sxs-lookup"><span data-stu-id="a81a8-109">xml</span></span>  
    <span data-ttu-id="a81a8-110"><exception cref="member">Descripción</exception> de ' ' '</span><span class="sxs-lookup"><span data-stu-id="a81a8-110">'''<exception cref="member">description</exception></span></span>  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
