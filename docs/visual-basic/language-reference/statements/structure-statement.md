---
title: Structure (Instrucción)
ms.date: 05/12/2018
f1_keywords:
- vb.Structure
- Structure
helpviewer_keywords:
- user-defined types [Visual Basic], Structure statement
- compound data types [Visual Basic]
- Structure keyword [Visual Basic]
- Structure statement [Visual Basic]
- UDT (user-defined types)
- types [Visual Basic], user-defined
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
ms.openlocfilehash: 6fdc4f1d2fbd40689c76a15a5a35b25522138be6
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234470"
---
# <a name="structure-statement"></a>Structure (Instrucción)
Declara el nombre de una estructura e introduce la definición de las variables, propiedades, eventos y procedimientos que la estructura incluye.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Público](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Privado protegido](../../language-reference/modifiers/private-protected.md) <br /><br /> Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Opcional. Indica una definición parcial de la estructura. Vea [parcial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Requerido. Nombre de esta estructura. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una estructura genérica.|  
|`typelist`|Es obligatorio si se utiliza la [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave. Lista de parámetros de tipo de esta estructura. Vea [escriba lista](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Opcional. Indica que esta estructura implementa los miembros de una o más interfaces. Vea [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`. Nombres de las interfaces implementadas por esta estructura.|  
|`datamemberdeclarations`|Requerido. Cero o más `Const`, `Dim`, `Enum`, o `Event` instrucciones declarar *miembros de datos* de la estructura.|  
|`methodmemberdeclarations`|Opcional. Cero o más declaraciones de `Function`, `Operator`, `Property`, o `Sub` procedimientos, que sirven como *miembros del método* de la estructura.|  
|`End Structure`|Requerido. Termina la definición de `Structure`.|  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `Structure` define un tipo de valor compuesto que se puede personalizar. A *estructura* es una generalización del tipo definido por el usuario (UDT) de las versiones anteriores de Visual Basic. Para obtener más información, consulte [estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Las estructuras admiten muchas de las mismas características que las clases. Por ejemplo, las estructuras pueden tener propiedades y procedimientos, pueden implementar interfaces y pueden tener constructores con parámetros. No obstante, existen diferencias importantes entre las estructuras y las clases en materias como la herencia, las declaraciones y la utilización. Además, las clases son tipos de referencia y las estructuras son tipos de valor. Para obtener más información, consulte [estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 `Structure` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que la *contexto de la declaración* para una estructura debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 De forma predeterminada las estructuras [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Anidamiento.** Puede definirse una estructura dentro de otra. La estructura exterior se denomina la *que contiene una estructura*, y la estructura interna se denomina un *anidados estructura*. Sin embargo, no se puede tener acceso a los miembros de una estructura anidada a través de la estructura contenedora. En lugar de ello, se debe declarar una variable del tipo de datos de la estructura anidada.  
  
-   **Declaración de miembros.** Se debe declarar cada miembro de una estructura. No puede ser un miembro de estructura [Protected](../../../visual-basic/language-reference/modifiers/protected.md) o `Protected Friend` porque no se puede heredar de una estructura. La propia estructura, sin embargo, puede ser de tipo `Protected` o `Protected Friend`.  
  
     En una estructura se pueden declarar cero o más variables no compartidas o eventos no compartidos y no personalizados. No pueden utilizarse únicamente constantes, propiedades y procedimientos, aunque algunos sean no compartidos.  
  
-   **inicialización.** No se puede inicializar el valor de ningún miembro de datos de una estructura no compartido como parte de su declaración. Dicho miembro de datos se debe inicializar mediante un constructor con parámetros en la estructura o bien mediante la asignación de un valor al miembro después de crear una instancia de la estructura.  
  
-   **Herencia.** Una estructura no puede heredar de ningún tipo distinto de <xref:System.ValueType>, del que todas las estructuras heredan. En particular, una estructura no puede heredar de otra.  
  
     No se puede utilizar el [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) en una definición de estructura, incluso para especificar <xref:System.ValueType>.  
  
-   **Implementación de.** Si utiliza la estructura de la [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md), debe implementar cada miembro definido por cada interfaz que se especifique en `interfacenames`.  
  
-   **Propiedad Default.** Una estructura puede especificar a lo sumo una propiedad como su *propiedad predeterminada*, usando la [predeterminado](../../../visual-basic/language-reference/modifiers/default.md) modificador. Para obtener más información, consulte [predeterminado](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** En una estructura, cada miembro se puede declarar con su propio nivel de acceso. De forma predeterminada todos los miembros de estructura [público](../../../visual-basic/language-reference/modifiers/public.md) acceso. Tenga en cuenta que si la propia estructura utiliza un nivel de acceso más limitado, se restringe automáticamente el acceso a sus miembros, aunque los niveles de acceso se ajusten con modificadores.  
  
-   **Ámbito.** Una estructura está en ámbito en su espacio de nombres, clase, estructura o módulo contenedores.  
  
     El ámbito de todos los miembros de la estructura es la estructura completa.  
  
-   **Duración.** Una estructura no dispone por sí misma de período de duración. Más bien, cada instancia de esa estructura tiene un período de duración independiente de todas las demás instancias.  
  
     La duración de una instancia comienza cuando se crea un [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md) cláusula. Finaliza cuando finaliza el período de duración de la variable que la contiene.  
  
     No puede extender el período de duración de una instancia de estructura. Los módulos proporcionan una aproximación a la funcionalidad de estructura estática. Para obtener más información, consulte [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Los miembros de estructura disponen de un período de duración en función de cómo y donde se declaran. Para obtener más información, vea "Duración" en [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md).  
  
-   **Calificación.** El código que se incluye fuera de una estructura debe calificar el nombre de un miembro con el nombre de dicha estructura.  
  
     Si el código incluido en una estructura anidada realiza una referencia sin calificar a un elemento de programación, Visual Basic busca este elemento en la estructura anidada en primer lugar, a continuación en la estructura contenedora y así sucesivamente hasta el elemento contenedor principal. Para obtener más información, consulte [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Consumo de memoria.** Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros. Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración. Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se utiliza la instrucción `Structure` para definir un conjunto de datos relacionados de un empleado. Se muestra el uso de los miembros `Public`, `Friend` y `Private` para reflejar la confidencialidad de los elementos de datos. También se muestran los miembros de evento, propiedad y procedimiento.  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/structure-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
