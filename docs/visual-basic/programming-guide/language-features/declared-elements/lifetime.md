---
title: "Per&#237;odo de duraci&#243;n en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elementos declarados, duración"
  - "duración"
  - "duración, elementos declarados"
  - "duración, Visual Basic"
  - "duración de la variable Shared"
  - "variables estáticas, duración"
  - "variables estáticas, Visual Basic"
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Per&#237;odo de duraci&#243;n en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El *período de duración* de un elemento declarado es el tiempo durante el cual está disponible para el uso.  Las variables son los únicos elementos que tienen un período de duración.  Para este propósito, el compilador trata los parámetros de procedimiento y la función vuelve como un caso especial de variable.  El período de duración de una variable representa el tiempo durante el cual puede contener un valor.  Su valor puede variar en su período de duración, pero siempre contiene un valor.  
  
## Períodos de duración diferentes  
 Una *variable miembro* \(declarada en el nivel de módulo, fuera de cualquier procedimiento\) tiene el mismo período de duración normalmente que el elemento en el que se declara.  Una variable no compartida declarada en una clase o estructura existe como copia separada para cada instancia de la clase o estructura en la que se declara.  Este tipo de variable tiene el mismo período de duración que su instancia.  No obstante, una variable `Shared` sólo tiene un período de duración, que es el tiempo completo de ejecución de la aplicación.  
  
 Una *variable local* \(declarada dentro de un procedimiento\) sólo existe mientras el procedimiento en el que se declara está en ejecución.  Esto también es aplicable a los parámetros del procedimiento y a cualquier valor devuelto de función.  No obstante, si el procedimiento llama a otros procedimientos, las variables locales conservan su valor durante la ejecución de los últimos.  
  
## Comienzo del período de duración  
 El período de duración de una variable local empieza con el control del procedimiento en el que se declara.  Las variables locales se inicializan con el valor predeterminado de su tipo de datos en el momento en que empieza la ejecución del procedimiento.  Cuando el procedimiento encuentra una instrucción `Dim` que especifica valores iniciales, establece esos valores para las variables aunque el código ya les haya asignado otros valores.  
  
 Los miembros de una variable de estructura se inicializan como si cada uno fuera una variable independiente.  De forma similar, los elementos de una variable de matriz se inicializan de manera individual.  
  
 Las variables declaradas dentro de un bloque en el interior de un procedimiento \(como un bucle `For` \) se inicializan en la entrada al procedimiento.  Estas inicializaciones tienen efecto independientemente de si el código ejecuta o no el bloque.  
  
## Final del período de duración  
 Cuando un procedimiento finaliza, no se conservan los valores de sus variables locales y [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] recupera su memoria.  La próxima vez que llame al procedimiento, se crean de nuevo y se reinicializan todas las variables locales.  
  
 Cuando finaliza una instancia de una clase o estructura, se pierde el valor y la memoria de sus variables no compartidas.  Cada nueva instancia de la clase o estructura crea y reinicializa sus variables no compartidas.  No obstante, las variables `Shared` se conservan hasta que finaliza la ejecución de la aplicación.  
  
## Prolongar el período de duración  
 Si declara una variable local con la palabra clave `Static`, su período de duración es más largo que el tiempo de ejecución de su procedimiento.  La tabla siguiente muestra cómo determina la declaración de procedimiento el tiempo de duración de una variable `Static`.  
  
|Ubicación de procedimiento y uso compartido|Comienza el período de duración de una variable estática|Finaliza el período de duración de una variable estática|  
|-------------------------------------------------|--------------------------------------------------------------|--------------------------------------------------------------|  
|En un módulo \(compartido de manera predeterminada\)|La primera vez que se llama al procedimiento|Cuando se detiene la aplicación|  
|En una clase, `Shared` \(el procedimiento no es un miembro de instancia\)|La primera vez que se llama al procedimiento en una instancia específica, o en el mismo nombre de clase o estructura|Cuando se detiene la aplicación|  
|En una instancia de una clase, no `Shared` \(el procedimiento es un miembro de instancia\)|La primera vez que se llama al procedimiento en la instancia específica|Cuando la instancia se libera para la recolección de elementos no utilizados|  
  
## Variables estáticas del mismo nombre  
 Puede declarar variables estáticas con el mismo nombre en más de un procedimiento.  Si hace esto, el compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] considera que cada variable es un elemento separado.  La inicialización de una de estas variables no afecta al valor de las demás.  Lo mismo ocurre si se define un procedimiento con un conjunto de sobrecargas y se declara una variable estática con el mismo nombre en cada una.  
  
## Elementos contenedores para variables estáticas  
 Puede declarar una variable local estática en una clase, es decir, dentro de un procedimiento de esa clase.  Sin embargo, no puede declarar una variable local estática dentro de una estructura, ya sea como miembro de una estructura o como una variable local de un procedimiento dentro de esa estructura.  
  
## Ejemplo  
  
### Descripción  
 El ejemplo siguiente declara una variable con la palabra clave [Static](../../../../visual-basic/language-reference/modifiers/static.md).  \(Observe que no necesita la palabra clave `Dim` cuando [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) utiliza un modificador como `Static`.\)  
  
### Código  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### Comentarios  
 En el ejemplo anterior, la variable `applesSold` continúa existiendo después de que el procedimiento `runningTotal` vuelve al código de llamada.  La siguiente vez que se llama a `runningTotal`, `applesSold` conserva el valor calculado anteriormente.  
  
 Si `applesSold` se hubiera declarado sin utilizar `Static`, los valores acumulados anteriores no se conservarían a través de llamadas a `runningTotal`.  La siguiente vez que se llamara a `runningTotal`, `applesSold` se habría vuelto a crear y se habría inicializado a 0. `runningTotal` habría devuelto simplemente el mismo valor que el que tenía cuando fue llamado.  
  
### Compilar el código  
 Puede inicializar el valor de una variable local estática en la propia declaración.  Si declara una matriz como `Static`, puede inicializar su rango \(número de dimensiones\), la longitud de cada dimensión y los valores de los elementos individuales.  
  
### Seguridad  
 En el ejemplo anterior, puede generar la misma duración si declara `applesSold` en el nivel de módulo.  No obstante, si ha cambiado de esta forma el ámbito de una variable, el procedimiento dejará de tener acceso exclusivo a él.  Dado que otros procedimientos podrían tener acceso a `applesSold` y cambiar su valor, el total acumulado no sería fiable, lo que podría dificultar el mantenimiento del código.  
  
## Vea también  
 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)