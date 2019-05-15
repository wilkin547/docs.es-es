---
title: El tipo subyacente <typename> de Enum no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 7d4566637da74726867c55ddf89b965d055e5d14
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589921"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a>El tipo subyacente \<typename > de Enum no es conforme a CLS
El tipo de datos especificado para esta enumeración no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS). No es un error dentro del componente, ya que .NET Framework y Visual Basic admiten este tipo de datos. Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admite este tipo de datos. Es posible que este componente no pueda interactuar correctamente con el componente.  
  
 Los siguientes tipos de datos de Visual Basic no son conformes a CLS:  
  
- [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40032  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si el componente solo con otros componentes de .NET Framework, o no se comunica con otros componentes, no es necesario cambiar nada.  
  
- Si trabaja con un componente no está escrito para .NET Framework, podría ser capaz de determinar mediante la reflexión o de documentación, si es compatible con este tipo de datos. Si es así, no es necesario cambiar nada.  
  
- Si trabaja con un componente que no admite este tipo de datos, debe reemplazar con el tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
- Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos diferente que en .NET Framework. Por ejemplo, `uint` suele ser de 16 bits en otros entornos. Si se pasa un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de Visual Basic.  
  
## <a name="see-also"></a>Vea también

- [Reflexión (Visual Basic)](../../programming-guide/concepts/reflection.md)
- [Reflexión](../../../framework/reflection-and-codedom/reflection.md)
