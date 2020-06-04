---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406513"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>La excepción del comentario XML debe tener un atributo 'cref'

La \<exception> etiqueta proporciona una manera de documentar las excepciones que puede producir un método. El atributo required `cref` designa el nombre de un miembro, que está protegido por el generador de documentación. Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.

**Identificador de error:** BC42319

## <a name="to-correct-this-error"></a>Para corregir este error

Agregue el `cref` atributo a la excepción como se indica a continuación:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Consulte también

- [\<exception>](../xmldoc/exception.md)
- [Procedimiento para crear documentación XML](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Etiquetas de comentario XML](../xmldoc/index.md)
