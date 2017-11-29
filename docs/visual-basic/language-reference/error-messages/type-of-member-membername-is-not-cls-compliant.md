---
title: Tipo de miembro &#39; &lt;membername&gt;&#39; no es conforme a CLS
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords: BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c09a71675275758220691ad09eeab48e53309f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>Tipo de miembro &#39; &lt;membername&gt;&#39; no es conforme a CLS
El tipo de datos especificado para este miembro no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS). Esto no es un error dentro de un componente, porque la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] admiten este tipo de datos. Sin embargo, otro componente escrito en código estrictamente conforme a CLS podría no admitir este tipo de datos. Posible que un componente de ese tipo no pueda interactuar correctamente con su componente.  
  
 Los siguientes tipos de datos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no son conformes con CLS:  
  
-   [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si el componente se comunica solo con otros [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componentes o no interactúen con cualquier otro componente, no necesita cambiar nada.  
  
-   Si interactúa con un componente no escrito para el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], es posible que pueda determinar, ya sea mediante reflexión o en documentación, si admite este tipo de datos. Si es así, no es necesario cambiar nada.  
  
-   Si interactúa con un componente que no admite este tipo de datos, debe reemplazar por el tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Por ejemplo, `uint` suele ser de 16 bits en otros entornos. Al pasar un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en su administrado [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] código.  
  
## <a name="see-also"></a>Vea también  
 [Reflexión](../../../framework/reflection-and-codedom/reflection.md)  
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
