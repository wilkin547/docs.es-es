---
title: "Estructuras y clases (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases [Visual Basic]"
  - "clases [Visual Basic], estructuras"
  - "variables de estructura"
  - "estructuras"
  - "estructuras, comparadas con clases"
  - "estructuras, variables de estructura"
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Estructuras y clases (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] unifica la sintaxis para clases y estructuras, y el resultado es que ambas entidades admiten prácticamente las mismas características.  No obstante, existen también importantes diferencias entre clases y estructuras.  
  
 Las clases tienen la ventaja de ser tipos de referencia: pasar una referencia es más eficiente que pasar una variable de estructura con todos sus datos.  Por otra parte, las estructuras no necesitan asignación de memoria en la pila global.  
  
 Puesto que no es posible heredar de una estructura, las estructuras sólo deben utilizarse para objetos que no necesiten extenderse.  Utilice estructuras cuando el objeto que desee crear tenga un tamaño de instancia pequeño; tenga en cuenta las características de rendimiento de las clases frente a las estructuras.  
  
## Similitudes  
 Las estructuras y las clases son similares en los siguientes aspectos:  
  
-   Ambas son tipos *container*, lo que significa que contienen otros tipos como miembros.  
  
-   Ambas tienen miembros, que pueden incluir constructores, métodos, propiedades, campos, constantes, enumeraciones, eventos y controladores de eventos.  Sin embargo, no confunda estos miembros con los *elementos* declarados de una estructura.  
  
-   Los miembros de ambas pueden tener niveles de acceso individualizados.  Por ejemplo, un miembro puede declararse como `Public` y otro como `Private`.  
  
-   Ambas pueden implementar interfaces.  
  
-   Ambas pueden tener constructores compartidos, con o sin parámetros.  
  
-   Ambas pueden exponer una *propiedad predeterminada*, siempre que esa propiedad acepte al menos un parámetro.  
  
-   Ambas pueden iniciar eventos y ambas pueden declarar delegados.  
  
## Diferencias  
 Las estructuras y las clases difieren en los siguientes aspectos:  
  
-   Las estructuras son *tipos de valor*, las clases son *tipos de referencia*.  Una variable de un tipo de estructura contiene los datos de la estructura, en lugar de contener una referencia a los datos, como sucede con los tipos de clase.  
  
-   Las estructuras utilizan asignación de pila y las clases utilizan asignación del montón.  
  
-   De forma predeterminada, todos los elementos de estructura son `Public`; las variables y constantes de clase son `Private`, mientras que otros miembros de clase son `Public` de forma predeterminada.  Este comportamiento de los miembros de las clases proporcionan compatibilidad con el sistema de valores predeterminados de Visual Basic 6.0.  
  
-   Una estructura debe tener al menos una variable no compartida o un elemento de evento no compartido y no personalizado; una clase puede estar completamente vacía.  
  
-   Los elementos de estructura no se pueden declarar como `Protected`, mientras que los miembros de clase sí se pueden.  
  
-   Un procedimiento de estructura sólo puede controlar eventos si es un procedimiento [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` y sólo mediante [AddHandler \(Instrucción\)](../../../../visual-basic/language-reference/statements/addhandler-statement.md); cualquier procedimiento de clase puede controlar eventos, ya sea utilizando la palabra clave [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) o la instrucción `AddHandler`.  Para obtener más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
-   Las declaraciones de variables de estructura no pueden especificar inicializadores o tamaños iniciales para matrices; mientras que las declaraciones de variables de clase sí pueden.  
  
-   Las estructuras heredan de forma implícita de la clase <xref:System.ValueType?displayProperty=fullName> y no pueden heredar de ningún otro tipo de clase. Las clases pueden heredar de cualquier clase o clases que no sean del tipo <xref:System.ValueType?displayProperty=fullName>.  
  
-   Las estructuras no son heredables; las clases, sí.  
  
-   Las estructuras no se terminan nunca, por lo tanto, Common Language Runtime \(CLR\) nunca llama al método <xref:System.Object.Finalize%2A> en una estructura; las clases las termina el recolector de elementos no utilizados, que llama al método <xref:System.Object.Finalize%2A> en una clase cuando detecta que no quedan referencias activas.  
  
-   Una estructura no requiere un constructor, una clase sí.  
  
-   Las estructuras sólo pueden tener constructores no compartidos si pueden tomar parámetros; sin embargo las clases pueden tener constructores con o sin parámetros.  
  
 Cada estructura tiene un constructor público implícito sin parámetros.  El constructor inicializa todos los elementos de datos de estructura con sus valores predeterminados.  Este comportamiento no puede redefinirse.  
  
## Instancias y variables  
 Puesto que las estructuras son tipos de valor, cada variable de estructura está enlazada de forma permanente a una instancia de estructura individual.  Por otro lado, las clases son tipos de referencia y una variable de objeto puede hacer referencia a varias instancias de clase en distintos momentos.  Esta distinción afecta al uso de estructuras y clases de las siguientes formas:  
  
-   **Inicialización.** Una variable de estructura incluye implícitamente una inicialización de los elementos mediante el constructor sin parámetros de la estructura.  Por tanto, `Dim s As struct1` equivale a `Dim s As struct1 = New struct1()`.  
  
-   **Asignar variables.** Al asignar una variable de estructura a otra o pasar una instancia de estructura a un argumento de procedimiento, se copian los valores actuales de todos los elementos de variable en la nueva estructura.  Al asignar una variable de objeto a otra o pasar una variable de objeto a un procedimiento, sólo se copia el puntero de referencia.  
  
-   **No asignar nada.** Puede asignar el valor [Nothing](../../../../visual-basic/language-reference/nothing.md) a una variable de estructura, aunque la instancia sigue asociada con la variable.  Puede seguir llamando a los métodos y obteniendo acceso a sus elementos de datos, aunque la asignación inicializa de nuevo los elementos de variable.  
  
     En contraposición, si establece una variable de objeto en `Nothing`, elimina su asociación con cualquier instancia de clase y no puede tener acceso a ningún miembro a través de la variable hasta que le asigne otra instancia.  
  
-   **Varias instancias.** Una variable de objeto puede tener asignadas distintas instancias de clase en momentos distintos y varias variables de objeto pueden hacer referencia a la misma instancia de clase al mismo tiempo.  Los cambios que realice a los valores de los miembros de clase afectan a dichos miembros cuando se tiene acceso a estos mediante otra variable que apunta a la misma instancia.  
  
     Los elementos de estructura, sin embargo, están aislados dentro de su propia instancia.  Los cambios a sus valores no se ven reflejados en ninguna otra variable de estructura, incluso en otras instancias de la misma declaración `Structure`.  
  
-   **Igualdad.** La comprobación de igualdad de dos estructuras debe realizarse mediante una prueba elemento a elemento.  Dos variables de objeto se pueden comparar mediante el método <xref:System.Object.Equals%2A>.  <xref:System.Object.Equals%2A> indica si las dos variables apuntan a la misma instancia.  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)