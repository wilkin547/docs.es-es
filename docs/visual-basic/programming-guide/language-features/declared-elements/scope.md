---
title: "&#193;mbito en Visual Basic | Microsoft Docs"
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
  - "ámbito de bloque"
  - "elementos declarados, ámbito"
  - "niveles de ámbito"
  - "nivel de módulo"
  - "ámbito de módulo"
  - "espacios de nombres, ámbito"
  - "ámbito de procedimiento"
  - "procedimientos, ámbito"
  - "ámbito, acerca del ámbito"
  - "ámbito, elementos declarados"
  - "ámbito, niveles"
  - "ámbito, Visual Basic"
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# &#193;mbito en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El *ámbito* de un elemento declarado es el conjunto de todo el código que puede hacer referencia a él sin calificar su nombre o marcarlo como disponible mediante [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  Un elemento puede tener uno de los niveles de ámbito siguientes:  
  
|Nivel|Descripción|  
|-----------|-----------------|  
|Ámbito de bloque|Ámbito disponible únicamente en el bloque de código en el que se ha declarado|  
|Ámbito de procedimiento|Disponible para todo el código dentro del procedimiento en el que se ha declarado|  
|Ámbito de módulo|Disponible para todo el código dentro del módulo, clase o estructura en el que se ha declarado|  
|Ámbito de espacio de nombres|Disponible para todo el código dentro del espacio de nombres en el que se ha declarado|  
  
 Estos niveles de ámbito progresan desde el más restringido \(bloque\) al más amplio \(espacio de nombres\), donde *ámbito más restringido* significa el conjunto de código más pequeño que puede hacer referencia al elemento sin calificación.  Para obtener más información, vea "Niveles de ámbito" en esta página.  
  
## Especificar ámbito y definir variables  
 El ámbito de un elemento se especifica al declararlo  y puede depender de los factores siguientes:  
  
-   La región \(bloque, procedimiento, módulo, clase o estructura\) donde se declara el elemento.  
  
-   El espacio de nombres que contiene la declaración del elemento.  
  
