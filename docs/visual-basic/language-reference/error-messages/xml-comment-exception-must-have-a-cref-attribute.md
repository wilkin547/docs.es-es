---
title: La excepción del comentario XML debe tener un &#39;cref&#39; atributo
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: ee91513ef94e2abbe01d3ac09796b7fdf8e129ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>La excepción del comentario XML debe tener un &#39;cref&#39; atributo
El \<excepción > etiqueta proporciona un medio para documentar las excepciones que se pueden iniciar mediante un método. Requerido `cref` atributo designa el nombre de un miembro, que comprueba el generador de documentación. Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.  
  
 **Id. de error:** BC42319  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Agregar el `cref` atributo a la excepción como sigue:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
