---
title: El tipo de miembro '<membername>' no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 03962a3004b975dec86099307346aa5cc8829020
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664285"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a>Tipo de miembro '\<membername >' no es conforme a CLS
El tipo de datos especificado para este miembro no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS). Esto no es un error en su componente, porque el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y Visual Basic admite este tipo de datos. Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admite este tipo de datos. Es posible que este componente no pueda interactuar correctamente con el componente.  
  
 Los siguientes tipos de datos de Visual Basic no son conformes a CLS:  
  
- [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si el componente interactúa con otros [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componentes o no se comunica con otros componentes, no es necesario cambiar nada.  
  
- Si trabaja con un componente no está escrito para la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], es posible que pueda determinar, ya sea mediante reflexión o de documentación, si admite este tipo de datos. Si es así, no es necesario cambiar nada.  
  
- Si trabaja con un componente que no admite este tipo de datos, debe reemplazar con el tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
- Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Por ejemplo, `uint` suele ser de 16 bits en otros entornos. Si se pasa un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de Visual Basic.  
  
## <a name="see-also"></a>Vea también

- [Reflexión](../../../framework/reflection-and-codedom/reflection.md)