-   El nivel de acceso que se declara para el elemento.  
  
 Tenga cuidado cuando defina variables del mismo nombre pero con ámbito diferente, puesto que ello podría causar resultados inesperados.  Para obtener más información, vea [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## Niveles de ámbito  
 Un elemento de programación está disponible en toda la región en la que se declara.  Todo el código de la misma región puede hacer referencia al elemento sin calificar su nombre.  
  
### Ámbito de bloque  
 Un bloque es un conjunto de instrucciones incluido dentro de las instrucciones de declaración de inicio y fin, como lo siguiente:  
  
-   `Do` y `Loop`  
  
-   `For` \[`Each`\] y `Next`  
  
-   `If` y `End If`  
  
-   `Select` y `End Select`  
  
-   `SyncLock` y `End SyncLock`  
  
-   `Try` y `End Try`  
  
-   `While` y `End While`  
  
-   `With` y `End With`  
  
 Si declara una variable dentro de un bloque, sólo puede utilizarla dentro de ese bloque.  En el ejemplo siguiente, el ámbito de la variable de entero `cube` es el bloque entre `If` y `End If`, y las referencias a `cube` dejan de ser posibles cuando termina la ejecución del bloque.  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  Incluso si el ámbito de una variable está limitado a un bloque, su período de duración sigue siendo el del procedimiento completo.  Si utiliza el bloque varias veces durante el procedimiento, todas las variables de bloque conservan su valor anterior.  Para evitar resultados inesperados en estos casos, es mejor inicializar las variables de bloque al principio del bloque.  
  
### Ámbito de procedimiento  
 Un elemento declarado en un procedimiento no está disponible fuera de él.  Solamente el procedimiento que contiene su declaración puede utilizarlo.  Las variables en este nivel también se denominan *variables locales*.  Se declaran con [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md), con o sin la palabra clave [Static](../../../../visual-basic/language-reference/modifiers/static.md).  
  
 Los ámbitos de procedimiento y de bloque están estrechamente relacionados.  Si se declara una variable dentro de un procedimiento, pero fuera de un bloque dentro del procedimiento, puede considerarse que la variable tiene ámbito de bloque, donde el bloque es el procedimiento completo.  
  
> [!NOTE]
>  Todos los elementos locales, aunque sean variables `Static`, son privados para el procedimiento en el que aparecen.  No se puede declarar un elemento mediante la palabra clave [Public](../../../../visual-basic/language-reference/modifiers/public.md) dentro de un procedimiento.  
  
### Ámbito de módulo  
 Por comodidad, el término *nivel de módulo* se aplica por igual a módulos, clases y estructuras.  Puede declarar elementos a este nivel si sitúa la instrucción de declaración fuera de cualquier procedimiento o bloque pero dentro del módulo, clase o estructura.  
  
 Cuando se incluye una declaración en el nivel de módulo, el nivel de acceso elegido determina el ámbito.  El espacio de nombres que contiene el módulo, la clase o la estructura también afecta al ámbito.  
  
 Los elementos para los que declara un nivel de acceso [Private](../../../../visual-basic/language-reference/modifiers/private.md) están disponibles en cada procedimiento de ese módulo, pero no en el código de otro módulo.  La instrucción `Dim` en el nivel de módulo toma `Private` como valor predeterminado si no utiliza ninguna palabra nivel de acceso.  No obstante, el ámbito y el nivel de acceso serán más patentes si utiliza la palabra clave `Private` en la instrucción `Dim`.  
  
 En el ejemplo siguiente, todos los procedimientos definidos en el módulo pueden hacer referencia a la variable de cadena `strMsg`.  Cuando se llama al segundo procedimiento, muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo:  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### Ámbito de espacio de nombres  
 Si declara un elemento en el nivel de módulo mediante la palabra clave [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [Public](../../../../visual-basic/language-reference/modifiers/public.md), dicho elemento quedará disponible para todos los procedimientos del espacio de nombres en los que se declare.  La siguiente modificación del ejemplo anterior permite que el código haga referencia a la variable de cadena `strMsg` en cualquier parte del espacio de nombres de su declaración.  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 El ámbito de espacio de nombres incluye espacios de nombres anidados.  Un elemento disponible de un espacio de nombres también está disponible en cualquier espacio de nombres anidado en su interior.  
  
 Si un proyecto no contiene [Namespace \(Instrucción\)](../../../../visual-basic/language-reference/statements/namespace-statement.md), todo lo que incluya el proyecto estará en el mismo espacio de nombres.  En este caso, el ámbito de espacio de nombres se puede considerar como el ámbito del proyecto.  Los elementos `Public` de un módulo, clase o estructura también están disponibles para cualquier proyecto que haga referencia a su proyecto.  
  
## Elección de ámbito  
 Cuando declara una variable, debe tener presente los puntos siguientes al elegir su ámbito.  
  
### Ventajas de variables locales  
 Las variables locales son una buena elección para cualquier tipo de cálculo temporal, por las razones siguientes:  
  
-   **Evitar conflictos de nombres.** Los nombres de variables locales no son susceptibles de entrar en conflicto.  Por ejemplo, es posible crear varios procedimientos distintos que contengan una variable denominada `intTemp`.  En tanto que `intTemp` esté declarado como una variable local, cada procedimiento reconocerá únicamente su propia versión de `intTemp`.  Cualquier procedimiento puede cambiar el valor de su variable `intTemp` local sin que ello afecte a las variables `intTemp` del resto de los procedimientos.  
  
-   **Consumo de memoria.** Las variables locales sólo utilizan la memoria mientras su procedimiento está en ejecución.  Su memoria se libera cuando el procedimiento vuelve al código de llamada.  Por el contrario, las variables [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) y [Static](../../../../visual-basic/language-reference/modifiers/static.md) consumen recursos de memoria hasta que su aplicación deja de ejecutarse, por lo que se deben utilizar sólo cuando sea necesario.  Las *variables de instancia* utilizan la memoria mientras su instancia sigue existiendo, lo que les resta eficacia frente a las variables locales pero son potencialmente más eficaces que las variables `Shared` o `Static`.  
  
### Minimizar el ámbito  
 En general, cuando se declara una variable o una constante, es un buen hábito de programación asignar un ámbito lo más restringido posible \(el ámbito de un bloque es el más restringido\).  Esto permite que no se pierda memoria y reduce al mínimo la posibilidad de que el código haga referencia por error a una variable incorrecta.  Del mismo modo, sólo debería declararse una variable como [Static](../../../../visual-basic/language-reference/modifiers/static.md) si es necesario que conserve su valor entre una llamada al procedimiento y otra.  
  
## Vea también  
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Cómo: Controlar el ámbito de una variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [Período de duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)