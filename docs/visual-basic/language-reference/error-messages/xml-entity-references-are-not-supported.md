---
description: 'Más información acerca de: BC31180: no se admiten las referencias de entidad XML'
title: No se admiten referencias de entidad XML
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: c45202fbd97d2343caf6bf4cdccf9368d0a7a295
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701422"
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
