---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321173"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>La excepción del comentario XML debe tener un atributo 'cref'

La etiqueta \<exception > proporciona una manera de documentar las excepciones que puede producir un método. El atributo `cref` necesario designa el nombre de un miembro, que se comprueba en el generador de documentación. Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.

**Identificador de error:** BC42319

## <a name="to-correct-this-error"></a>Para corregir este error

Agregue el atributo `cref` a la excepción como se indica a continuación:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Vea también

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
