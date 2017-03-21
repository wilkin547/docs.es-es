---
title: "Cómo: declarar una constante (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
dev_langs:
- VB
helpviewer_keywords:
- Integer data type, declaring constants
- Single data type, declaring constants
- Const statement [Visual Basic], declaring constants
- procedures, declaration
- data types [Visual Basic], constants
- Long data type, declaring constants
- Visual Basic code, declaring variables and constants
- Double data type, declaring constants
- Boolean data type, declaring constants
- modules, declaring constants
- Byte data type, declaring constants
- constants, declaring
- Date data type, declaring constants
- String data type, declaring constants
- declaring constants, const keyword
- Currency data type, declaring constants and variants
- module-level constants and variables
- Object data type, declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 401d0feb85fccf94a25308d38c3c75198ef9294c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a>Cómo: Declarar una constante (Visual Basic)
Utiliza el `Const` instrucción para declarar una constante y establecer su valor. Al declarar una constante, se asigna un nombre significativo a un valor. Una vez que se declara una constante, no se puede modificar o asigna un nuevo valor.  
  
 Declarar una constante dentro de un procedimiento o en la sección de declaraciones de un módulo, clase o estructura. Constantes de clase o nivel de estructura son `Private` de forma predeterminada, pero también se puede declarar como `Public`, `Friend`, `Protected`, o `Protected Friend` para el nivel apropiado de acceso al código.  
  
 La constante debe tener un nombre simbólico válido (las reglas son las mismas que para crear nombres de variable) y una expresión compuesta de numérico o cadena constantes y operadores (pero no hay llamadas de función).  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-declare-a-constant"></a>Para declarar una constante  
  
-   Escriba una declaración que incluya un especificador de acceso, el `Const` (palabra clave) y una expresión, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask Nº&8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar una constante explícitamente especificando un tipo de datos (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, o `String`).  
  
     Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con un `As` cláusula. El compilador determina el tipo de la constante del tipo de la expresión. Para obtener más información, consulte [constante y tipos de datos literales](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Para declarar una constante que tiene un tipo de datos establecidos explícitamente  
  
-   Escriba una declaración que incluya la `As` (palabra clave) y una explícitas tipo de datos, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask&#9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     Puede declarar varias constantes en una sola línea, aunque el código es más legible si declarar solamente una constante por línea. Si declara varias constantes en una sola línea, deben tener el mismo nivel de acceso (`Public`, `Private`, `Friend`, `Protected`, o `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Para declarar varias constantes en una sola línea  
  
-   Separe las declaraciones con una coma y un espacio, como en el ejemplo siguiente:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Tipos de datos constantes y literales](constant-and-literal-data-types.md)   
 [Información general de constantes](constants-overview.md)
 [Cómo: declarar una constante](how-to-declare-a-constant.md)
 [constantes definidas por el usuario](user-defined-constants.md)
 [tipos de datos constantes y literales](constant-and-literal-data-types.md)
 [Cómo: agrupar valores de constantes relacionadas](how-to-group-related-constant-values-together.md)
 [información general de las enumeraciones](enumerations-overview.md)
 [Cómo: declarar enumeraciones](how-to-declare-enumerations.md)
 [Cómo: hacer referencia a un miembro de enumeración](how-to-refer-to-an-enumeration-member.md)
 [enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
 [Cómo: recorrer en iteración una enumeración](how-to-iterate-through-an-enumeration.md)
 [Cómo: determinar la cadena Asociado con un valor de enumeración](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)

 [Información general de las enumeraciones](enumerations-overview.md)   
 [Información general de constantes](constants-overview.md)   
 [Cómo: declarar una enumeración](how-to-declare-enumerations.md)   
 [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)   
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)

