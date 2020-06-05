---
title: Estructuras y clases
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: d252d9216a9b825ad0663a5779d7ce7f81fa9011
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393577"
---
# <a name="structures-and-classes-visual-basic"></a>Estructuras y clases (Visual Basic)
Visual Basic unifica la sintaxis de las estructuras y las clases, con el resultado de que ambas entidades admiten la mayoría de las mismas características. Sin embargo, también hay diferencias importantes entre estructuras y clases.  
  
 Las clases tienen la ventaja de ser tipos de referencia: pasar una referencia es más eficaz que pasar una variable de estructura con todos sus datos. Por otro lado, las estructuras no requieren la asignación de memoria en el montón global.  
  
 Dado que no se puede heredar de una estructura, las estructuras deben usarse solo para los objetos que no es necesario extender. Use estructuras cuando el objeto que desea crear tenga un tamaño de instancia pequeño y tenga en cuenta las características de rendimiento de clases frente a estructuras.  
  
## <a name="similarities"></a>Similitudes  
 Las estructuras y clases son similares en los siguientes aspectos:  
  
- Ambos son tipos de *contenedor* , lo que significa que contienen otros tipos como miembros.  
  
- Ambos tienen miembros, que pueden incluir constructores, métodos, propiedades, campos, constantes, enumeraciones, eventos y controladores de eventos. Sin embargo, no confunda estos miembros con los *elementos* declarados de una estructura.  
  
- Los miembros de ambos pueden tener niveles de acceso individualizados. Por ejemplo, se puede declarar un miembro `Public` y otro `Private` .  
  
- Ambos pueden implementar interfaces.  
  
- Ambos pueden tener constructores compartidos, con o sin parámetros.  
  
- Ambos pueden exponer una *propiedad predeterminada*, siempre que la propiedad tome al menos un parámetro.  
  
- Ambos pueden declarar y generar eventos y ambos pueden declarar delegados.  
  
## <a name="differences"></a>Diferencias  
 Las estructuras y las clases difieren en los siguientes detalles:  
  
- Las estructuras son *tipos de valor*; las clases son *tipos de referencia*. Una variable de un tipo de estructura contiene los datos de la estructura, en lugar de contener una referencia a los datos como un tipo de clase.  
  
- Las estructuras usan la asignación de la pila; las clases usan la asignación del montón.  
  
- De forma predeterminada, todos los elementos de estructura son `Public` variables y constantes de clase `Private` , mientras que otros miembros de clase son `Public` de forma predeterminada. Este comportamiento para los miembros de clase proporciona compatibilidad con el sistema Visual Basic de los valores predeterminados 6,0.  
  
- Una estructura debe tener al menos una variable no compartida o un elemento de evento no compartido no personalizado; una clase puede estar completamente vacía.  
  
- Los elementos de estructura no se pueden declarar como `Protected` ; los miembros de clase pueden.  
  
- Un procedimiento de estructura solo puede controlar eventos si se trata de un procedimiento [compartido](../../../language-reference/modifiers/shared.md) `Sub` y solo por medio de la [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md); cualquier procedimiento de clase puede controlar eventos mediante la palabra clave [Handles](../../../language-reference/statements/handles-clause.md) o la `AddHandler` instrucción. Para más información, vea [Eventos](../events/index.md).  
  
- Las declaraciones de variables de estructura no pueden especificar inicializadores ni tamaños iniciales para matrices; las declaraciones de variables de clase pueden.  
  
- Las estructuras heredan implícitamente de la <xref:System.ValueType?displayProperty=nameWithType> clase y no pueden heredar de ningún otro tipo; las clases pueden heredar de cualquier clase o clases que no sean <xref:System.ValueType?displayProperty=nameWithType> .  
  
- Las estructuras no se pueden heredar; las clases son.  
  
- Las estructuras nunca finalizan, por lo que el Common Language Runtime (CLR) nunca llama al <xref:System.Object.Finalize%2A> método en ninguna estructura; las clases las termina el recolector de elementos no utilizados (GC), que llama a <xref:System.Object.Finalize%2A> en una clase cuando detecta que no quedan referencias activas.  
  
- Una estructura no requiere un constructor; una clase.  
  
- Las estructuras pueden tener constructores no compartidos solo si toman parámetros; las clases pueden tenerlos con o sin parámetros.  
  
 Cada estructura tiene un constructor público implícito sin parámetros. Este constructor inicializa todos los elementos de datos de la estructura en sus valores predeterminados. Este comportamiento no se puede volver a definir.  
  
## <a name="instances-and-variables"></a>Instancias y variables  
 Dado que las estructuras son tipos de valor, cada variable de estructura se enlaza de forma permanente a una instancia de la estructura individual. Pero las clases son tipos de referencia y una variable de objeto puede hacer referencia a varias instancias de clase en momentos diferentes. Esta distinción afecta al uso de estructuras y clases de las siguientes maneras:  
  
- **Inicial.** Una variable de estructura incluye implícitamente una inicialización de los elementos mediante el constructor sin parámetros de la estructura. Por lo tanto, `Dim s As struct1` es equivalente a `Dim s As struct1 = New struct1()` .  
  
- **Asignación de variables.** Cuando se asigna una variable de estructura a otra, o se pasa una instancia de la estructura a un argumento de procedimiento, los valores actuales de todos los elementos variables se copian en la nueva estructura. Al asignar una variable de objeto a otra, o pasar una variable de objeto a un procedimiento, solo se copia el puntero de referencia.  
  
- **No asignar nada.** Puede asignar el valor [Nothing](../../../language-reference/nothing.md) a una variable de estructura, pero la instancia continúa asociada a la variable. Todavía puede llamar a sus métodos y obtener acceso a sus elementos de datos, aunque la asignación reinicializa los elementos de variable.  
  
     Por el contrario, si se establece una variable de objeto en `Nothing` , se desasocia de cualquier instancia de clase y no se puede tener acceso a los miembros a través de la variable hasta que se le asigne otra instancia.  
  
- **Varias instancias.** Una variable de objeto puede tener asignadas instancias de clase diferentes en momentos diferentes, y varias variables de objeto pueden hacer referencia a la misma instancia de clase al mismo tiempo. Los cambios que realice en los valores de los miembros de clase afectan a esos miembros cuando se obtiene acceso a ellos a través de otra variable que apunta a la misma instancia.  
  
     Los elementos de la estructura, sin embargo, están aislados dentro de su propia instancia. Los cambios en sus valores no se reflejan en otras variables de estructura, incluso en otras instancias de la misma `Structure` declaración.  
  
- **Determinar.** Las pruebas de igualdad de dos estructuras deben realizarse con una prueba elemento a elemento. Se pueden comparar dos variables de objeto mediante el <xref:System.Object.Equals%2A> método. <xref:System.Object.Equals%2A>indica si las dos variables apuntan a la misma instancia.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos](index.md)
- [Tipos de datos compuestos](composite-data-types.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Estructuras](structures.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Estructuras y otros elementos de programación](structures-and-other-programming-elements.md)
- [Objetos y clases](../objects-and-classes/index.md)
