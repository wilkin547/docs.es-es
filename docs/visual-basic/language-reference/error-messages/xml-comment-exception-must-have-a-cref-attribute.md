---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 18e7aa5f6905eaa9c509aa21fe6f5bfcd54d46f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163303"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a>BC42319: la excepción de comentario XML debe tener un atributo ' CREF '

La \<exception> etiqueta proporciona una manera de documentar las excepciones que puede producir un método. El atributo required `cref` designa el nombre de un miembro, que está protegido por el generador de documentación. Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.

**Identificador de error:** BC42319

## <a name="to-correct-this-error"></a>Para corregir este error

Agregue el `cref` atributo a la excepción como se indica a continuación:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>Vea también

- [\<exception>](../xmldoc/exception.md)
- [Procedimiento para crear documentación XML](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Etiquetas de comentario XML](../xmldoc/index.md)
