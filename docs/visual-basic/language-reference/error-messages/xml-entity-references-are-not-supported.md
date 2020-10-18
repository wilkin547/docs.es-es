---
title: No se admiten referencias de entidad XML
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 37e72dbd6de61a50b4192a0151db40cb4be49d1c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163277"
---
# <a name="bc31180-xml-entity-references-are-not-supported"></a>BC31180: no se admiten referencias de entidad XML

Una referencia de entidad (por ejemplo, `©` ) que no se define en la especificación xml 1,0 se incluye como un valor para un literal XML. Solo `&` `"` `<` `>` `'` se admiten las referencias de entidad XML,,, y en los literales XML.

 **Identificador de error:** BC31180

## <a name="to-correct-this-error"></a>Para corregir este error

- Quite la referencia de entidad no admitida.

## <a name="see-also"></a>Vea también

- [Literales XML y la especificación XML 1.0](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [Literales XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
