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
ms.openlocfilehash: 9560faf90d531c32f104dbd053a7c1f5584cfb1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351170"
---
# <a name="get-statement"></a>Get (Instrucción)
Declara un procedimiento de propiedad `Get` que se usa para recuperar el valor de una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional en, como máximo, una de las instrucciones `Get` y `Set` de esta propiedad. Puede ser uno de los siguientes:<br /><br /> -   [protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [privado](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Opcional. Una o varias instrucciones que se ejecutan cuando se llama al procedimiento de propiedad `Get`.|  
|`End Get`|Obligatorio. Finaliza la definición del procedimiento de propiedad `Get`.|  
  
## <a name="remarks"></a>Comentarios  
 Cada propiedad debe tener un procedimiento de propiedad `Get` a menos que la propiedad esté marcada `WriteOnly`. El procedimiento `Get` se utiliza para devolver el valor actual de la propiedad.  
  
 Visual Basic llama automáticamente al procedimiento `Get` de una propiedad cuando una expresión solicita el valor de la propiedad.  
  
 El cuerpo de la declaración de propiedad solo puede contener los procedimientos `Get` y `Set` de la propiedad entre la [instrucción Property](../../../visual-basic/language-reference/statements/property-statement.md) y la instrucción `End Property`. No puede almacenar nada que no sea esos procedimientos. En concreto, no puede almacenar el valor actual de la propiedad. Debe almacenar este valor fuera de la propiedad, porque si lo almacena dentro de cualquiera de los procedimientos de propiedad, el otro procedimiento de propiedad no podrá tener acceso a él. El enfoque habitual es almacenar el valor en una variable [privada](../../../visual-basic/language-reference/modifiers/private.md) declarada en el mismo nivel que la propiedad. Debe definir un procedimiento de `Get` dentro de la propiedad a la que se aplica.  
  
 El procedimiento `Get` toma como valor predeterminado el nivel de acceso de la propiedad que lo contiene a menos que use `accessmodifier` en la instrucción `Get`.  
  
## <a name="rules"></a>Reglas  
  
- **Niveles de acceso mixtos.** Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o el procedimiento de `Set`, pero no ambos. Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad. Por ejemplo, si la propiedad se declara `Friend`, puede declarar el `Get` procedimiento `Private`, pero no `Public`.  
  
     Si va a definir una propiedad `ReadOnly`, el procedimiento `Get` representa la propiedad completa. No se puede declarar un nivel de acceso diferente para `Get`, porque esto establecería dos niveles de acceso para la propiedad.  
  
- **Tipo de valor devuelto.** La [instrucción Property](../../../visual-basic/language-reference/statements/property-statement.md) puede declarar el tipo de datos del valor que devuelve. El procedimiento `Get` devuelve automáticamente ese tipo de datos. Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.  
  
     Si la instrucción `Property` no especifica `returntype`, el procedimiento devuelve `Object`.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Devolver de un procedimiento.** Cuando el procedimiento `Get` devuelve al código de llamada, la ejecución continúa dentro de la instrucción que solicitó el valor de propiedad.  
  
     `Get` procedimientos de propiedad pueden devolver un valor mediante la [instrucción return](../../../visual-basic/language-reference/statements/return-statement.md) o asignando el valor devuelto al nombre de la propiedad. Para obtener más información, vea el tema sobre el valor devuelto en la [instrucción function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Las instrucciones `Exit Property` y `Return` producen una salida inmediata de un procedimiento de propiedad. Cualquier número de instrucciones `Exit Property` y `Return` puede aparecer en cualquier parte del procedimiento y se pueden mezclar instrucciones `Exit Property` y `Return`.  
  
- **Valor devuelto.** Para devolver un valor de un procedimiento `Get`, puede asignar el valor al nombre de la propiedad o incluirlo en una [instrucción return](../../../visual-basic/language-reference/statements/return-statement.md). La instrucción `Return` asigna simultáneamente el valor devuelto del procedimiento `Get` y sale del procedimiento.  
  
     Si usa `Exit Property` sin asignar un valor al nombre de la propiedad, el procedimiento `Get` devuelve el valor predeterminado del tipo de datos de la propiedad. Para obtener más información, vea el tema sobre el valor devuelto en la [instrucción function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     En el ejemplo siguiente se muestran dos maneras en las que la propiedad de solo lectura `quoteForTheDay` puede devolver el valor contenido en la variable privada `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la instrucción `Get` para devolver el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Vea también

- [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Tutorial: Definir clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
