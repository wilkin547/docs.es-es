---
title: El tipo de valor opcional para el parámetro opcional <parametername> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: 35ddf1d42efae20be477c20b89775de64ceee176
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589836"
---
# <a name="type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a>Tipo de valor opcional para el parámetro opcional \<parametername > no es conforme a CLS
Un procedimiento se marca como `<CLSCompliant(True)>`, pero declara un parámetro [opcional](../../../visual-basic/language-reference/modifiers/optional.md) con valor predeterminado de un tipo no conforme.  
  
 Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS. Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales. También se aplica a los valores predeterminados de parámetros opcionales.  
  
 Los siguientes tipos de datos de Visual Basic no son conformes a CLS:  
  
- [SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Al aplicar el atributo <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo como `True` o `False` para indicar compatibilidad o incompatibilidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.  
  
 Si no aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40042  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si el parámetro opcional debe tener un valor predeterminado de este tipo particular, quite <xref:System.CLSCompliantAttribute>. El procedimiento no puede ser conforme a CLS.  
  
- Si el procedimiento debe ser conforme a CLS, cambie el tipo de este valor predeterminado al tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
- Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos diferente que en .NET Framework. Por ejemplo, `int` suele ser de 16 bits en otros entornos. Si se acepta un entero de 16 bits de esos componentes, declárelo como `Short` en lugar de `Integer` en el código administrado de Visual Basic.
