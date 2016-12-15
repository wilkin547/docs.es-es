---
title: "Constantes definidas por el usuario (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "referencias circulares entre constantes"
  - "Const (instrucción) [Visual Basic], constantes definidas por el usuario"
  - "constantes, referencias circulares"
  - "constantes, definidas por el usuario"
  - "ámbito, constantes"
  - "constantes definidas por el usuario"
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Constantes definidas por el usuario (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una constante es un nombre significativo que toma el lugar de un número o cadena que no cambia.  Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación.  Puede utilizar constantes definidas por los controles o componentes con los que trabaja o puede crear sus propias constantes.  Las constantes que crea el usuario se denominan *definidas por el usuario*.  
  
 Las constantes se declaran con la instrucción `Const`, utilizando las mismas directrices que en la creación de nombres de variables.  Si `Option Strict` es `On`, debe declarar el tipo de constante explícitamente.  
  
## Utilización de la instrucción Const  
 Una instrucción `Const` puede representar una cantidad matemática o fecha y hora:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 También puede definir constantes `String`:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 La expresión a la derecha del signo igual \(`=`\) suele ser un número o una cadena de literal, pero también puede ser una expresión que da como resultado un número o una cadena \(si bien dicha expresión no puede contener llamadas a funciones\).  Incluso pueden definirse constantes en términos de constantes definidas anteriormente:  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## Ámbito de las constantes definidas por el usuario  
 El ámbito de la instrucción `Const` es el mismo que el de una variable declarada en la misma ubicación.  Puede especificar el ámbito de cualquiera de las siguientes maneras:  
  
-   Para crear una constante que exista sólo dentro de un procedimiento concreto, declárela dentro de dicho procedimiento.  
  
-   Para crear una constante disponible para todos los procedimientos de una clase, pero no para código fuera de ese módulo, declárela en la sección de declaraciones de la clase.  
  
-   Para crear una constante que esté disponible para todos los miembros de un ensamblado, pero no para clientes fuera del ensamblado, declárela mediante la palabra clave `Friend` en la sección de declaraciones de la clase.  
  
-   Para crear una constante disponible en toda la aplicación, declárela con la palabra clave `Public` en la sección de declaraciones de la clase.  
  
 Para obtener más información, vea [Cómo: Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### Evitar referencias circulares  
 Puesto que las constantes pueden definirse en función de otras constantes, puede ocurrir que sin darse cuenta cree un *ciclo* o referencia circular involuntariamente, entre dos o más constantes.  Un ciclo se produce cuando hay dos o más constantes públicas, cada una definida basándose en la otra, como en este ejemplo:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 Si se produce un ciclo,[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] genera un error del compilador.  
  
## Vea también  
 [Const \(Instrucción\)](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constantes y enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)