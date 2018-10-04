---
title: Module (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48779879"
---
# <a name="module-statement"></a>Module (Instrucción)
Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y procedimientos que incluye el módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Opcional. Puede ser uno de los siguientes:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Requerido. Nombre de este módulo. Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Opcional. Instrucciones que definen las variables, propiedades, eventos, procedimientos y los tipos anidados de este módulo.  
  
 `End Module`  
 Termina la definición de `Module`.  
  
## <a name="remarks"></a>Comentarios  
 Un `Module` instrucción define un tipo de referencia disponible a lo largo de su espacio de nombres. Un *módulo* (a veces denominado un *módulo estándar*) es similar a una clase, pero con algunas diferencias importantes. Cada módulo tiene exactamente una instancia y no necesita ser creado ni asignado a una variable. Los módulos no admiten la herencia ni implementan interfaces. Tenga en cuenta que un módulo no es un *tipo* en el sentido de que es una clase o estructura, no se puede declarar un elemento de programación para que el tipo de datos de un módulo.  
  
 Puede usar `Module` sólo en el nivel de espacio de nombres. Esto significa que el *contexto de declaración* para un módulo debe ser un archivo de código fuente o espacio de nombres y no puede ser la clase, estructura, módulo, interfaz, procedimiento o bloque. No se puede anidar un módulo dentro de otro módulo, o dentro de cualquier tipo. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Un módulo tiene la misma duración que el programa. Dado que sus miembros son todos `Shared`, también tienen duraciones iguales que el del programa.  
  
 De forma predeterminada los módulos [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Todos los miembros de un módulo son implícitamente `Shared`.  
  
## <a name="classes-and-modules"></a>Las clases y módulos  
 Estos elementos tienen muchas similitudes, pero hay diferencias importantes.  
  
-   **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos .cls) y *módulos estándar* (archivos BAS). La versión actual llama a estos *clases* y *módulos*, respectivamente.  
  
-   **Miembros compartidos.** Puede controlar si un miembro de una clase es un compartido o un miembro de instancia.  
  
-   **Orientación a objetos.** Clases están orientada a objetos, pero no son de módulos. Por lo que se pueden crear instancias únicas clases como objetos. Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Modificadores.** Todos los miembros de módulo son implícitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md). No puede usar el `Shared` palabra clave al declarar un miembro y no puede modificar el estado de cualquier miembro compartido.  
  
-   **Herencia.** Un módulo no puede heredar de ningún tipo distinto <xref:System.Object>, todos los módulos heredan. En concreto, un módulo no puede heredar de otra.  
  
     No puede usar el [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) en una definición de módulo, ni siquiera para especificar <xref:System.Object>.  
  
-   **Propiedad predeterminada.** No se puede definir cualquier propiedad predeterminada en un módulo. Para obtener más información, consulte [predeterminado](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Dentro de un módulo, puede declarar a cada miembro con su propio nivel de acceso. De forma predeterminada los miembros del módulo [pública](../../../visual-basic/language-reference/modifiers/public.md) acceder, excepto las variables y constantes, que de forma predeterminada [privada](../../../visual-basic/language-reference/modifiers/private.md) acceso. Cuando un módulo con más acceso restringido que uno de sus miembros, el nivel de acceso del módulo especificado tiene prioridad.  
  
-   **Ámbito.** Es un módulo en el ámbito de su espacio de nombres.  
  
     El ámbito de todos los miembros del módulo es el módulo completo. Tenga en cuenta que todos los miembros se someten a *promoción*, lo que hace que su ámbito se promueva al nivel de espacio de nombres que contiene el módulo. Para obtener más información, consulte [promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Calificación.** Puede tener varios módulos en un proyecto y puede declarar a miembros con el mismo nombre en dos o más módulos. Sin embargo, debe calificar cualquier referencia a este miembro con el nombre de módulo correspondiente si la referencia es de fuera de ese módulo. Para obtener más información, consulte [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Namespace (instrucción)](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
