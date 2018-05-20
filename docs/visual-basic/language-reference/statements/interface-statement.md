---
title: Instrucción Interface (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 31ff9211034438e225494b916045acd07c37810f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="interface-statement-visual-basic"></a>Instrucción Interface (Visual Basic)
Declara el nombre de una interfaz e introduce las definiciones de los miembros que consta de la interfaz.  
  
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
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Público](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Privado protegido](../../language-reference/modifiers/private-protected.md)<br /><br /> Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Requerido. Nombre de esta interfaz. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una interfaz genérica.|  
|`typelist`|Es obligatorio si se utiliza la [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave. Lista de parámetros de tipo para esta interfaz. Opcionalmente, cada parámetro de tipo puede declararse variante mediante `In` y `Out` modificadores genéricos. Vea [escriba lista](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional. Indica que esta interfaz hereda los atributos y miembros de otra interfaz o interfaces. Vea [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Inherits`. Los nombres de las interfaces del que se deriva esta interfaz.|  
|`modifiers`|Opcional. Modificadores adecuados para el miembro de interfaz que se está definiendo.|  
|`Property`|Opcional. Define una propiedad que sea miembro de la interfaz.|  
|`Function`|Opcional. Define un `Function` procedimiento que sea miembro de la interfaz.|  
|`Sub`|Opcional. Define un `Sub` procedimiento que sea miembro de la interfaz.|  
|`Event`|Opcional. Define un evento que sea miembro de la interfaz.|  
|`Interface`|Opcional. Define una interfaz que está anidada dentro de esta interfaz. La definición de interfaz anidada debe finalizar con un `End Interface` instrucción.|  
|`Class`|Opcional. Define una clase que es un miembro de la interfaz. La definición de clase de miembro debe terminar con un `End Class` instrucción.|  
|`Structure`|Opcional. Define una estructura que es un miembro de la interfaz. La definición de estructura miembro debe finalizar con un `End Structure` instrucción.|  
|`membername`|Se requiere para cada propiedad, procedimiento, evento, interfaz, clase o estructura definida como un miembro de la interfaz. Nombre del miembro.|  
|`End Interface`|Termina la definición de `Interface`.|  
  
## <a name="remarks"></a>Comentarios  
 Un *interfaz* define un conjunto de miembros, como propiedades y procedimientos, que las clases y las estructuras pueden implementar. La interfaz define solo las firmas de los miembros y no sus mecanismos internos.  
  
 Una clase o estructura implementa la interfaz proporcionando código para cada miembro definido por la interfaz. Por último, cuando la aplicación crea una instancia de esa clase o estructura, un objeto existe y se ejecuta en la memoria. Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) y [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que la *contexto de la declaración* para una interfaz debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Interfaces de forma predeterminada, [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Interfaces de anidamiento.** Puede definir una interfaz dentro de otra. La interfaz externa se denomina la *que contiene interfaz*, y la interfaz interna se denomina un *interfaz anidada*.  
  
-   **Declaración de miembros.** Cuando se declara una propiedad o procedimiento como un miembro de una interfaz, está definiendo sólo la *firma* de esa propiedad o procedimiento. Esto incluye el tipo de elemento (propiedad o procedimiento), sus parámetros y tipos de parámetro y su tipo de valor devuelto. Por este motivo, la definición de miembro utiliza una única línea de código e instrucciones de terminación como `End Function` o `End Property` no son válidas en una interfaz.  
  
     En cambio, cuando se define una enumeración o estructura, o una clase anidada o interfaz, es necesario incluir a sus miembros de datos.  
  
-   **Modificadores de miembros.** No puede usar los modificadores de acceso al definir miembros de módulo, ni se puede especificar [Shared](../../../visual-basic/language-reference/modifiers/shared.md) ni ningún modificador de procedimiento excepto [sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md). Puede declarar cualquier miembro con [sombras](../../../visual-basic/language-reference/modifiers/shadows.md), y se puede usar [predeterminado](../../../visual-basic/language-reference/modifiers/default.md) al definir una propiedad, así como [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) o [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Herencia.** Si utiliza la interfaz de la [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), puede especificar una o varias interfaces base. Puede heredar de dos interfaces incluso si cada una definen a un miembro con el mismo nombre. Si lo hace, el código que implementa debe utilizar la calificación de nombres para especificar qué miembro está implementando.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo. Por ejemplo, un `Public` interfaz no puede heredar de un `Friend` interfaz.  
  
     Una interfaz no puede heredar de una interfaz anidada dentro de ella.  
  
-   **Implementación de.** Cuando se utiliza una clase de la [implementa](../../../visual-basic/language-reference/statements/implements-clause.md) instrucción para implementar esta interfaz, debe implementar todos los miembros definidos dentro de la interfaz. Además, cada firma en el código que implementa debe coincidir exactamente con la firma correspondiente definida en esta interfaz. Sin embargo, no tiene el nombre del miembro en el código de implementación para que coincida con el nombre de miembro, como se define en la interfaz.  
  
     Cuando una clase está implementando un procedimiento, no puede designar el procedimiento como `Shared`.  
  
-   **Propiedad Default.** Una interfaz puede especificar a lo sumo una propiedad como su *propiedad predeterminada*, que puede hacer referencia sin usar el nombre de propiedad. Esta propiedad se especifica mediante la declaración con el [predeterminado](../../../visual-basic/language-reference/modifiers/default.md) modificador.  
  
     Tenga en cuenta que esto significa que una interfaz sólo puede definir una propiedad predeterminada si no hereda ninguna.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Todos los miembros de interfaz tienen implícitamente [público](../../../visual-basic/language-reference/modifiers/public.md) acceso. No se puede utilizar ningún modificador de acceso al definir a un miembro. Sin embargo, una clase que implementa la interfaz puede declarar un nivel de acceso para cada miembro implementado.  
  
     Si asigna una instancia de clase a una variable, el nivel de acceso de sus miembros puede depender de si el tipo de datos de la variable es la interfaz subyacente o la clase de implementación. Esto se ilustra en el siguiente ejemplo:  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     Si tiene acceso a los miembros de clase mediante `varAsInterface`, tienen acceso público. Sin embargo, si tiene acceso a los miembros a través de `varAsClass`, `Sub` procedimiento `doSomething` tiene acceso privado.  
  
-   **Ámbito.** Una interfaz está en ámbito a lo largo de su espacio de nombres, una clase, estructura o módulo.  
  
     El ámbito de cada miembro de interfaz es toda la interfaz.  
  
-   **Duración.** Una interfaz no sí tiene una duración, ni tampoco a sus miembros. Cuando una clase implementa una interfaz y un objeto se crea como una instancia de que (clase), el objeto tiene una duración dentro de la aplicación en el que se está ejecutando. Para obtener más información, vea "Duración" en [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Interface` instrucción para definir una interfaz denominada `thisInterface`, que debe implementarse con una `Property` instrucción y un `Function` instrucción.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 Tenga en cuenta que la `Property` y `Function` instrucciones no introducen bloques que terminan con `End Property` y `End Function` dentro de la interfaz. La interfaz define solo las firmas de sus miembros. Toda la `Property` y `Function` bloques aparecen en una clase que implementa `thisInterface`.  
  
## <a name="see-also"></a>Vea también  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
