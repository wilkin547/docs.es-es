---
title: Instrucción Interface
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 02d258084aaaa53dcc559cfaa0dec27556351037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404491"
---
# <a name="interface-statement-visual-basic"></a>Instrucción Interface (Visual Basic)
Declara el nombre de una interfaz e introduce las definiciones de los miembros que la interfaz contiene.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
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
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de atributos](attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Pública](../modifiers/public.md)<br />-   [Contra](../modifiers/protected.md)<br />-   [Respecto](../modifiers/friend.md)<br />-   [Privada](../modifiers/private.md)<br />-  [Friend protegido](../modifiers/protected-friend.md)<br/>- [Privado protegido](../modifiers/private-protected.md)<br /><br /> Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [Shadows](../modifiers/shadows.md).|  
|`name`|Necesario. Nombre de esta interfaz. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una interfaz genérica.|  
|`typelist`|Obligatorio si se usa la palabra clave [of](of-clause.md) . Lista de parámetros de tipo para esta interfaz. Opcionalmente, cada parámetro de tipo se puede declarar como variante mediante el uso `In` de los `Out` Modificadores genéricos y. Consulte [lista de tipos](type-list.md).|  
|`Inherits`|Opcional. Indica que esta interfaz hereda los atributos y los miembros de otra interfaz o interfaces. Vea [Inherits (instrucción](inherits-statement.md)).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Inherits`. Los nombres de las interfaces de las que se deriva esta interfaz.|  
|`modifiers`|Opcional. Modificadores adecuados para el miembro de interfaz que se está definiendo.|  
|`Property`|Opcional. Define una propiedad que es miembro de la interfaz.|  
|`Function`|Opcional. Define un `Function` procedimiento que es miembro de la interfaz.|  
|`Sub`|Opcional. Define un `Sub` procedimiento que es miembro de la interfaz.|  
|`Event`|Opcional. Define un evento que es miembro de la interfaz.|  
|`Interface`|Opcional. Define una interfaz que está anidada dentro de esta interfaz. La definición de interfaz anidada debe terminar con una `End Interface` instrucción.|  
|`Class`|Opcional. Define una clase que es miembro de la interfaz. La definición de clase de miembro debe terminar con una `End Class` instrucción.|  
|`Structure`|Opcional. Define una estructura que es un miembro de la interfaz. La definición de la estructura de miembro debe terminar con una `End Structure` instrucción.|  
|`membername`|Se requiere para cada propiedad, procedimiento, evento, interfaz, clase o estructura definidos como miembro de la interfaz. Nombre del miembro.|  
|`End Interface`|Termina la definición de `Interface`.|  
  
## <a name="remarks"></a>Observaciones  
 Una *interfaz* define un conjunto de miembros, como propiedades y procedimientos, que las clases y estructuras pueden implementar. La interfaz solo define las firmas de los miembros y no sus trabajos internos.  
  
 Una clase o estructura implementa la interfaz proporcionando código para cada miembro definido por la interfaz. Por último, cuando la aplicación crea una instancia a partir de esa clase o estructura, existe un objeto y se ejecuta en la memoria. Para obtener más información, vea [objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md) e [interfaces](../../programming-guide/language-features/interfaces/index.md).  
  
 `Interface` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que el contexto de la *declaración* de una interfaz debe ser un archivo de código fuente, un espacio de nombres, una clase, una estructura, un módulo o una interfaz y no puede ser un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 El acceso predeterminado de las interfaces es [Friend](../modifiers/friend.md) . Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
- **Anidar interfaces.** Puede definir una interfaz dentro de otra. La interfaz externa se denomina *interfaz contenedora*y la interfaz interna se denomina *interfaz anidada*.  
  
- **Declaración de miembros.** Cuando se declara una propiedad o un procedimiento como miembro de una interfaz, solo se define la *firma* de esa propiedad o procedimiento. Esto incluye el tipo de elemento (propiedad o procedimiento), sus parámetros y tipos de parámetro, y su tipo de valor devuelto. Por este motivo, la definición de miembro solo utiliza una línea de código y las instrucciones de terminación como `End Function` o `End Property` no son válidas en una interfaz.  
  
     Por el contrario, cuando se define una enumeración o una estructura, o una clase o interfaz anidada, es necesario incluir sus miembros de datos.  
  
- **Modificadores de miembro.** No se puede usar ningún modificador de acceso al definir miembros de módulo, ni se puede especificar un modificador de procedimiento [compartido](../modifiers/shared.md) o Any excepto [sobrecargas](../modifiers/overloads.md). Puede declarar cualquier miembro con [sombras](../modifiers/shadows.md), y puede usar el [valor predeterminado](../modifiers/default.md) al definir una propiedad, así como [ReadOnly](../modifiers/readonly.md) o [WriteOnly](../modifiers/writeonly.md).  
  
- **Ella.** Si la interfaz utiliza la [instrucción Inherits](inherits-statement.md), puede especificar una o varias interfaces base. Puede heredar de dos interfaces incluso si cada una de ellas define un miembro con el mismo nombre. Si lo hace, el código de implementación debe usar la calificación de nombre para especificar qué miembro está implementando.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo. Por ejemplo, una `Public` interfaz no puede heredar de una `Friend` interfaz.  
  
     Una interfaz no puede heredar de una interfaz anidada dentro de ella.  
  
- **Aplicación.** Cuando una clase usa la instrucción [Implements](implements-clause.md) para implementar esta interfaz, debe implementar todos los miembros definidos en la interfaz. Además, cada firma del código que implementa debe coincidir exactamente con la firma correspondiente definida en esta interfaz. Sin embargo, el nombre del miembro en el código de implementación no tiene que coincidir con el nombre de miembro definido en la interfaz.  
  
     Cuando una clase implementa un procedimiento, no puede designar el procedimiento como `Shared` .  
  
- **Propiedad predeterminada.** Una interfaz puede especificar como máximo una propiedad como su *propiedad predeterminada*, a la que se puede hacer referencia sin usar el nombre de la propiedad. Para especificar este tipo de propiedad, se declara con el modificador [predeterminado](../modifiers/default.md) .  
  
     Tenga en cuenta que esto significa que una interfaz solo puede definir una propiedad predeterminada si hereda ninguno.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Todos los miembros de interfaz tienen acceso [público](../modifiers/public.md) de forma implícita. No se puede usar ningún modificador de acceso al definir un miembro. Sin embargo, una clase que implementa la interfaz puede declarar un nivel de acceso para cada miembro implementado.  
  
     Si asigna una instancia de clase a una variable, el nivel de acceso de sus miembros puede depender de si el tipo de datos de la variable es la interfaz subyacente o la clase de implementación. Esto se ilustra en el siguiente ejemplo.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Si tiene acceso a los miembros de clase a través `varAsInterface` de, todos tienen acceso público. Sin embargo, si obtiene acceso a los miembros a través de `varAsClass` , el `Sub` procedimiento `doSomething` tiene acceso privado.  
  
- **Ámbito.** Una interfaz está en el ámbito a lo largo de su espacio de nombres, clase, estructura o módulo.  
  
     El ámbito de cada miembro de interfaz es toda la interfaz.  
  
- **Validez.** Una interfaz no tiene una duración, ni sus miembros. Cuando una clase implementa una interfaz y un objeto se crea como una instancia de esa clase, el objeto tiene una duración dentro de la aplicación en la que se está ejecutando. Para obtener más información, vea "Lifetime" en la [instrucción Class](class-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la `Interface` instrucción para definir una interfaz denominada `thisInterface` , que debe implementarse con una `Property` instrucción y una `Function` instrucción.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Tenga en cuenta que las `Property` `Function` instrucciones y no presentan los bloques que terminan con `End Property` y `End Function` dentro de la interfaz. La interfaz define solo las firmas de sus miembros. Los `Property` bloques y completos `Function` aparecen en una clase que implementa `thisInterface` .  
  
## <a name="see-also"></a>Consulte también

- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
- [Instrucción Class](class-statement.md)
- [Module (Instrucción)](module-statement.md)
- [Structure (Instrucción)](structure-statement.md)
- [Property Statement](property-statement.md)
- [Instrucción Function](function-statement.md)
- [Instrucción Sub](sub-statement.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [De](../modifiers/in-generic-modifier.md)
- [Enuncia](../modifiers/out-generic-modifier.md)
