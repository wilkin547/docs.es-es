---
title: "Enumeraciones y calificaci&#243;n de nombres (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "nombres ambiguos, enumeraciones"
  - "declaraciones, enumeraciones"
  - "declaraciones, espacios de nombres"
  - "declarar enumeraciones"
  - "declarar espacios de nombres, enumeraciones"
  - "enumeraciones [Visual Basic], calificación de nombres"
  - "Imports (instrucción), declaraciones de espacios de nombres"
  - "conflictos de nombres"
  - "nombres, evitar conflictos"
  - "espacios de nombres, declarar"
  - "conflictos de nomenclatura, enumeraciones"
  - "conflictos de nomenclatura, calificar nombres"
  - "convenciones de nomenclatura, conflictos de nomenclatura"
  - "referencias, miembros de enumeración"
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Enumeraciones y calificaci&#243;n de nombres (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Normalmente, cuando se hace referencia a un miembro de una enumeración, es necesario calificarlo con el nombre de la enumeración.  Por ejemplo, para hacer referencia al miembro `Sunday` de la enumeración `Days`, se utilizaría la siguiente sintaxis:  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## Utilizar la instrucción Imports  
 Se puede evitar la utilización de nombres completos agregando la instrucción `Imports` a la sección de declaraciones de espacios de nombres del código, como en el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 Una instrucción `Imports` importa nombres de espacios de nombres de proyectos y ensamblados a los que se hace referencia y de dentro del mismo proyecto como el módulo en el que aparece la instrucción.  Una vez agregada esta instrucción, podría hacer referencia a los miembros de la enumeración sin calificación, como se muestra a continuación:  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 Mediante la organización de conjuntos de constantes relacionadas en enumeraciones, se pueden utilizar los mismos nombres de constantes en diferentes contextos.  Por ejemplo, puede utilizar los mismos nombres de las constantes de días de la semana en las enumeraciones `Days` y `WorkDays`.  Si utiliza la instrucción `Imports` con las enumeraciones, debe evitar referencias ambiguas.  Considere el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 Suponiendo que `Monday` sea un miembro de las enumeraciones `Days` y `Workdays`, este código generará un error del compilador.  Para evitar las referencias ambiguas a una constante individual, debe calificar el nombre de la constante con su enumeración.  El siguiente código hace referencia a las constantes `Saturday` en las enumeraciones `Days` y `WorkDays`.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## Vea también  
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Cómo: Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Cómo: Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Enum \(Instrucción\)](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)