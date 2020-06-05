---
title: Tipo de datos
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
ms.openlocfilehash: 928d7fb6a40873641ae3e91e057c272b946a0091
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393719"
---
# <a name="data-types-in-visual-basic"></a>Tipos de datos en Visual Basic
El *tipo de datos* de un elemento de programación hace referencia al tipo de datos que puede contener y cómo almacena los datos. Los tipos de datos se aplican a todos los valores que se pueden almacenar en la memoria del equipo o participar en la evaluación de una expresión. Cada variable, literal, constante, enumeración, propiedad, parámetro de procedimiento, argumento de procedimiento y valor devuelto de un procedimiento tiene un tipo de datos.  
  
## <a name="declared-data-types"></a>Tipos de datos declarados  
 Define un elemento de programación con una instrucción de declaración y especifica su tipo de datos con la cláusula `As`. En la tabla siguiente se muestran las instrucciones que usa para declarar diversos elementos.  
  
|Elemento de programación|Declaración de tipos de datos|  
|-------------------------|---------------------------|  
|Variable|En una [instrucción Dim](../../../language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal|Con un carácter de tipo literal; consulte "Caracteres de tipo literal" en [Caracteres de tipo](type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Constante|En una [instrucción Const](../../../language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Enumeración|En una [instrucción Enum](../../../language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Propiedad|En una [instrucción Property](../../../language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Parámetro de procedimiento|En una [instrucción Sub](../../../language-reference/statements/sub-statement.md), [instrucción Function](../../../language-reference/statements/function-statement.md) o una [instrucción Operator](../../../language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Argumento de procedimiento|En el código de llamada; cada argumento es un elemento de programación que ya se declaró, o bien una expresión que contiene los elementos declarados<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Valor devuelto de un procedimiento|En una [instrucción Function](../../../language-reference/statements/function-statement.md) o una [instrucción Operator](../../../language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Para ver una lista de los tipos de datos de Visual Basic, consulte [Tipos de datos](../../../language-reference/data-types/index.md).  
  
## <a name="see-also"></a>Consulte también

- [Caracteres de tipo](type-characters.md)
- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos de datos compuestos](composite-data-types.md)
- [Tipos genéricos en Visual Basic](generic-types.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Estructuras](structures.md)
- [Tuplas](tuples.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Tipos de datos](../../../language-reference/data-types/index.md)
- [Uso eficiente de los tipos de datos](efficient-use-of-data-types.md)
