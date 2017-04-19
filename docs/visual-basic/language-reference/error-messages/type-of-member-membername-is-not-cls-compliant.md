---
title: Tipo de miembro &quot;&lt;membername&gt;&quot; no es conforme a CLS | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
dev_langs:
- VB
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ea35f54cf8f0fb5a11148b8017456feb8d3524a
ms.lasthandoff: 03/13/2017

---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>Tipo de miembro '&lt;membername&gt;' no es compatible con CLS
El tipo de datos especificado para este miembro no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS). Esto no es un error en su componente, porque la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] y [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] admiten este tipo de datos. Sin embargo, otro componente escrito en código estrictamente compatible con CLS podría no admitir este tipo de datos. Un componente no puede interactuar correctamente con su componente.  
  
 Los siguientes tipos de datos [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no son conformes con CLS:  
  
-   [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, vea [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si su componente interactúa con otros [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] componentes o no interactúen con cualquier otro componente, no es necesario cambiar nada.  
  
-   Si trabaja con un componente no escrito para la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], es posible que pueda determinar, ya sea mediante reflexión o documentación, si admite este tipo de datos. Si lo hace, no es necesario cambiar nada.  
  
-   Si dispone de interfaz con un componente que no admite este tipo de datos, debe reemplazarlo con el tipo compatible con CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Por ejemplo, `uint` suele ser de 16 bits en otros entornos. Si se pasa un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en administradas [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] código.  
  
## <a name="see-also"></a>Vea también  
 [Reflexión](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)   
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
