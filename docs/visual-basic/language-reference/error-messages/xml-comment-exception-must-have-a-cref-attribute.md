---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a974df5d2305b88946981d0d258a8088b23d3fc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766615"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="064d5-102">La excepción del comentario XML debe tener un atributo 'cref'</span><span class="sxs-lookup"><span data-stu-id="064d5-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="064d5-103">El \<excepción > etiqueta proporciona una manera de documentar las excepciones que se pueden iniciar mediante un método.</span><span class="sxs-lookup"><span data-stu-id="064d5-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="064d5-104">Necesario `cref` atributo designa el nombre de un miembro, que está activado de forma que el generador de documentación.</span><span class="sxs-lookup"><span data-stu-id="064d5-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="064d5-105">Si el miembro existe, se traduce en el nombre de elemento canónico en el archivo de documentación.</span><span class="sxs-lookup"><span data-stu-id="064d5-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="064d5-106">**Identificador de error:** BC42319</span><span class="sxs-lookup"><span data-stu-id="064d5-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="064d5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="064d5-107">To correct this error</span></span>  
  
- <span data-ttu-id="064d5-108">Agregar el `cref` atribuir a la excepción como sigue:</span><span class="sxs-lookup"><span data-stu-id="064d5-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="064d5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="064d5-109">See also</span></span>

- [<span data-ttu-id="064d5-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="064d5-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="064d5-111">Cómo: Crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="064d5-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="064d5-112">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="064d5-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
