---
title: Module (Instrucción)
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
ms.openlocfilehash: f4a0c7b772417085718b63569e8368178e348567
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605022"
---
# <a name="module-statement"></a>Module (Instrucción)
Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y los procedimientos que incluye el módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Opcional. Puede ser uno de los siguientes:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Requerido. Nombre de este módulo. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Opcional. Instrucciones que definen las variables, propiedades, eventos, procedimientos y los tipos anidados de este módulo.  
  
 `End Module`  
 Termina la definición de `Module`.  
  
## <a name="remarks"></a>Comentarios  
 Un `Module` instrucción define un tipo de referencia disponible a lo largo de su espacio de nombres. A *módulo* (a veces denominado un *módulo estándar*) es similar a una clase pero con algunas diferencias importantes. Cada módulo tiene exactamente una instancia y no necesita ser creado ni asignado a una variable. Los módulos no admiten la herencia ni implementan interfaces. Tenga en cuenta que un módulo no es un *tipo* en el sentido de que es una clase o estructura, no puede declarar un elemento de programación que el tipo de datos de un módulo.  
  
 Puede usar `Module` en el nivel de espacio de nombres. Esto significa que la *contexto de la declaración* para un módulo debe ser un archivo de código fuente o espacio de nombres y no puede ser una clase, estructura, módulo, interfaz, procedimiento o bloque. No se pueden anidar un módulo dentro de otro módulo, o dentro de cualquier tipo. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Un módulo tiene la misma duración que el programa. Dado que sus miembros son todos los `Shared`, también tienen duraciones iguales que el programa.  
  
 De forma predeterminada los módulos [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Todos los miembros de un módulo son implícitamente `Shared`.  
  
## <a name="classes-and-modules"></a>Las clases y módulos  
 Estos elementos tienen muchas similitudes, pero hay diferencias importantes.  
  
-   **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos de CLS) y *módulos estándar* (archivos de BAS). La versión actual llama a estos *clases* y *módulos*, respectivamente.  
  
-   **Miembros compartidos.** Puede controlar si un miembro de una clase es un compartido o miembro de instancia.  
  
-   **Orientación a objetos.** Clases están orientada a objetos, pero no son de módulos. Por lo que pueden crearse instancias de clases sola como objetos. Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Modificadores.** Todos los miembros de módulo son implícitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md). No se puede utilizar el `Shared` palabra clave al declarar un miembro y no puede modificar el estado de cualquier miembro compartido.  
  
-   **Herencia.** Un módulo no puede heredar de ningún tipo distinto de <xref:System.Object>, de que todos los módulos se heredan. En concreto, un módulo no puede heredar de otra.  
  
     No se puede utilizar el [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) en una definición de módulo, incluso para especificar <xref:System.Object>.  
  
-   **Propiedad Default.** No se puede definir las propiedades predeterminadas en un módulo. Para obtener más información, consulte [predeterminado](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Dentro de un módulo, puede declarar a cada miembro con su propio nivel de acceso. De forma predeterminada los miembros de módulo [público](../../../visual-basic/language-reference/modifiers/public.md) tener acceso, excepto las variables y constantes, que de forma predeterminada [privada](../../../visual-basic/language-reference/modifiers/private.md) acceso. Cuando un módulo más restringió el acceso a uno de sus miembros, el nivel de acceso del módulo especificado tiene prioridad.  
  
-   **Ámbito.** Es un módulo en el ámbito de su espacio de nombres.  
  
     El ámbito de cada miembro de módulo es el módulo completo. Tenga en cuenta que todos los miembros se someten a *promoción de tipo*, lo que hace que su ámbito se promueva al espacio de nombres que contiene el módulo. Para obtener más información, consulte [la promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Calificación.** Puede tener varios módulos en un proyecto y puede declarar a miembros con el mismo nombre en dos o más módulos. Sin embargo, debe calificar cualquier referencia a un miembro de este tipo con el nombre del módulo adecuado si la referencia es desde fuera de ese módulo. Para obtener más información, consulte [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Namespace (instrucción)](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
