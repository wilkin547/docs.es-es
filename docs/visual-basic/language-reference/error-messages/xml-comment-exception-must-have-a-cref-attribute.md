---
description: "Más información sobre: BC42319: la excepción de comentario XML debe tener un atributo ' CREF '"
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: e602a2973d95f70d5ab532e6be319a9575d239a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701461"
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
