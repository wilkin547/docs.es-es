---
title: El tipo subyacente <typename> de Enum no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 79faf0038b2b313bdc21e12c8ae76854bcd6957f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406578"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a>El tipo subyacente \<typename> de Enum no es compatible con CLS
El tipo de datos especificado para esta enumeración no forma parte de la [independencia del lenguaje y de los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS). Esto no es un error en el componente, porque el .NET Framework y Visual Basic admiten este tipo de datos. Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admita este tipo de datos. Tal componente podría no ser capaz de interactuar correctamente con el componente.  
  
 Los siguientes tipos de datos de Visual Basic no son conformes a CLS:  
  
- [Tipo de datos SByte](../data-types/sbyte-data-type.md)  
  
- [Tipo de datos UInteger](../data-types/uinteger-data-type.md)  
  
- [Tipo de datos ULong](../data-types/ulong-data-type.md)  
  
- [Tipo de datos UShort](../data-types/ushort-data-type.md)  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40032  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si el componente interactúa únicamente con otros componentes de .NET Framework, o no interactúa con ningún otro componente, no es necesario cambiar nada.  
  
- Si interactúa con un componente que no está escrito para el .NET Framework, es posible que pueda determinar, ya sea a través de la reflexión o desde la documentación, si admite este tipo de datos. En caso contrario, no es necesario cambiar nada.  
  
- Si interactúa con un componente que no admite este tipo de datos, debe reemplazarlo por el tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
- Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework. Por ejemplo, `uint` suele ser de 16 bits en otros entornos. Si va a pasar un argumento de 16 bits a este componente, declárelo como `UShort` en lugar de `UInteger` en el código de Visual Basic administrado.  
  
## <a name="see-also"></a>Consulte también

- [Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md) (Reflexión [Visual Basic])
- [Reflexión](../../../framework/reflection-and-codedom/reflection.md)
