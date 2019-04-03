---
title: Estructuras y clases (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: 3635729705520518d4c950f8a79da7d1249285bf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841620"
---
# <a name="structures-and-classes-visual-basic"></a>Estructuras y clases (Visual Basic)
Visual Basic unifica la sintaxis para las estructuras y clases, con lo que ambas entidades admiten la mayoría de las mismas características. Sin embargo, también hay diferencias importantes entre las clases y estructuras.  
  
 Las clases tienen la ventaja de ser tipos de referencia, pasando una referencia es más eficaz que se pasa una variable de estructura con todos sus datos. Por otro lado, las estructuras no requieren la asignación de memoria del montón global.  
  
 Dado que no se puede heredar de una estructura, estructuras deben usarse sólo para objetos que no es necesario que se extenderá. Utilice estructuras cuando el objeto que desea crear tiene un tamaño de instancia pequeña y tener en cuenta las características de rendimiento de las clases y estructuras.  
  
## <a name="similarities"></a>Similitudes  
 Estructuras y clases son similares en los siguientes aspectos:  
  
-   Ambos son *contenedor* tipos, lo que significa que contienen otros tipos como miembros.  
  
-   Ambas tienen miembros, que pueden incluir constructores, métodos, propiedades, campos, constantes, enumeraciones, eventos y controladores de eventos. Sin embargo, no confunda estos miembros con el declarado *elementos* de una estructura.  
  
-   Niveles de acceso pueden haber individualizados los miembros de ambos. Por ejemplo, se puede declarar un miembro `Public` y otra `Private`.  
  
-   Ambos pueden implementar interfaces.  
  
-   Ambos pueden tener constructores compartidos, con o sin parámetros.  
  
-   Ambas pueden exponer una *propiedad predeterminada*, siempre que la propiedad tiene al menos un parámetro.  
  
-   Ambos pueden declarar y provocar eventos, y ambas pueden declarar a los delegados.  
  
## <a name="differences"></a>Diferencias  
 Estructuras y clases difieren en las siguientes indicaciones:  
  
-   Las estructuras son *los tipos de valor*; las clases son *hacen referencia a tipos*. Una variable de un tipo de estructura contiene datos de la estructura, en lugar que contiene una referencia a los datos como un tipo de clase.  
  
-   Estructuras de utilizar asignación de la pila; las clases utilizan la asignación del montón.  
  
-   Todos los elementos de estructura son `Public` de forma predeterminada; la clase variables y constantes son `Private` de forma predeterminada, mientras que otros miembros de clase son `Public` de forma predeterminada. Este comportamiento para los miembros de clase proporciona compatibilidad con el sistema de Visual Basic 6.0 de los valores predeterminados.  
  
-   Una estructura debe tener al menos no compartido no compartido, o variable no personalizado elemento eventos; una clase puede estar completamente vacía.  
  
-   Elementos de la estructura no se pueden declarar como `Protected`; los miembros de clase pueden.  
  
-   Un procedimiento de estructura puede controlar eventos solo si es un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedimiento y sólo por medio de la [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md); cualquier procedimiento de clase puede controlar eventos, mediante cualquiera de los [ Controla](../../../../visual-basic/language-reference/statements/handles-clause.md) palabra clave o el `AddHandler` instrucción. Para más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
-   Las declaraciones de variables de estructura no pueden especificar inicializadores o tamaños iniciales para matrices; las declaraciones de variable de clase pueden.  
  
-   Las estructuras heredan implícitamente de la <xref:System.ValueType?displayProperty=nameWithType> clase y no puede heredar de cualquier otro tipo; las clases pueden heredar de cualquier clase o clases distinto <xref:System.ValueType?displayProperty=nameWithType>.  
  
-   Las estructuras no son heredables; las clases son.  
  
-   Nunca se terminan las estructuras de modo que nunca llame common language runtime (CLR) los <xref:System.Object.Finalize%2A> método en una estructura; las clases se terminan por el recolector de elementos no utilizados (GC), que llama a <xref:System.Object.Finalize%2A> en una clase cuando detecta que no hay referencias activas restantes.  
  
-   Una estructura no requiere un constructor; realiza una clase.  
  
-   Las estructuras pueden tener constructores no compartidos únicamente si toman parámetros; las clases pueden tenerlos con o sin parámetros.  
  
 Cada estructura tiene un constructor implícito público sin parámetros. Este constructor inicializa de elementos de datos el de la estructura en sus valores predeterminados. No se puede volver a definir este comportamiento.  
  
## <a name="instances-and-variables"></a>Instancias y Variables  
 Dado que las estructuras son tipos de valor, cada variable de estructura permanentemente está enlazado a una instancia de estructura individual. Pero las clases son tipos de referencia y una variable de objeto puede hacer referencia a varias instancias de clase en momentos diferentes. Esta distinción afecta al uso de estructuras y clases de las maneras siguientes:  
  
-   **Inicialización.** Una variable de estructura incluye implícitamente una inicialización de los elementos mediante el constructor sin parámetros de la estructura. Por lo tanto, `Dim s As struct1` es equivalente a `Dim s As struct1 = New struct1()`.  
  
-   **Asignación de Variables.** Al asignar una variable de estructura a otro, o pasar una instancia de la estructura a un argumento de procedimiento, se copian los valores actuales de todos los elementos de la variable a la nueva estructura. Al asignar una variable de objeto a otro, o pasar una variable de objeto a un procedimiento, se copia solo el puntero de referencia.  
  
-   **Asignar nada.** Puede asignar el valor [nada](../../../../visual-basic/language-reference/nothing.md) a una estructura variable, pero la instancia continúa va a asociar a la variable. Todavía puede llamar a sus métodos y tener acceso a sus elementos de datos, aunque se reinicializan elementos variable mediante la asignación.  
  
     En cambio, si establece una variable de objeto en `Nothing`, desasocia cualquier instancia de clase y no se puede obtener acceso a todos los miembros a través de la variable hasta que asigne otra instancia.  
  
-   **Varias instancias.** Una variable de objeto puede tener distintas instancias de clase asignadas a ella en momentos diferentes, y varias variables de objeto pueden hacer referencia a la misma instancia de clase al mismo tiempo. Cambios en los valores de los miembros de clase afectan a dichos miembros cuando se tiene acceso a través de otra variable que apunta a la misma instancia.  
  
     Elementos de estructura, sin embargo, están aislados dentro de su propia instancia. No se reflejan los cambios en sus valores en otras variables de estructura, incluso en otras instancias del mismo `Structure` declaración.  
  
-   **Igualdad.** Comprobar la igualdad de dos estructuras debe realizarse con una elemento por elemento prueba. Se pueden comparar dos variables de objeto mediante el <xref:System.Object.Equals%2A> método. <xref:System.Object.Equals%2A> indica si las dos variables apuntan a la misma instancia.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
