---
title: Solución de problemas de variables
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
ms.openlocfilehash: e2bcf0b779d98ea4b109ea6d33b69a15110d423c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080171"
---
# <a name="troubleshooting-variables-in-visual-basic"></a>Solucionar problemas de variables en Visual Basic

En esta página se enumeran algunos problemas comunes que pueden producirse al trabajar con variables en Visual Basic.  
  
## <a name="unable-to-access-members-of-an-object"></a>No se puede acceder a los miembros de un objeto  

 Si el código intenta obtener acceso a una propiedad o a un método en un objeto, existen dos posibles resultados de error:  
  
- El compilador puede generar un mensaje de error si declara que la variable de objeto es de un tipo específico y, después, hace referencia a un miembro no definido por dicho tipo.  
  
- Se produce una excepción <xref:System.MemberAccessException> en tiempo de ejecución cuando el objeto asignado a una variable de objeto no expone el miembro al que el código intenta obtener acceso. En el caso de una variable de [Object Data Type](../../../language-reference/data-types/object-data-type.md), también puede obtener esta excepción si el miembro no es `Public`. Esto se debe a que el enlace en tiempo de ejecución solo permite el acceso a miembros `Public` .  
  
 Si [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) establece la comprobación de tipos como `On`, una variable de objeto solo puede tener acceso a los métodos y propiedades de la clase con la que se ha declarado. Esto se ilustra en el siguiente ejemplo:  

 [!code-vb[VbVbalrVariables#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#2)]  
  
 En este ejemplo, `p` puede usar solo los miembros de la propia clase <xref:System.Object> , que no incluyen la propiedad `Left` . Por otro lado, `q` se ha declarado con el tipo <xref:System.Windows.Forms.Label>, así que puede usar todos los métodos y propiedades de la clase <xref:System.Windows.Forms.Label> en el espacio de nombres <xref:System.Windows.Forms> .  
  
### <a name="correct-approach"></a>Enfoque correcto  

 Para obtener acceso a todos los miembros de un objeto de una clase determinada, declare la variable de objeto con el tipo de dicha clase siempre que sea posible. Si no puede realizarlo de esta manera, por ejemplo si no conoce el tipo de objeto en tiempo de compilación, debe establecer `Option Strict` como `Off` y declarar la variable como [Object Data Type](../../../language-reference/data-types/object-data-type.md). Esto permite que se asignen a la variable los objetos de cualquier tipo y debe realizar los pasos necesarios para asegurarse de que el objeto asignado actualmente es de un tipo válido. Puede usar el [operador typeof](../../../language-reference/operators/typeof-operator.md) para tomar esta decisión.  
  
## <a name="other-components-cannot-access-your-variable"></a>Otros componentes no pueden tener acceso a la variable  

 Los nombres de Visual Basic no *distinguen mayúsculas de minúsculas*. Si dos nombres solo se distinguen por el uso de mayúsculas y minúsculas, el compilador los interpreta como el mismo nombre Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.  
  
 Sin embargo, Common Language Runtime (CLR) usa enlaces que *distinguen entre mayúsculas y minúsculas* . Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas. Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`. Si, posteriormente, vuelve a compilar la clase y cambia el nombre del elemento a `abc`, los otros ensamblados que usen la clase ya no tendrán acceso a este elemento. Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.  
  
 Para obtener más información, consulta [Common Language Runtime](../../../../standard/clr.md).  
  
### <a name="correct-approach"></a>Enfoque correcto  

 Para permitir que otros componentes tengan acceso a las variables, trate sus nombres como si distinguieran entre mayúsculas y minúsculas. Cuando pruebe la clase o el módulo, asegúrese de que los demás ensamblados se enlazan con las variables esperadas. Después de publicar un componente, no realice ninguna modificación en los nombres de variable existentes, incluido el cambio entre mayúsculas y minúsculas.  
  
## <a name="wrong-variable-being-used"></a>Uso de la variable equivocada  

 Cuando hay más de una variable con el mismo nombre, el compilador Visual Basic intenta resolver cada referencia a ese nombre. Si las variables tienen un ámbito diferente, el compilador resuelve una referencia a la declaración con el ámbito más limitado. Si tienen el mismo ámbito, se produce un error en la resolución y el compilador señala un error. Para obtener más información, consulta [References to Declared Elements](../declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Enfoque correcto  

 Evite usar variables con el mismo nombre pero con un ámbito diferente. Si usa otros ensamblados o proyectos, evite en la medida de lo posible usar nombres definidos en dichos componentes externos. Si tiene más de una variable con el mismo nombre, asegúrese de calificar todas las referencias a esta. Para obtener más información, consulta [References to Declared Elements](../declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Vea también

- [Variables](index.md)
- [Declaración de variable](variable-declaration.md)
- [Variables de objeto](object-variables.md)
- [Declaración de variables de objeto](object-variable-declaration.md)
- [Procedimiento para obtener acceso a los miembros de un objeto](how-to-access-members-of-an-object.md)
- [Valores de las variables de objeto](object-variable-values.md)
- [Procedimiento para determinar el tipo al que hace referencia una variable de objeto](how-to-determine-what-type-an-object-variable-refers-to.md)
- [References to Declared Elements](../declared-elements/references-to-declared-elements.md)
- [Declared Element Names](../declared-elements/declared-element-names.md)
