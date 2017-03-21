---
title: Solucionar problemas de Variables en Visual Basic | Documentos de Microsoft
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
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
caps.latest.revision: 20
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
ms.openlocfilehash: 9cddf7ced50c42514ebc9a613f49adee31edde0b
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-variables-in-visual-basic"></a>Solucionar problemas de variables en Visual Basic
Esta página muestra algunos problemas comunes que pueden producirse al trabajar con variables en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="unable-to-access-members-of-an-object"></a>No se puede acceder a los miembros de un objeto  
 Si el código intenta obtener acceso a una propiedad o a un método en un objeto, existen dos posibles resultados de error:  
  
-   El compilador puede generar un mensaje de error si declara que la variable de objeto es de un tipo específico y, después, hace referencia a un miembro no definido por dicho tipo.  
  
-   Tiempo de ejecución <xref:System.MemberAccessException>se produce cuando el objeto asignado a una variable de objeto no expone el miembro el código está intentando obtener acceso.</xref:System.MemberAccessException> En el caso de una variable de [tipo de datos Object](../../../../visual-basic/language-reference/data-types/object-data-type.md), también puede obtener esta excepción si el miembro no es `Public`. Esto se debe a que el enlace en tiempo de ejecución solo permite el acceso a miembros `Public` .  
  
 Cuando el [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) comprobación de tipos de conjuntos de `On`, puede tener acceso a una variable de objeto sólo los métodos y propiedades de la clase con la que se declara. Esto se ilustra en el siguiente ejemplo:  

 [!code-vb[VbVbalrVariables&#2;](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]  
  
 En este ejemplo, `p` sólo puede utilizar los miembros de la <xref:System.Object>de clase, que no incluyen el `Left` propiedad.</xref:System.Object> Por otro lado, `q` se ha declarado como de tipo <xref:System.Windows.Forms.Label>, por lo que puede utilizar todos los métodos y propiedades de la <xref:System.Windows.Forms.Label>de clase en el <xref:System.Windows.Forms>espacio de nombres.</xref:System.Windows.Forms> </xref:System.Windows.Forms.Label> </xref:System.Windows.Forms.Label>  
  
### <a name="correct-approach"></a>Enfoque correcto  
 Para obtener acceso a todos los miembros de un objeto de una clase determinada, declare la variable de objeto con el tipo de dicha clase siempre que sea posible. Si no puede hacer esto, por ejemplo, si no conoce el objeto de tipo en tiempo de compilación, debe establecer `Option Strict` a `Off` y declarar la variable de la [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md). Esto permite que se asignen a la variable los objetos de cualquier tipo y debe realizar los pasos necesarios para asegurarse de que el objeto asignado actualmente es de un tipo válido. Puede usar el [operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) para tomar esta decisión.  
  
## <a name="other-components-cannot-access-your-variable"></a>Otros componentes no pueden tener acceso a la variable  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]los nombres son *entre mayúsculas y minúsculas*. Si dos nombres solo se distinguen por el uso de mayúsculas y minúsculas, el compilador los interpreta como el mismo nombre Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.  
  
 Sin embargo, Common Language Runtime (CLR) usa enlaces que *distinguen entre mayúsculas y minúsculas* . Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas. Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`. Si, posteriormente, vuelve a compilar la clase y cambia el nombre del elemento a `abc`, los otros ensamblados que usen la clase ya no tendrán acceso a este elemento. Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.  
  
 Para obtener más información, consulte [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).  
  
### <a name="correct-approach"></a>Enfoque correcto  
 Para permitir que otros componentes tengan acceso a las variables, trate sus nombres como si distinguieran entre mayúsculas y minúsculas. Cuando pruebe la clase o el módulo, asegúrese de que los demás ensamblados se enlazan con las variables esperadas. Después de publicar un componente, no realice ninguna modificación en los nombres de variable existentes, incluido el cambio entre mayúsculas y minúsculas.  
  
## <a name="wrong-variable-being-used"></a>Uso de la variable equivocada  
 Cuando haya más de una variable con el mismo nombre, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador intenta resolver todas las referencias a ese nombre. Si las variables tienen un ámbito diferente, el compilador resuelve una referencia a la declaración con el ámbito más limitado. Si tienen el mismo ámbito, se produce un error en la resolución y el compilador señala un error. Para obtener más información, consulte [referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Enfoque correcto  
 Evite usar variables con el mismo nombre pero con un ámbito diferente. Si usa otros ensamblados o proyectos, evite en la medida de lo posible usar nombres definidos en dichos componentes externos. Si tiene más de una variable con el mismo nombre, asegúrese de calificar todas las referencias a esta. Para obtener más información, consulte [referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Vea también  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Declaración de Variable de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Cómo: obtener acceso a miembros de un objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [Valores de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Cómo: determinar qué tipo de una Variable de objeto hace referencia a](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
