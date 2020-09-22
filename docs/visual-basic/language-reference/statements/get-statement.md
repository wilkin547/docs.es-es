---
title: Get (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 3da6c099b3f43a144484eaddf58605609eb0bbfe
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866200"
---
# <a name="get-statement"></a>Get (Instrucción)

Declara un `Get` procedimiento de propiedad que se usa para recuperar el valor de una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de atributos](attribute-list.md).|  
|`accessmodifier`|Opcional en, como máximo, una de las `Get` `Set` instrucciones y de esta propiedad. Puede ser uno de los siguientes:<br /><br /> -   [Contra](../modifiers/protected.md)<br />-   [Respecto](../modifiers/friend.md)<br />-   [Privada](../modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Opcional. Una o varias instrucciones que se ejecutan cuando `Get` se llama al procedimiento de propiedad.|  
|`End Get`|Obligatorio. Finaliza la definición del procedimiento de `Get` propiedad.|  
  
## <a name="remarks"></a>Comentarios  

 Cada propiedad debe tener un `Get` procedimiento de propiedad a menos que se marque la propiedad `WriteOnly` . El `Get` procedimiento se utiliza para devolver el valor actual de la propiedad.  
  
 Visual Basic llama automáticamente al procedimiento de una propiedad `Get` cuando una expresión solicita el valor de la propiedad.  
  
 El cuerpo de la declaración de propiedad solo puede contener los procedimientos y de la propiedad `Get` `Set` entre la [instrucción Property](property-statement.md) y la `End Property` instrucción. No puede almacenar nada que no sea esos procedimientos. En concreto, no puede almacenar el valor actual de la propiedad. Debe almacenar este valor fuera de la propiedad, porque si lo almacena dentro de cualquiera de los procedimientos de propiedad, el otro procedimiento de propiedad no podrá tener acceso a él. El enfoque habitual es almacenar el valor en una variable [privada](../modifiers/private.md) declarada en el mismo nivel que la propiedad. Debe definir un `Get` procedimiento dentro de la propiedad a la que se aplica.  
  
 El `Get` procedimiento tiene como valor predeterminado el nivel de acceso de la propiedad que lo contiene a menos que use `accessmodifier` en la `Get` instrucción.  
  
## <a name="rules"></a>Reglas  
  
- **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` procedimiento o `Set` , pero no para ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si se declara la propiedad `Friend` , puede declarar el `Get` procedimiento `Private` , pero no `Public` .  
  
     Si está definiendo una `ReadOnly` propiedad, el `Get` procedimiento representa toda la propiedad. No se puede declarar un nivel de acceso diferente para `Get` , ya que esto establecería dos niveles de acceso para la propiedad.  
  
- **Tipo de valor devuelto.** La [instrucción Property](property-statement.md) puede declarar el tipo de datos del valor que devuelve. El `Get` procedimiento devuelve automáticamente ese tipo de datos. Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.  
  
     Si la `Property` instrucción no especifica `returntype` , el procedimiento devuelve `Object` .  
  
## <a name="behavior"></a>Comportamiento  
  
- **Devolver de un procedimiento.** Cuando el `Get` procedimiento vuelve al código de llamada, la ejecución continúa dentro de la instrucción que solicitó el valor de propiedad.  
  
     `Get` los procedimientos de propiedad pueden devolver un valor mediante la [instrucción return](return-statement.md) o asignando el valor devuelto al nombre de la propiedad. Para obtener más información, vea el tema sobre el valor devuelto en la [instrucción function](function-statement.md).  
  
     Las `Exit Property` `Return` instrucciones y producen una salida inmediata de un procedimiento de propiedad. Cualquier número de `Exit Property` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Property` e `Return` instrucciones.  
  
- **Valor devuelto.** Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de la propiedad o incluirlo en una [instrucción return](return-statement.md). La `Return` instrucción asigna simultáneamente el `Get` valor devuelto del procedimiento y sale del procedimiento.  
  
     Si utiliza `Exit Property` sin asignar un valor al nombre de la propiedad, el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos de la propiedad. Para obtener más información, vea el tema sobre el valor devuelto en la [instrucción function](function-statement.md).  
  
     En el ejemplo siguiente se muestran dos maneras en que la propiedad de solo lectura `quoteForTheDay` puede devolver el valor contenido en la variable privada `quoteValue` .  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `Get` instrucción para devolver el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Consulte también

- [Set (instrucción)](set-statement.md)
- [Property Statement](property-statement.md)
- [Instrucción Exit](exit-statement.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Tutorial: Definir clases](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
