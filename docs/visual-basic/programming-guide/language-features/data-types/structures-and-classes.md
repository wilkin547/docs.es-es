---
title: Estructuras y clases (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures
- classes [Visual Basic]
- structures, compared to classes
- structures, structure variables
- structure variables
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e7402ec0fcfc279470d39a4919d3b5ec8b5d9dff
ms.lasthandoff: 03/13/2017

---
# <a name="structures-and-classes-visual-basic"></a>Estructuras y clases (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]unifica la sintaxis de estructuras y clases, con lo que ambas entidades admiten prácticamente las mismas características. Sin embargo, también hay diferencias importantes entre las estructuras y clases.  
  
 Las clases tienen la ventaja de ser tipos de referencia: pasar una referencia es más eficiente que pasar una variable de estructura con todos sus datos. Por otro lado, las estructuras no requieren la asignación de memoria en el montón global.  
  
 Porque no se puede heredar de una estructura, estructuras deben usarse sólo para objetos que no se necesite ampliar. Utilice estructuras cuando el objeto que se va a crear tiene un tamaño de instancia pequeña y tener en cuenta las características de rendimiento de las clases y estructuras.  
  
## <a name="similarities"></a>Similitudes  
 Estructuras y clases son similares en los siguientes aspectos:  
  
-   Ambos son *contenedor* tipos, lo que significa que contienen otros tipos como miembros.  
  
-   Ambas tienen miembros, que pueden incluir constructores, métodos, propiedades, campos, constantes, enumeraciones, eventos y controladores de eventos. Sin embargo, no confunda estos miembros con el declarado *elementos* de una estructura.  
  
-   Los miembros de ambas pueden haber niveles de acceso individualizados. Por ejemplo, un miembro puede declararse `Public` y otra `Private`.  
  
-   Ambas pueden implementar interfaces.  
  
-   Ambas pueden tener constructores compartidos, con o sin parámetros.  
  
-   Ambas pueden exponer una *propiedad predeterminada*, siempre que la propiedad tiene al menos un parámetro.  
  
-   Ambos pueden declarar y provocar eventos y ambas pueden declarar a delegados.  
  
## <a name="differences"></a>Diferencias  
 Estructuras y clases difieren de las indicaciones siguientes:  
  
-   Las estructuras son *los tipos de valor*; son clases *tipos de referencia*. Una variable de un tipo de estructura contiene los datos de la estructura, en lugar que contiene una referencia a los datos como un tipo de clase.  
  
-   Estructuras de utilicen asignación de la pila; las clases utilizan asignación del montón.  
  
-   Todos los elementos de estructura son `Public` de forma predeterminada, la clase variables y constantes son `Private` de forma predeterminada, mientras que otros miembros de clase son `Public` de forma predeterminada. Este comportamiento para los miembros de la clase proporciona compatibilidad con el sistema de Visual Basic 6.0 de valores predeterminados.  
  
-   Una estructura debe tener al menos una no compartido variable o no compartido y no personalizado elemento de evento; una clase puede estar completamente vacía.  
  
-   Elementos de estructura no pueden declararse como `Protected`; pueden miembros de clase.  
  
-   Un procedimiento de estructura puede controlar eventos si es un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedimiento y sólo por medio de la [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md); cualquier procedimiento de clase puede controlar eventos, mediante la [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) palabra clave o el `AddHandler` instrucción. Para obtener más información, consulte [eventos](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
-   Declaraciones de variables de estructura no pueden especificar inicializadores o tamaños iniciales para matrices; las declaraciones de variable de clase pueden.  
  
-   Las estructuras heredan implícitamente de la <xref:System.ValueType?displayProperty=fullName>de clase y no puede heredar de cualquier otro tipo, las clases pueden heredar de cualquier clase o clases que no sean <xref:System.ValueType?displayProperty=fullName>.</xref:System.ValueType?displayProperty=fullName> </xref:System.ValueType?displayProperty=fullName>  
  
-   Las estructuras no son heredables; las clases son.  
  
-   Las estructuras no se terminan nunca, por lo que common language runtime (CLR) nunca llama el <xref:System.Object.Finalize%2A>método en una estructura; las clases se terminan por el recolector de elementos no utilizados (GC), que llama a <xref:System.Object.Finalize%2A>en una clase cuando no detecta que quedan referencias activas.</xref:System.Object.Finalize%2A> </xref:System.Object.Finalize%2A>  
  
-   Una estructura no requiere un constructor; realiza una clase.  
  
-   Las estructuras pueden tener constructores no compartidos únicamente si toman parámetros; las clases pueden tenerlos con o sin parámetros.  
  
 Cada estructura tiene un constructor público implícito sin parámetros. Este constructor inicializa los elementos de datos de la de la estructura con sus valores predeterminados. No se puede volver a definir este comportamiento.  
  
## <a name="instances-and-variables"></a>Instancias y Variables  
 Dado que las estructuras son tipos de valor, cada variable de estructura permanentemente está enlazado a una instancia de estructura individual. Pero las clases son tipos de referencia y una variable de objeto puede hacer referencia a varias instancias de clase en distintos momentos. Esta distinción afecta al uso de estructuras y clases de las maneras siguientes:  
  
-   **Inicialización.** Una variable de estructura incluye implícitamente una inicialización de los elementos mediante el constructor sin parámetros de la estructura. Por lo tanto, `Dim s As struct1` es equivalente a `Dim s As struct1 = New struct1()`.  
  
-   **Asignación de Variables.** Al asignar una variable de estructura a otra o pasar una instancia de estructura a un argumento de procedimiento, se copian los valores actuales de todos los elementos de variable en la nueva estructura. Al asignar una variable de objeto a otra o pasar una variable de objeto a un procedimiento, se copia el puntero de referencia.  
  
-   **Asignar nada.** Puede asignar el valor [nada](../../../../visual-basic/language-reference/nothing.md) a una estructura variable, pero la instancia sigue siendo asociado a la variable. Puede llamar a sus métodos y tener acceso a sus elementos de datos, aunque se reinicializan elementos variables mediante la asignación.  
  
     En cambio, si establece una variable de objeto en `Nothing`, elimina su asociación con cualquier instancia de clase y no se puede obtener acceso a todos los miembros a través de la variable hasta que asigne otra instancia.  
  
-   **Varias instancias.** Una variable de objeto puede tener distintas instancias de clase asignados en momentos distintos y varias variables de objeto pueden hacer referencia a la misma instancia de clase al mismo tiempo. Cambios realizados en los valores de miembros de clase afectan a dichos miembros cuando se tiene acceso a través de otra variable que apunta a la misma instancia.  
  
     Elementos de estructura, sin embargo, están aislados dentro de su propia instancia. Cambios en sus valores no se reflejan en ninguna otra variable de estructura, incluso en otras instancias del mismo `Structure` declaración.  
  
-   **Igualdad.** Comprobar la igualdad de dos estructuras debe realizarse con una elemento por elemento prueba. Se pueden comparar dos variables de objeto mediante la <xref:System.Object.Equals%2A>método.</xref:System.Object.Equals%2A> <xref:System.Object.Equals%2A>indica si las dos variables apuntan a la misma instancia.</xref:System.Object.Equals%2A>  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
