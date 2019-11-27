---
title: 'Cómo: Declarar una constante'
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: 5054d4a4fc02d8bd22efceb01770fc54167d8cb3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347468"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Cómo: Declarar una constante (Visual Basic)
Use la instrucción `Const` para declarar una constante y establecer su valor. Al declarar una constante, se asigna un nombre descriptivo a un valor. Una vez declarada una constante, no se puede modificar ni asignar un nuevo valor.  
  
 Una constante se declara dentro de un procedimiento o en la sección de declaraciones de un módulo, clase o estructura. Las constantes de nivel de clase o estructura se `Private` de forma predeterminada, pero también se pueden declarar como `Public`, `Friend`, `Protected`o `Protected Friend` para el nivel adecuado de acceso al código.  
  
 La constante debe tener un nombre simbólico válido (las reglas son las mismas que para crear nombres de variable) y una expresión compuesta por constantes numéricas o de cadena y operadores (pero ninguna llamada de función).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Para declarar una constante  
  
- Escriba una declaración que incluya un especificador de acceso, la palabra clave `Const` y una expresión, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [option STRICT](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar una constante explícitamente especificando un tipo de datos (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`o `String`).  
  
     Cuando `Option Infer` se `On` o se `Off``Option Strict`, puede declarar una constante sin especificar un tipo de datos con una cláusula `As`. El compilador determina el tipo de la constante a partir del tipo de la expresión. Para obtener más información, vea [tipos de datos constantes y literales](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Para declarar una constante que tiene un tipo de datos declarado explícitamente  
  
- Escriba una declaración que incluya la palabra clave `As` y un tipo de datos explícito, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     Puede declarar varias constantes en una sola línea, aunque el código es más legible si declara una sola constante por línea. Si declara varias constantes en una sola línea, todas deben tener el mismo nivel de acceso (`Public`, `Private`, `Friend`, `Protected`o `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Para declarar varias constantes en una sola línea  
  
- Separe las declaraciones con una coma y un espacio, como en el ejemplo siguiente:  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Vea también

- [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Tipos de datos constantes y literales](constant-and-literal-data-types.md)
- [Información general sobre las constantes](constants-overview.md)
- [Declarar una constante](how-to-declare-a-constant.md)
- [Constantes definidas por el usuario](user-defined-constants.md)
- [Tipos de datos constantes y literales](constant-and-literal-data-types.md)
- [Agrupar valores de constantes relacionadas](how-to-group-related-constant-values-together.md)
- [Información general sobre las enumeraciones](enumerations-overview.md)
- [Declarar una enumeración](how-to-declare-enumerations.md)
- [Hacer referencia al miembro de una enumeración](how-to-refer-to-an-enumeration-member.md)
- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Recorrer en iteración una enumeración en Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Determinar la cadena asociada a un valor de enumeración](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)

- [Información general sobre las enumeraciones](enumerations-overview.md)
- [Información general sobre las constantes](constants-overview.md)
- [Cómo: declarar una enumeración](how-to-declare-enumerations.md)
- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
