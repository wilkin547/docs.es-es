---
title: "C&#243;mo: Declarar una constante (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.constant"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean (tipo de datos), declarar constantes"
  - "Byte (tipo de datos), declarar constantes"
  - "Const (instrucción) [Visual Basic], declarar constantes"
  - "constantes, declarar"
  - "Currency (tipo de datos), declarar constantes y variantes"
  - "tipos de datos [Visual Basic], constantes"
  - "Date (tipo de datos), declarar constantes"
  - "declarar constantes, const (palabra clave)"
  - "Double (tipo de datos), declarar constantes"
  - "Integer (tipo de datos), declarar constantes"
  - "Long (tipo de datos), declarar constantes"
  - "constantes y variables de nivel de módulo"
  - "módulos, declarar constantes"
  - "Object (tipo de datos), declarar constantes"
  - "procedimientos, declaración"
  - "Single (tipo de datos), declarar constantes"
  - "String (tipo de datos), declarar constantes"
  - "código de Visual Basic, declarar variables y constantes"
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Declarar una constante (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

La instrucción `Const` se utiliza para declarar una constante y establecer su valor.  Al declarar una constante, puede asignar un nombre significativo a un valor.  Una vez que se declara una constante, no se puede modificar ni se le puede asignar un nuevo valor.  
  
 Una constante puede declararse dentro de un procedimiento o en la sección de declaraciones de un módulo, clase o estructura.  Las constantes de clase o nivel de estructura son de manera predeterminada `Private` pero también se pueden declarar como `Public`, `Friend`, `Protected` o `Protected Friend` para el nivel de acceso al código adecuado.  
  
 La constante debe tener un nombre simbólico válido \(las reglas son las mismas que se aplican para la creación de nombres de variables\) y una expresión que se componga de constantes numéricas o de cadena, y operadores; no obstante, no se pueden utilizar llamadas a funciones.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Para declarar una constante  
  
-   Escriba una declaración que incluya un especificador de acceso, la palabra clave `Const` y una expresión, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar una constante explícitamente especificando un tipo de datos \(`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single` o `String`\).  
  
     Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con una cláusula `As`.  El compilador determina el tipo de la constante del tipo de expresión.  Para obtener más información, vea [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md).  
  
### Para declarar una constante que tiene un tipo de datos explícito  
  
-   Escriba una declaración que incluya la palabra clave `As` y un tipo de datos explícito, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     Pueden declararse varias constantes en una sola línea, si bien para facilitar la lectura del código se recomienda declarar solamente una constante por línea.  Si declara varias constantes en una línea única, deben tener todas ellas el mismo nivel de acceso \(`Public`, `Private`, `Friend`, `Protected` o `Protected Friend`\).  
  
### Para declarar varias constantes en una sola línea  
  
-   Separe las declaraciones con una coma y un espacio, como en el ejemplo siguiente:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## Vea también  
 [Const \(Instrucción\)](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constantes y enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)