---
title: La excepción del comentario XML debe tener un &#39;cref&#39; atributo
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785562"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>La excepción del comentario XML debe tener un &#39;cref&#39; atributo
El \<excepción > etiqueta proporciona una manera de documentar las excepciones que se pueden iniciar mediante un método. Necesario `cref` atributo designa el nombre de un miembro, que está activado de forma que el generador de documentación. Si el miembro existe, se traduce en el nombre de elemento canónico en el archivo de documentación.  
  
 **Identificador de error:** BC42319  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Agregar el `cref` atribuir a la excepción como sigue:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
