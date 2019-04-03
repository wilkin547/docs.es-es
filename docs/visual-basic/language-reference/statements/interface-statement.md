---
title: Instrucción Interface (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: db39759a804905450e7f8913f45e8ddab39d8416
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823537"
---
# <a name="interface-statement-visual-basic"></a>Instrucción Interface (Visual Basic)
Declara el nombre de una interfaz e introduce las definiciones de los miembros que incluye la interfaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`attributelist`|Opcional. Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [privado](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Private protegida](../../language-reference/modifiers/private-protected.md)<br /><br /> Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Obligatorio. Nombre de esta interfaz. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una interfaz genérica.|  
|`typelist`|Obligatorio si se usa el [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave. Lista de parámetros de tipo para esta interfaz. Opcionalmente, cada parámetro de tipo se puede declarar variante utilizando `In` y `Out` modificadores genéricos. Consulte [escriba lista](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional. Indica que esta interfaz hereda los atributos y miembros de otra interfaz o interfaces. Consulte [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Inherits`. Los nombres de las interfaces que esta interfaz se deriva.|  
|`modifiers`|Opcional. Modificadores adecuados para el miembro de interfaz que se está definiendo.|  
|`Property`|Opcional. Define una propiedad que sea miembro de la interfaz.|  
|`Function`|Opcional. Define un `Function` procedimiento que sea miembro de la interfaz.|  
|`Sub`|Opcional. Define un `Sub` procedimiento que sea miembro de la interfaz.|  
|`Event`|Opcional. Define un evento que sea miembro de la interfaz.|  
|`Interface`|Opcional. Define una interfaz que está anidada dentro de esta interfaz. La definición de interfaz anidada debe finalizar con un `End Interface` instrucción.|  
|`Class`|Opcional. Define una clase que es un miembro de la interfaz. La definición de clase de miembro debe terminar con un `End Class` instrucción.|  
|`Structure`|Opcional. Define una estructura que es un miembro de la interfaz. La definición de estructura de miembro debe finalizar con un `End Structure` instrucción.|  
|`membername`|Se requiere para cada propiedad, procedimiento, evento, interfaz, clase o estructura definida como un miembro de la interfaz. Nombre del miembro.|  
|`End Interface`|Termina la definición de `Interface`.|  
  
## <a name="remarks"></a>Comentarios  
 Un *interfaz* define un conjunto de miembros, como las propiedades y los procedimientos que las clases y estructuras pueden implementar. La interfaz define solo las firmas de los miembros y no sus mecanismos internos.  
  
 Una clase o estructura implementa la interfaz proporcionando código para cada miembro definido por la interfaz. Por último, cuando la aplicación crea una instancia de esa clase o estructura, un objeto existe y se ejecuta en la memoria. Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) y [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que el *contexto de declaración* para una interfaz debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 De forma predeterminada para las interfaces [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Anidar Interfaces.** Puede definir una interfaz dentro de otra. Se llama a la interfaz externa del *que contiene la interfaz*, y la interfaz interna se denomina un *interfaz anidada*.  
  
-   **Declaración de miembro.** Cuando se declara una propiedad o procedimiento como miembro de una interfaz, está definiendo solo la *firma* de esa propiedad o ese procedimiento. Esto incluye el tipo de elemento (propiedad o procedimiento), sus parámetros y tipos de parámetro y su tipo de valor devuelto. Por este motivo, la definición de miembro utiliza sólo una línea de código y las instrucciones de terminación como `End Function` o `End Property` no son válidas en una interfaz.  
  
     En cambio, cuando se define una enumeración o estructura, o una clase anidada o interfaz, es necesario incluir a sus miembros de datos.  
  
-   **Modificadores de miembros.** No se puede usar cualquier modificador de acceso al definir miembros de módulo, ni se puede especificar [Shared](../../../visual-basic/language-reference/modifiers/shared.md) ni ningún modificador de procedimiento excepto [sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md). Puede declarar ningún miembro con [sombras](../../../visual-basic/language-reference/modifiers/shadows.md), y se puede usar [predeterminado](../../../visual-basic/language-reference/modifiers/default.md) al definir una propiedad, así como [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) o [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Herencia.** Si usa la interfaz de la [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), puede especificar una o varias interfaces bases. Puede heredar de dos interfaces incluso si cada uno de ellos define un miembro con el mismo nombre. Si lo hace, el código de implementación debe utilizar la calificación de nombres para especificar qué miembro se implementa.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo. Por ejemplo, un `Public` interfaz no puede heredar de un `Friend` interfaz.  
  
     Una interfaz no puede heredar de una interfaz anidada dentro de él.  
  
-   **Implementación de.** Cuando una clase utiliza la [implementa](../../../visual-basic/language-reference/statements/implements-clause.md) instrucción para implementar esta interfaz, debe implementar todos los miembros definidos dentro de la interfaz. Además, cada firma en el código que implementa debe coincidir exactamente con la firma correspondiente definida en esta interfaz. Sin embargo, no tiene el nombre del miembro en el código de implementación para que coincida con el nombre del miembro tal como se define en la interfaz.  
  
     Cuando una clase que implementa un procedimiento, no puede designar el procedimiento como `Shared`.  
  
-   **Propiedad predeterminada.** Una interfaz puede especificar a lo sumo una propiedad como su *propiedad predeterminada*, que puede hacer referencia sin usar el nombre de propiedad. Esta propiedad se especifica mediante la declaración con el [predeterminado](../../../visual-basic/language-reference/modifiers/default.md) modificador.  
  
     Tenga en cuenta que esto significa que una interfaz puede definir una propiedad predeterminada solo si no hereda ninguna.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Todos los miembros de interfaz tienen implícitamente [pública](../../../visual-basic/language-reference/modifiers/public.md) acceso. No se puede utilizar cualquier modificador de acceso al definir a un miembro. Sin embargo, una clase que implementa la interfaz puede declarar un nivel de acceso para cada miembro implementado.  
  
     Si asigna una instancia de clase a una variable, el nivel de acceso de sus miembros puede depender de si el tipo de datos de la variable es la interfaz subyacente o la clase de implementación. Esto se ilustra en el siguiente ejemplo:  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Si tiene acceso a los miembros de clase a través de `varAsInterface`, tienen acceso público. Sin embargo, si tiene acceso a los miembros a través de `varAsClass`, `Sub` procedimiento `doSomething` tiene acceso privado.  
  
-   **Ámbito.** Es una interfaz en el ámbito de su espacio de nombres, clase, estructura o módulo.  
  
     El ámbito de cada miembro de interfaz es toda la interfaz.  
  
-   **Duración.** Una interfaz no sí tiene una duración, ni tampoco a sus miembros. Cuando una clase implementa una interfaz y un objeto se crea como una instancia de que la clase, el objeto tiene una duración dentro de la aplicación en el que se está ejecutando. Para obtener más información, vea "Duración" en [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Interface` instrucción para definir una interfaz denominada `thisInterface`, que debe implementarse con un `Property` instrucción y un `Function` instrucción.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Tenga en cuenta que el `Property` y `Function` instrucciones no crea nuevos bloques que terminan con `End Property` y `End Function` dentro de la interfaz. La interfaz define solo las firmas de sus miembros. El completo `Property` y `Function` bloques aparecen en una clase que implementa `thisInterface`.  
  
## <a name="see-also"></a>Vea también

- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
