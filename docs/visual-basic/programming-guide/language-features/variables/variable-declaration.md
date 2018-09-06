---
title: Declaración de variable en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 92a20e5fbe60c71ec3375ed35c919e1f88cf0a9c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43737560"
---
# <a name="variable-declaration-in-visual-basic"></a>Declaración de variable en Visual Basic
Declare una variable para especificar su nombre y las características. La instrucción de declaración de variables es el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Su ubicación y contenido determinan las características de la variable.  
  
 Para las reglas de nomenclatura de variables y consideraciones, consulte [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Niveles de declaración  
  
### <a name="local-and-member-variables"></a>Local y Variables de miembro  
 Un *variable local* es aquella que se declara dentro de un procedimiento. Un *variable miembro* es un miembro de un tipo de Visual Basic; se declara en el nivel de módulo, dentro de una clase, estructura o módulo, pero no en cualquiera de los procedimientos interno de esa clase, estructura o módulo.  
  
### <a name="shared-and-instance-variables"></a>Compartido y las Variables de instancia  
 En una clase o estructura, depende de la categoría de una variable de miembro o si no se comparte. Si se declara con el [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) palabra clave, es un *variable compartida*, y está presente en una única copia compartida entre todas las instancias de la clase o estructura.  
  
 En caso contrario, es un *variable de instancia*, y se crea una copia independiente para cada instancia de la clase o estructura. Una copia determinada de una variable de instancia solo está disponible para la instancia de la clase o estructura en la que se creó. Es independiente de una copia de la variable de instancia de cualquier otra instancia de la clase o estructura.  
  
## <a name="declaring-data-type"></a>Declaración de tipo de datos  
 El [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula en la instrucción de declaración permite definir el tipo de datos o el tipo de objeto de la variable que se está declarando. Puede especificar cualquiera de los siguientes tipos para una variable:  
  
-   Escriba un datos básicos, como `Boolean`, `Long`, o `Decimal`  
  
-   Un tipo de datos compuestos, como una matriz o una estructura  
  
-   Un tipo de objeto o clase, definida en la aplicación o en otra aplicación  
  
-   Un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] clase, como <xref:System.Windows.Forms.Label> o <xref:System.Windows.Forms.TextBox>  
  
-   Tipo de una interfaz, como <xref:System.IComparable> o <xref:System.IDisposable>  
  
 Puede declarar varias variables en una instrucción sin tener que repetir el tipo de datos. En las instrucciones siguientes, las variables `i`, `j`, y `k` se declaran como tipo `Integer`, `l` y `m` como `Long`, y `x` y `y` como `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Para obtener más información sobre los tipos de datos, vea [tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Para obtener más información sobre los objetos, consulte [objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) y [programar con componentes](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).  
  
## <a name="local-type-inference"></a>Inferencia de tipo de variable local  
 *Inferencia de tipo* se usa para determinar los tipos de datos de variables locales declaradas sin un `As` cláusula. El compilador deduce el tipo de la variable del tipo de la expresión de inicialización. Esto le permite declarar variables sin especificar explícitamente un tipo. En el ejemplo siguiente, ambos `num1` y `num2` están fuertemente tipados como enteros.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 Si desea usar la inferencia de tipo local, `Option Infer` debe establecerse en `On`. Para obtener más información, vea [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).  
  
## <a name="characteristics-of-declared-variables"></a>Características de las Variables declaradas  
 El *duración* de una variable es el período de tiempo durante el cual está disponible para su uso. En general, existe una variable como el elemento que lo declara (por ejemplo, un procedimiento o clase) sigue existiendo. Si la variable no necesita seguir existiendo más allá de la duración de su elemento contenedor, no es necesario hacer nada especial en la declaración. Si la variable debe continuar sigue existiendo después de su elemento contenedor, puede incluir el `Static` o `Shared` palabra clave en su `Dim` instrucción. Para obtener más información, consulte [duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 El *ámbito* de una variable es el conjunto de todo el código que puede hacer referencia sin calificar su nombre. Ámbito de una variable viene determinada por donde se declara. Código que se encuentra en una región determinada puede utilizar las variables definidas en dicha región sin tener que calificar sus nombres. Para obtener más información, consulte [ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Una variable *nivel de acceso* es la extensión de código que tiene permiso para acceder a él. Esto viene determinado por el modificador de acceso (como [pública](../../../../visual-basic/language-reference/modifiers/public.md) o [privada](../../../../visual-basic/language-reference/modifiers/private.md)) que se utilizan en el `Dim` instrucción. Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vea también  
 [Crear una variable nueva](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [Introducir y extraer los datos de una variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)  
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
