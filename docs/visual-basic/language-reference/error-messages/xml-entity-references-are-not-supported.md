---
title: No se admiten referencias de entidad XML
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 02620b5b4a33fcfcdecd8c9152106262df252c85
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662567"
---
# <a name="xml-entity-references-are-not-supported"></a>No se admiten referencias de entidad XML
Una referencia de entidad (por ejemplo, `©`) que no está definido en el XML 1.0 specification se incluye como un valor de un literal XML. Solo `&`, `"`, `<`, `>`, y `'` se admiten referencias de entidad XML en literales XML.  
  
 **Identificador de error:** BC31180  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite la referencia de entidad no admitido.  
  
## <a name="see-also"></a>Vea también

- [Literales XML y la especificación XML 1.0](../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
