---
title: "Declaraci&#243;n de variables de objeto (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "enlace, tardío y temprano"
  - "clases [Visual Basic], declarar"
  - "declaraciones, clase"
  - "declarar clases"
  - "declarar variables, variables de objeto"
  - "enlace temprano"
  - "enlace tardío"
  - "variables de objeto, declarar"
  - "variables [Visual Basic], objeto"
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
caps.latest.revision: 33
caps.handback.revision: 33
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Declaraci&#243;n de variables de objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Utiliza una instrucción de declaración normal para declarar una variable de objeto.  Para el tipo de datos, especifica `Object` \(es decir, [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)\) o una clase más específica a partir de la cual se crea el objeto.  
  
 Declarar una variable como `Object` es lo mismo que declararla como <xref:System.Object?displayProperty=fullName>.  
  
 Cuando se declara una variable con una clase de objeto específica, ésta obtiene acceso a todos los métodos y propiedades de dicha clase y las clases de las que hereda.  Si declara la variable con <xref:System.Object>, puede tener acceso sólo a los miembros de la clase <xref:System.Object>, a menos que cambie `Option Strict Off` para permitir el enlace en tiempo de ejecución.  
  
## Sintaxis de la declaración  
 Use la sintaxis siguiente para declarar una variable de objeto:  
  
```  
Dim variablename As [New] { objectclass | Object }  
```  
  
 También puede especificar [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) o [Static](../../../../visual-basic/language-reference/modifiers/static.md) en la declaración.  Son válidas las siguientes declaraciones de ejemplo:  
  
```  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## Enlace en tiempo de ejecución y enlace en tiempo de compilación  
 A veces la clase específica es desconocida hasta que se ejecuta el código.  En este caso, debe declarar la variable de objeto con el tipo de datos `Object`,  Esto crea una referencia general a cualquier tipo de objeto y se asigna la clase específica en tiempo de ejecución.  Esto se llama *enlace en tiempo de ejecución*.  El enlace en tiempo de ejecución requiere tiempo de ejecución adicional.  También limita su código a los métodos y propiedades de la clase que le ha asignado recientemente.  Esto puede producir errores en tiempo de ejecución si su código intenta tener acceso a miembros de una clase diferente.  
  
 Si conoce la clase específica en tiempo de compilación, declare la variable de objeto como miembro de dicha clase.  Esto se llama *enlace en tiempo de compilación*.  El enlace en tiempo de compilación mejora el rendimiento y garantiza el acceso de su código a todos los métodos y propiedades de la clase específica.  En las declaraciones del ejemplo anterior, si la variable `objA` utiliza sólo objetos de clase <xref:System.Windows.Forms.Label?displayProperty=fullName>, debe especificar `As System.Windows.Forms.Label` en su declaración.  
  
### Ventajas del enlace en tiempo de compilación  
 La declaración de una variable de objeto como una clase específica ofrece varias ventajas:  
  
-   Comprobación automática de tipos  
  
-   Acceso garantizado a todos los miembros de la clase específica  
  
-   Compatibilidad con Microsoft IntelliSense en el Editor de código  
  
-   Legibilidad mejorada de su código  
  
-   Disminución del número de errores en el código  
  
-   Errores detectados en tiempo de compilación en vez de en tiempo de ejecución  
  
-   Aumento de la velocidad de ejecución del código  
  
## Acceso a los miembros de variables de objeto  
 Si `Option Strict` está en `On`, una variable de objeto sólo puede tener acceso a los métodos y propiedades de la clase con la que se ha declarado.  Esto se ilustra en el siguiente ejemplo:  
  
```  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 En este ejemplo, `p` puede utilizar sólo los miembros de la propia clase <xref:System.Object>, que no incluyen la propiedad `Left`.  Por otro lado, `q` se ha declarado con el tipo <xref:System.Windows.Forms.Label>, así que puede utilizar todos los métodos y propiedades de la clase <xref:System.Windows.Forms.Label> en el espacio de nombres <xref:System.Windows.Forms>.  
  
## Flexibilidad de las variables de objeto  
 Cuando se trabaja con objetos en una jerarquía de herencia, existe la posibilidad de elegir la clase que se va a utilizar para declarar las variables de objeto.  A la hora de tomar esta decisión, debe buscarse un equilibrio entre la flexibilidad de la asignación de objetos y el acceso a los miembros de una clase.  Por ejemplo, si consideramos la jerarquía de herencia que conduce a la clase <xref:System.Windows.Forms.Form?displayProperty=fullName>:  
  
 <xref:System.Object>  
  
 `` <xref:System.ComponentModel.Component>  
  
 `` <xref:System.Windows.Forms.Control>  
  
 `` <xref:System.Windows.Forms.ScrollableControl>  
  
 `` <xref:System.Windows.Forms.ContainerControl>  
  
 `` <xref:System.Windows.Forms.Form>  
  
 Supongamos que una aplicación define un clase de formulario denominado `specialForm`, que hereda de la clase <xref:System.Windows.Forms.Form>.  Puede declarar una variable de objeto que haga referencia específicamente a `specialForm`, como se muestra en el ejemplo siguiente:  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 La declaración del ejemplo anterior limita la variable `nextForm` a objetos de la clase `specialForm`, pero también pone todos los métodos y propiedades de `specialForm` a disposición de `nextForm`, así como todos los miembros de todas las clases de las que hereda `specialForm`.  
  
 Puede hacer que una variable de objeto sea más general si la declara de tipo <xref:System.Windows.Forms.Form>, como se muestra en el ejemplo siguiente.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
 La declaración del ejemplo anterior le permite asignar cualquier formulario de su aplicación a `anyForm`.  Sin embargo, aunque `anyForm` pueda tener acceso a todos los miembros de la clase <xref:System.Windows.Forms.Form>, no puede utilizar ninguno de los métodos o propiedades adicionales definidos para formularios específicos como `specialForm`.  
  
 Todos los miembros de una clase base están disponibles para las clases derivadas, pero los miembros adicionales de una clase derivada no están disponibles para la clase base.  
  
## Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [Cómo: Obtener acceso a los miembros de un objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [New \(Operador\)](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)