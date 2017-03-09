---
title: "Shared (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shared"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elementos, compartidos"
  - "miembros, compartidos"
  - "no compartidos"
  - "elementos compartidos"
  - "Shared (palabra clave)"
  - "miembros compartidos"
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shared (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que uno o varios elementos de programación declarados están asociados a una clase o estructura en general y no a una instancia específica de la clase o estructura.  
  
## Comentarios  
  
## Cuándo se utiliza Shared  
 Al compartir un miembro de una clase o estructura, éste está disponible para cada instancia; en cambio, si es *no compartido*, cada instancia mantiene su propia copia.  Por ejemplo, esto es útil si el valor de una variable se aplica a toda la aplicación.  Si declara esta variable `Shared`, todas las instancias tendrán acceso a la misma ubicación de almacenamiento y si una instancia cambia el valor de la variable, todas las instancias tendrán acceso al valor actualizado.  
  
 El uso compartido no modifica el nivel de acceso de un miembro.  Por ejemplo, un miembro de clase puede ser compartido y privado \(accesible sólo desde dentro la clase\), o no compartido y público.  Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Reglas  
  
-   **Contexto de la declaración.** Sólo puede utilizar `Shared` en el nivel de módulo.  Esto significa que el contexto de declaración de un elemento `Shared` debe ser una clase o estructura, y no un archivo de código fuente, un espacio de nombres o un procedimiento.  
  
-   **Modificadores combinados.** No se puede especificar `Shared` junto con [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md) o [Static](../../../visual-basic/language-reference/modifiers/static.md) en la misma declaración.  
  
-   **Acceso.** Se tiene acceso a un elemento compartido calificándolo con su nombre de clase o de estructura, y no con el nombre de variable de una instancia específica de su clase o estructura.  Ni siquiera tiene que crear una instancia de una clase o estructura para tener acceso a sus miembros compartidos.  
  
     El ejemplo siguiente llama al procedimiento compartido <xref:System.Double.IsNaN%2A> expuesto por la estructura <xref:System.Double>.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Uso compartido implícito.** No se puede utilizar el modificador `Shared` en [Const \(Instrucción\)](../../../visual-basic/language-reference/statements/const-statement.md), pero las constantes se comparten de forma implícita.  De igual manera, no se puede declarar un miembro de un módulo o una interfaz `Shared` pero se comparte implícitamente.  
  
## Comportamiento  
  
-   **Almacenamiento.** Una variable o evento compartido se almacena en la memoria sólo una vez, independientemente del número de instancias que se hayan creado de su clase o estructura.  De igual manera, una propiedad o procedimiento compartido contiene sólo un conjunto de variables locales.  
  
-   **Acceso mediante una variable de instancia.** Es posible tener acceso a un elemento compartido calificándolo con el nombre de una variable que contiene una instancia específica de su clase o estructura.  Aunque esto suele funcionar del modo previsto, el compilador genera un mensaje de advertencia y obtiene acceso mediante el nombre de clase o estructura en lugar de la variable.  
  
-   **Acceso mediante una expresión de instancia.** Si tiene acceso a un elemento compartido mediante una expresión que devuelve una instancia de su clase o estructura, el compilador obtiene acceso mediante el nombre de clase o estructura en lugar de evaluar la expresión.  Esto genera unos resultados inesperados si había previsto que la expresión realizara otras acciones además de devolver la instancia.  Esto se ilustra en el siguiente ejemplo:  
  
    ```  
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     En el ejemplo anterior, el compilador genera un mensaje de advertencia las dos veces que el código tiene acceso a la variable compartida `total` mediante una instancia.  En cada caso, obtiene acceso directamente mediante la clase `shareTotal` y no utiliza ninguna instancia.  En el caso de una llamada prevista al procedimiento `returnClass`, significa que ni tan siquiera genera una llamada a `returnClass`, por lo que no se realiza la acción adicional de mostrar "Function returnClass\(\) called".  
  
 El modificador `Shared` se puede utilizar en estos contextos:  
  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Período de duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)