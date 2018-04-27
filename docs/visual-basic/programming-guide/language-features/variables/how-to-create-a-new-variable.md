---
title: 'Cómo: Crear una nueva variable (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aff160584d3d1fe382020d5b8c25ac57dab66d92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
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
  
3.  Siga las especificaciones con el nombre de la variable, que debe seguir las convenciones y reglas de Visual Basic. Para obtener más información, consulte [nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  Siga el nombre con el [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula para especificar el tipo de datos de la variable.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Si no especifica el tipo de datos, utiliza el valor predeterminado: `Object`.  
  
5.  Siga el `As` cláusula con un signo igual (`=`) y siga el signo igual con el valor inicial de la variable.  
  
     Visual Basic asigna el valor especificado a la variable cada vez que se ejecuta el `Dim` instrucción. Si no especifica un valor inicial, Visual Basic asigna el valor inicial predeterminado para el tipo de datos de la variable cuando entra por primera vez el código que contiene el `Dim` instrucción.  
  
     Si la variable es un tipo de referencia, puede crear una instancia de su clase incluyendo la [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md) palabra clave en el `As` cláusula. Si no usa `New`, el valor inicial de la variable es [nada](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
