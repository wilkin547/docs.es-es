---
title: "Tipo de valor opcional para el parámetro opcional &lt;parametername&gt; no es compatible con CLS | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- BC40042
- vbc40042
dev_langs:
- VB
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: 8
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
ms.openlocfilehash: 3dbcab01022d1604e79c6bfc3e04a14ef60bc219
ms.lasthandoff: 03/13/2017

---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a>Tipo de valor opcional para el parámetro opcional &lt;parametername&gt; no es compatible con CLS
Un procedimiento se marca como `<CLSCompliant(True)>`, pero declara un parámetro [opcional](../../../visual-basic/language-reference/modifiers/optional.md) con valor predeterminado de un tipo no conforme.  
  
 Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), solo debe usar tipos conformes a CLS. Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales. También se aplica a los valores predeterminados de parámetros opcionales.  
  
 Los siguientes tipos de datos [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no son conformes con CLS:  
  
-   [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Al aplicar el <xref:System.CLSCompliantAttribute>atributo a un elemento de programación, establezca el atributo `isCompliant` parámetro como `True` o `False` para indicar compatibilidad o incompatibilidad.</xref:System.CLSCompliantAttribute> No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.  
  
 Si no aplica <xref:System.CLSCompliantAttribute>a un elemento, se considera como no conforme.</xref:System.CLSCompliantAttribute>  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40042  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si el parámetro opcional debe tener un valor predeterminado de este tipo determinado, quite <xref:System.CLSCompliantAttribute>.</xref:System.CLSCompliantAttribute> El procedimiento no puede ser conforme a CLS.  
  
-   Si el procedimiento debe ser conforme a CLS, cambie el tipo de este valor predeterminado al tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Por ejemplo, `int` suele ser de 16 bits en otros entornos. Al aceptar un entero de 16 bits de ese componente, declárelo como `Short` en lugar de `Integer` en su código [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] administrado.  
  
## <a name="see-also"></a>Vea también  
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
