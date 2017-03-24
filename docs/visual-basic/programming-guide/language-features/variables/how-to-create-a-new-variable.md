---
title: "Cómo: crear una nueva Variable (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
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
ms.openlocfilehash: 2856fe19ddc48a14385aaae7b1c331fcb96c0554
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Cómo: Crear una nueva variable (Visual Basic)
Crear una variable con un [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>Para crear una nueva variable  
  
1.  Declare la variable en un `Dim` instrucción.  
  
    ```  
  
    Dim newCustomer  
    ```  
  
2.  Incluyen especificaciones para las características de la variable, como [privada](../../../../visual-basic/language-reference/modifiers/private.md), [estático](../../../../visual-basic/language-reference/modifiers/static.md), [sombras](../../../../visual-basic/language-reference/modifiers/shadows.md), o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Para obtener más información, consulte [características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     No es necesario el `Dim` palabra clave si utiliza otras palabras clave en la declaración.  
  
3.  Siga con el nombre de la variable, que debe seguir las especificaciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] reglas y convenciones. Para obtener más información, consulte [nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  Siga con el nombre de la [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula para especificar el tipo de datos de la variable.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Si no especifica el tipo de datos, utiliza el valor predeterminado: `Object`.  
  
5.  Siga el `As` cláusula con un signo igual (`=`) y siga el signo igual con el valor inicial de la variable.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]asigna el valor especificado a la variable cada vez que se ejecuta el `Dim` instrucción. Si no especifica un valor inicial, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] asigna el valor inicial predeterminado para el tipo de datos de la variable cuando escribe por primer vez el código que contiene el `Dim` instrucción.  
  
     Si la variable es un tipo de referencia, puede crear una instancia de su clase incluyendo la [nuevo operador](../../../../visual-basic/language-reference/operators/new-operator.md) palabra clave en el `As` cláusula. Si no utiliza `New`, el valor inicial de la variable es [nada](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)   
 [Inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
