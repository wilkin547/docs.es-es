---
title: Key (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 695f356f44bfd6ea5ad3c0a977ec31ddfbea2b05
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668228"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
El `Key` palabra clave le permite especificar el comportamiento de las propiedades de tipos anónimos. Solo las propiedades se designa como propiedades clave participan en las pruebas de igualdad entre las instancias de tipo anónimo, o un cálculo de valores de código hash. No se puede cambiar los valores de las propiedades de clave.  
  
 Designar una propiedad de un tipo anónimo como una propiedad de clave mediante la colocación de la palabra clave `Key` delante de su declaración en la lista de inicialización. En el ejemplo siguiente, `Airline` y `FlightNo` son propiedades clave, pero `Gate` no es.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 Cuando se crea un nuevo tipo anónimo, hereda directamente de <xref:System.Object>. El compilador reemplaza tres miembros heredados: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, y <xref:System.Object.ToString%2A>. El código de invalidación que se genera para <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> se basa en las propiedades de clave. Si no hay ninguna propiedad clave en el tipo, <xref:System.Object.GetHashCode%2A> y <xref:System.Object.Equals%2A> no se sobrescriben.  
  
## <a name="equality"></a>Igualdad  
 Dos instancias de tipo anónimo son iguales si son instancias del mismo tipo y si los valores de sus propiedades clave son iguales. En los ejemplos siguientes, `flight2` es igual a `flight1` del ejemplo anterior porque son instancias del mismo anónimo tipo y tienen valores para las propiedades de clave coincidentes. Sin embargo, `flight3` no es igual a `flight1` porque tiene un valor diferente para una propiedad clave, `FlightNo`. Instancia `flight4` no es el mismo tipo que `flight1` porque designan diferentes propiedades como propiedades de clave.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 Si dos instancias se declaran con sólo clave no propiedades, idénticas en nombre, tipo, orden y valor, las dos instancias no son iguales. Una instancia sin propiedades de clave es igual solo a sí mismo.  
  
 Para obtener más información acerca de las condiciones en las que dos instancias de tipo anónimo son instancias del mismo tipo anónimo, vea [tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Cálculo del código hash  
 Al igual que <xref:System.Object.Equals%2A>, la función hash que se define en <xref:System.Object.GetHashCode%2A> para un tipo anónimo se basa en las propiedades clave del tipo. Los ejemplos siguientes muestran la interacción entre las propiedades de clave y valor hash de los valores de código.  
  
 Instancias de un tipo anónimo que tienen los mismos valores para todas las propiedades de clave tienen el mismo valor de código hash, incluso si las propiedades que no son de clave no tienen valores coincidentes. La siguiente instrucción devuelve `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 Las instancias de un tipo anónimo que tienen valores diferentes para una o varias propiedades claves tienen valores de código hash diferente. La siguiente instrucción devuelve `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 Las instancias de tipos anónimos que designan las diferentes propiedades como propiedades de clave no son instancias del mismo tipo. Tienen valores de código hash diferente incluso cuando los nombres y valores de todas las propiedades son iguales. La siguiente instrucción devuelve `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a>Valores de solo lectura  
 No se puede cambiar los valores de las propiedades de clave. Por ejemplo, en `flight1` en los ejemplos anteriores, el `Airline` y `FlightNo` campos son de solo lectura, pero `Gate` puede cambiarse.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a>Vea también
- [Definición de tipo anónimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Cómo: Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
