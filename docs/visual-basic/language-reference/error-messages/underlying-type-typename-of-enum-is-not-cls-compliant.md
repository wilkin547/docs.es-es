---
title: "Tipo subyacente &lt;typename&gt; de enumeración no es compatible con CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e054f8d992154f66ab1d48a477a7e04900aa5b4d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a>Tipo subyacente &lt;typename&gt; de enumeración no es compatible con CLS
El tipo de datos especificado para esta enumeración no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS). Esto no es un error dentro de un componente, porque la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] admiten este tipo de datos. Sin embargo, otro componente escrito en código estrictamente conforme a CLS podría no admitir este tipo de datos. Posible que un componente de ese tipo no pueda interactuar correctamente con su componente.  
  
 Los siguientes tipos de datos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no son conformes con CLS:  
  
-   [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40032  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si el componente se comunica solo con otros [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componentes o no interactúen con cualquier otro componente, no necesita cambiar nada.  
  
-   Si interactúa con un componente no escrito para el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], es posible que pueda determinar, ya sea mediante reflexión o en documentación, si admite este tipo de datos. Si es así, no es necesario cambiar nada.  
  
-   Si interactúa con un componente que no admite este tipo de datos, debe reemplazar por el tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Por ejemplo, `uint` suele ser de 16 bits en otros entornos. Al pasar un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en su administrado [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] código.  
  
## <a name="see-also"></a>Vea también  
 [Reflexión (Visual Basic)](../../programming-guide/concepts/reflection.md)  
 [Reflexión](../../../framework/reflection-and-codedom/reflection.md)  
 
