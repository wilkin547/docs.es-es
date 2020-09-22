---
title: Clave
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 582ed5bb67b9c7504e736710aa4649cffb12ef45
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867996"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)

La `Key` palabra clave le permite especificar el comportamiento de las propiedades de los tipos anónimos. Solo las propiedades que se designan como propiedades clave participan en las pruebas de igualdad entre las instancias de tipo anónimo o el cálculo de los valores de código hash. No se pueden cambiar los valores de las propiedades de clave.  
  
 Designe una propiedad de un tipo anónimo como una propiedad de clave colocando la palabra clave `Key` delante de su declaración en la lista de inicialización. En el ejemplo siguiente, `Airline` y `FlightNo` son propiedades clave, pero `Gate` no lo es.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 Cuando se crea un nuevo tipo anónimo, hereda directamente de <xref:System.Object> . El compilador invalida tres miembros heredados: <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> y <xref:System.Object.ToString%2A> . El código de invalidación que se produce para <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> se basa en las propiedades de clave. Si no hay ninguna propiedad clave en el tipo, <xref:System.Object.GetHashCode%2A> y <xref:System.Object.Equals%2A> no se reemplazan.  
  
## <a name="equality"></a>Igualdad  

 Dos instancias de tipo anónimo son iguales si son instancias del mismo tipo y si los valores de sus propiedades de clave son iguales. En los ejemplos siguientes, `flight2` es igual a `flight1` en el ejemplo anterior porque son instancias del mismo tipo anónimo y tienen valores coincidentes para sus propiedades de clave. Sin embargo, `flight3` no es igual a `flight1` porque tiene un valor diferente para una propiedad de clave, `FlightNo` . `flight4`La instancia no es del mismo tipo que `flight1` porque designan propiedades diferentes como propiedades clave.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Si dos instancias de se declaran solo con propiedades que no son de clave, idénticas en nombre, tipo, orden y valor, las dos instancias de no son iguales. Una instancia sin propiedades de clave es igual a sí misma.  
  
 Para obtener más información sobre las condiciones en las que dos instancias de tipos anónimos son instancias del mismo tipo anónimo, vea [tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Cálculo de código hash  

 Al igual <xref:System.Object.Equals%2A> que, la función hash que se define en <xref:System.Object.GetHashCode%2A> para un tipo anónimo se basa en las propiedades clave del tipo. En los siguientes ejemplos se muestra la interacción entre las propiedades de clave y los valores de código hash.  
  
 Las instancias de un tipo anónimo que tienen los mismos valores para todas las propiedades de clave tienen el mismo valor de código hash, incluso si las propiedades que no son de clave no tienen valores coincidentes. La siguiente instrucción devuelve `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Las instancias de un tipo anónimo que tienen valores diferentes para una o varias propiedades de clave tienen diferentes valores de código hash. La siguiente instrucción devuelve `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Las instancias de tipos anónimos que designan propiedades diferentes como propiedades clave no son instancias del mismo tipo. Tienen valores de código hash diferentes incluso cuando los nombres y valores de todas las propiedades son iguales. La siguiente instrucción devuelve `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Valores de solo lectura  

 No se pueden cambiar los valores de las propiedades de clave. Por ejemplo, en `flight1` los ejemplos anteriores, los `Airline` campos y `FlightNo` son de solo lectura, pero `Gate` se pueden cambiar.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>Consulte también

- [Definición de tipo anónimo](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Procedimiento para deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
