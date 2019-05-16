---
title: El tipo <typename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 2805cac71cb36d21f5ab21a5875183803d07a4b4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642366"
---
# <a name="type-typename-is-not-cls-compliant"></a>Tipo \<typename > no es conforme a CLS
Una variable, propiedad o valor devuelto de función se declara con un tipo de datos que no es conforme a CLS.  
  
 Para una aplicación sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), debe utilizar solo tipos conformes a CLS.  
  
 Los siguientes tipos de datos de Visual Basic no son conformes a CLS:  
  
- [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **Identificador de error:** BC40041  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si la aplicación debe ser conforme a CLS, cambie el tipo de datos de este elemento para el tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
- Si la aplicación no necesita ser compatible con CLS, no es necesario cambiar nada. Sin embargo debe ser consciente de que no.
