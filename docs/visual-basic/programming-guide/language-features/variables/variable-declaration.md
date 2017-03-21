---
title: "Declaración de variable en Visual Basic | Documentos de Microsoft"
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
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8cabb2d319288653c80099c816e46e822429d6ec
ms.lasthandoff: 03/13/2017

---
# <a name="variable-declaration-in-visual-basic"></a>Declaración de variable en Visual Basic
Declare una variable para especificar su nombre y sus características. La instrucción de declaración para variables es el [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md). Su ubicación y contenido determinan las características de la variable.  
  
 Para las reglas de nomenclaturas de variables y consideraciones, consulte [nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Niveles de declaración  
  
### <a name="local-and-member-variables"></a>Local y Variables de miembro  
 Un *variable local* es aquella que se declara dentro de un procedimiento. Un *variable miembro* es un miembro de un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipo; se declara en el nivel de módulo, dentro de una clase, estructura o módulo, pero no dentro de ningún procedimiento interno de esa clase, estructura o módulo.  
  
### <a name="shared-and-instance-variables"></a>Compartir y las Variables de instancia  
 En una clase o estructura, depende de la categoría de una variable miembro o no se comparte. Si se declara con la [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) (palabra clave), es un *variable compartida*, y existe en una única copia compartida por todas las instancias de la clase o estructura.  
  
 De lo contrario, es un *variable de instancia*, y se crea una copia independiente de ella para cada instancia de la clase o estructura. Una copia determinada de una variable de instancia está disponible sólo para la instancia de la clase o estructura en la que se creó. Es independiente de una copia de la variable de instancia en cualquier otra instancia de la clase o estructura.  
  
## <a name="declaring-data-type"></a>Declaración de tipo de datos  
 El [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula en la instrucción de declaración permite definir el tipo de datos o el tipo de objeto de la variable que se está declarando. Puede especificar cualquiera de los siguientes tipos de variable:  
  
-   Escriba un datos básicos, como `Boolean`, `Long`, o`Decimal`  
  
-   Un tipo de datos compuesto, como una matriz o una estructura  
  
-   Un tipo de objeto o clase, definido en la aplicación o en otra aplicación  
  
-   Un [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] de clase, como <xref:System.Windows.Forms.Label>o <xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox> </xref:System.Windows.Forms.Label>  
  
-   Tipo de una interfaz, como <xref:System.IComparable>o <xref:System.IDisposable></xref:System.IDisposable> </xref:System.IComparable>  
  
 Puede declarar varias variables en una instrucción sin tener que repetir el tipo de datos. En las instrucciones siguientes, las variables `i`, `j`, y `k` se declaran como tipo `Integer`, `l` y `m` como `Long`, y `x` y `y` como `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Para obtener más información sobre los tipos de datos, consulte [tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Para obtener más información sobre objetos, consulte [objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) y [programación con componentes](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).  
  
## <a name="local-type-inference"></a>Inferencia de tipo de variable local  
 *Inferencia de tipo* se usa para determinar los tipos de datos de variables locales declaradas sin un `As` cláusula. El compilador deduce el tipo de la variable del tipo de la expresión de inicialización. Esto permite declarar variables sin especificar explícitamente un tipo. En el siguiente ejemplo, ambos `num1` y `num2` están fuertemente tipados como enteros.  
  
 [!code-vb[1 VbVbalrTypeInference](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 Si desea utilizar la inferencia de tipo local, `Option Infer` debe establecerse en `On`. Para obtener más información, consulte [inferencia de tipo Local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) y [Option Infer instrucción](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="characteristics-of-declared-variables"></a>Características de las Variables declaradas  
 El *duración* de una variable es el período de tiempo durante el cual está disponible para su uso. En general, una variable existe mientras el elemento que lo declara (como un procedimiento o clase) siga existiendo. Si la variable no necesita seguir existiendo más allá de la duración de su elemento contenedor, no necesitará hacer nada especial en la declaración. Si la variable debe seguir existiendo durante más tiempo que su elemento contenedor, puede incluir la `Static` o `Shared` palabra clave en su `Dim` instrucción. Para obtener más información, consulte [duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 El *ámbito* de una variable es el conjunto de código que puede hacer referencia sin calificar su nombre. El ámbito de una variable depende de dónde se declara. Código que se encuentra en una región determinada puede utilizar las variables definidas en dicha región sin tener que calificar sus nombres. Para obtener más información, consulte [ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Una variable *nivel de acceso* es la extensión de código que tiene permiso de acceso. Esto viene determinado por el modificador de acceso (como [público](../../../../visual-basic/language-reference/modifiers/public.md) o [privada](../../../../visual-basic/language-reference/modifiers/private.md)) que se utilizan en el `Dim` instrucción. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo: crear una nueva Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)   
 [Cómo: mover datos hacia y desde una Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Protegido](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Estático](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
