---
title: Estructuras y clases (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08e31481feac7a6184c6b29269d193c749f440ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="structures-and-classes-visual-basic"></a>Estructuras y clases (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]unifica la sintaxis de estructuras y clases, con lo que ambas entidades admiten la mayoría de las mismas características. Sin embargo, también hay diferencias importantes entre las estructuras y clases.  
  
 Las clases tienen la ventaja de ser tipos de referencia: pasar una referencia es más eficaz que se pasa una variable de estructura con todos sus datos. Por otro lado, las estructuras no requieren la asignación de memoria en el montón global.  
  
 Dado que no se puede heredar de una estructura, estructuras de deben usarse solo para los objetos que no es necesario ampliar. Utilice estructuras cuando el objeto que se va a crear tiene un tamaño de instancia pequeña y tener en cuenta las características de rendimiento de las clases y estructuras.  
  
## <a name="similarities"></a>Similitudes  
 Estructuras y clases son similares en los siguientes aspectos:  
  
-   Ambos son *contenedor* tipos, lo que significa que contienen otros tipos como miembros.  
  
-   Ambas tienen miembros, que pueden incluir constructores, métodos, propiedades, campos, constantes, enumeraciones, eventos y controladores de eventos. Sin embargo, es importante no confundir estos miembros con el declarado *elementos* de una estructura.  
  
-   Los miembros de ambos pueden haber niveles de acceso individualizados. Por ejemplo, un miembro puede declararse `Public` y otra `Private`.  
  
-   Ambas pueden implementar interfaces.  
  
-   Ambos pueden tener constructores compartidos, con o sin parámetros.  
  
-   Ambas pueden exponer una *propiedad predeterminada*, siempre que la propiedad tiene al menos un parámetro.  
  
-   Ambos pueden declarar y provocar eventos y ambas pueden declarar a delegados.  
  
## <a name="differences"></a>Diferencias  
 Estructuras y clases son distintas de las indicaciones siguientes:  
  
-   Las estructuras son *los tipos de valor*; las clases son *hacen referencia a tipos*. Una variable de un tipo de estructura contiene datos de la estructura, en lugar de hacerse que contiene una referencia a los datos como un tipo de clase.  
  
-   Estructuras de utilicen asignación de pila; las clases utilizan asignación del montón.  
  
-   Todos los elementos de estructura son `Public` de forma predeterminada; clase variables y constantes son `Private` de forma predeterminada, mientras que otros miembros de clase son `Public` de forma predeterminada. Este comportamiento para los miembros de la clase proporciona compatibilidad con el sistema de Visual Basic 6.0 de valores predeterminados.  
  
-   Una estructura debe tener al menos una no compartido no compartida, o variable no personalizado event, elemento; una clase puede estar completamente vacía.  
  
-   Elementos de estructura no se pueden declarar como `Protected`; los miembros de clase pueden.  
  
-   Un procedimiento de estructura puede controlar eventos si es un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedimiento y solo por medio de la [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md); cualquier procedimiento de clase puede controlar eventos, mediante cualquier la [ Controla](../../../../visual-basic/language-reference/statements/handles-clause.md) palabra clave o el `AddHandler` instrucción. Para más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
-   Declaraciones de variables de estructura no pueden especificar inicializadores o tamaños iniciales para matrices; las declaraciones de variable de clase pueden.  
  
-   Las estructuras heredan implícitamente de la <xref:System.ValueType?displayProperty=nameWithType> clase y no puede heredar de cualquier otro tipo; las clases pueden heredar de cualquier clase o clases distinto de <xref:System.ValueType?displayProperty=nameWithType>.  
  
-   Las estructuras no son heredables; las clases son.  
  
-   Estructuras no se terminan nunca, por ello, common language runtime (CLR) no llama nunca la <xref:System.Object.Finalize%2A> método en una estructura; las clases se terminan por el recolector de elementos no utilizados (GC), que llama a <xref:System.Object.Finalize%2A> en una clase cuando detecta que no hay referencias activas restantes.  
  
-   Una estructura no requiere un constructor; realiza una clase.  
  
-   Las estructuras pueden tener constructores no compartidos únicamente si toman parámetros; las clases pueden tenerlos con o sin parámetros.  
  
 Cada estructura tiene un constructor público implícito sin parámetros. Este constructor inicializa los elementos de datos de la de la estructura con sus valores predeterminados. No se puede volver a definir este comportamiento.  
  
## <a name="instances-and-variables"></a>Instancias y Variables  
 Dado que las estructuras son tipos de valor, cada variable de estructura permanentemente se enlaza a una instancia de estructura individual. Pero las clases son tipos de referencia y una variable de objeto puede hacer referencia a varias instancias de clase en momentos diferentes. Esta distinción afecta al uso de estructuras y clases de las maneras siguientes:  
  
-   **Inicialización.** Una variable de estructura incluye implícitamente una inicialización de los elementos mediante el constructor sin parámetros de la estructura. Por lo tanto, `Dim s As struct1` es equivalente a `Dim s As struct1 = New struct1()`.  
  
-   **Asignación de Variables.** Al asignar una variable de estructura a otra o pasar una instancia de estructura a un argumento de procedimiento, se copian los valores actuales de todos los elementos de la variable a la nueva estructura. Al asignar una variable de objeto a otro, o pasar una variable de objeto a un procedimiento, se copia el puntero de referencia.  
  
-   **Asignar nada.** Puede asignar el valor [nada](../../../../visual-basic/language-reference/nothing.md) a una estructura de variable, pero la instancia continúa estando asociado a la variable. Puede llamar a sus métodos y obteniendo acceso a sus elementos de datos, aunque se reinicializan elementos variables por la asignación.  
  
     En cambio, si establece una variable de objeto en `Nothing`, desasocia desde cualquier instancia de clase y no se puede tener acceso a los miembros a través de la variable hasta que asigne otra instancia.  
  
-   **Varias instancias.** Una variable de objeto puede tener distintas instancias de clase asignados a él en momentos diferentes y varias variables de objeto pueden hacer referencia a la misma instancia de clase al mismo tiempo. Cambios realizados en los valores de los miembros de clase afectan a dichos miembros cuando se tiene acceso a través de otra variable que apunta a la misma instancia.  
  
     Elementos de estructura, sin embargo, están aislados dentro de su propia instancia. Cambios en sus valores no se reflejan en ninguna otra variable de estructura, incluso en otras instancias de la misma `Structure` declaración.  
  
-   **Igualdad.** Comprobar la igualdad de dos estructuras debe realizarse con una prueba de elemento a elemento. Se pueden comparar dos variables de objeto mediante la <xref:System.Object.Equals%2A> método. <xref:System.Object.Equals%2A>indica si las dos variables apuntan a la misma instancia.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
