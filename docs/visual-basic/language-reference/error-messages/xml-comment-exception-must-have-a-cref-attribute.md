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
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813293"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>La excepción del comentario XML debe tener un atributo 'cref'
El \<excepción > etiqueta proporciona una manera de documentar las excepciones que se pueden iniciar mediante un método. Necesario `cref` atributo designa el nombre de un miembro, que está activado de forma que el generador de documentación. Si el miembro existe, se traduce en el nombre de elemento canónico en el archivo de documentación.  
  
 **Identificador de error:** BC42319  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Agregar el `cref` atribuir a la excepción como sigue:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>Vea también

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Cómo: Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
