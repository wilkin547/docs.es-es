---
title: El tipo de valor devuelto de la función '<procedurename>' no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 8ced0b6e06edadd9aed787aab2e715a2853e73a9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870848"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a>El tipo de valor devuelto de la función '\<procedurename>' no es compatible con CLS

Un `Function` procedimiento está marcado como `<CLSCompliant(True)>` pero devuelve un tipo que está marcado como `<CLSCompliant(False)>` , no está marcado o no cumple los requisitos porque es un tipo no conforme.  
  
 Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS. Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.  
  
 Los siguientes tipos de datos de Visual Basic no son conformes a CLS:  
  
- [Tipo de datos SByte](../data-types/sbyte-data-type.md)  
  
- [Tipo de datos UInteger](../data-types/uinteger-data-type.md)  
  
- [Tipo de datos ULong](../data-types/ulong-data-type.md)  
  
- [Tipo de datos UShort](../data-types/ushort-data-type.md)  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40027  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si el `Function` procedimiento debe devolver este tipo determinado, quite <xref:System.CLSCompliantAttribute> . El procedimiento no puede ser conforme a CLS.  
  
- Si el `Function` procedimiento debe ser conforme a CLS, cambie el tipo de valor devuelto al tipo conforme a CLS más próximo. Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647. Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
- Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework. Por ejemplo, `int` suele ser de 16 bits en otros entornos. Si devuelve un entero de 16 bits a este componente, declárelo como `Short` en lugar de `Integer` en el código de Visual Basic administrado.
