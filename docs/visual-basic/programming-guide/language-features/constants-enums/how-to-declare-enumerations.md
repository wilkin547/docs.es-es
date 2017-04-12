---
title: "Cómo: declarar enumeraciones (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
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
ms.openlocfilehash: 8ff8bf2df39bed0597740bcda968283ec854f447
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a>Cómo: Declarar enumeraciones (Visual Basic)
Crear una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o módulo. No se puede declarar una enumeración dentro de un método. Para especificar el nivel de acceso adecuado, utilice `Private`, `Protected`, `Friend`, o `Public`.  
  
 Un `Enum` tipo tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante. El nombre debe ser válido [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] calificador. El tipo subyacente debe ser uno de los tipos enteros:`Byte`, `Short`, `Long` o `Integer`. `Integer` es el valor predeterminado. Las enumeraciones tienen siempre establecimiento inflexible y no son intercambiables con tipos de números enteros.  
  
 Las enumeraciones no pueden tener valores de punto flotante. Si se asigna un valor de punto flotante con una enumeración `Option Strict On`, obtendrá un error del compilador. Si `Option Strict` es `Off`, el valor se convierte automáticamente en el `Enum` tipo.  
  
 Para obtener información sobre nombres y cómo utilizar el `Imports` instrucción innecesaria, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Para declarar una enumeración  
  
1.  Escriba una declaración que incluya un nivel de acceso del código, el `Enum` (palabra clave) y un nombre válido, como en los ejemplos siguientes, cada uno de los cuales declara otra `Enum`.  
  
     [!code-vb[VbEnumsTask&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Defina las constantes en la enumeración. De forma predeterminada, se inicializa la primera constante de una enumeración en `0`, y posteriores se inicializan con un valor de la constante anterior más uno. Por ejemplo, la siguiente enumeración, `Days`, contiene una constante denominada `Sunday` con el valor `0`, una constante denominada `Monday` con el valor `1`, una constante denominada `Tuesday` con el valor de `2`, y así sucesivamente.  
  
     [!code-vb[VbEnumsTask Nº&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Puede asignar explícitamente valores a constantes en una enumeración mediante una instrucción de asignación. Puede asignar cualquier valor entero, incluidos los números negativos. Por ejemplo, puede constantes con valores menores que cero representen condiciones de error. En la siguiente enumeración, la constante `Invalid` se asigna explícitamente el valor `–1`y la constante `Sunday` se asigna el valor `0`. Porque es la primera constante de la enumeración `Saturday` también se inicializa con el valor `0`. El valor de `Monday` es `1` (uno más que el valor de `Sunday`); el valor de `Tuesday` es `2`, y así sucesivamente.  
  
     [!code-vb[VbEnumsTask&#5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Para declarar una enumeración como un tipo explícito  
  
-   Especifique el tipo de la enumeración mediante el `As` cláusula, tal como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbEnumsTask&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Cómo: hacer referencia a un miembro de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Cómo: recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Cómo: determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Cuándo utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Información general de constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
