---
title: "Namespace (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Namespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaraciones, espacios de nombres"
  - "declarar espacios de nombres, sintaxis"
  - "Namespace (instrucción)"
  - "espacios de nombres, declarar"
  - "espacios de nombres, anidados"
  - "espacios de nombres, raíz"
  - "espacios de nombres de la raíz"
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
caps.latest.revision: 39
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 39
---
# Namespace (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara el nombre de un espacio de nombres y determina que el código fuente que sigue a la declaración se compile dentro de ese espacio de nombres.  
  
## Sintaxis  
  
```  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## Elementos  
 Global  
 Opcional.  Permite definir un espacio de nombres fuera del proyecto.  Vea [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Obligatorio.  Un nombre único que identifica el espacio de nombres.  Debe ser un identificador de Visual Basic válido.  Para obtener más información, vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Opcional.  Elementos que forman el espacio de nombres.  Incluyen, entre otros, enumeraciones, estructuras, interfaces, clases, módulos, delegados, y otros espacios de nombres.  
  
 `End Namespace`  
 Termina un bloque `Namespace`.  
  
## Comentarios  
 Los espacios de nombres se utilizan como un sistema de organización.  Proporcionan una manera de clasificar y presentar elementos de programación que se exponen a otros programas y aplicaciones.  Observe que un espacio de nombres no es *un tipo* en el sentido de que una clase o estructura ser\-usted no puede declarar un elemento de programación para obtener el tipo de datos de un espacio de nombres.  
  
 Todos los elementos de programación declarados tras una instrucción `Namespace` pertenecen a ese espacio de nombres.  Visual Basic continúa compilando los elementos en el último espacio de nombres declarado hasta que encuentra una instrucción `End Namespace` u otra instrucción `Namespace`.  
  
 Si ya se ha definido un espacio de nombres, aunque sea fuera del proyecto, puede agregar en él elementos de programación.  Para ello, utilice una instrucción de `Namespace` para que Visual Basic para compilar elementos en el espacio de nombres.  
  
 Sólo puede utilizar una instrucción `Namespace` en el nivel de archivo o de espacio de nombres.  Esto significa que el *contexto de la declaración* de un espacio de nombres debe ser un archivo de código fuente u otro espacio de nombres y no puede ser una clase, estructura, módulo, interfaz o procedimiento.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Puede declarar un espacio de nombres dentro de otro.  No existe un límite estricto en cuanto a los niveles de anidamiento que se pueden declarar, pero debe recordar que si otro código tiene acceso a los elementos declarados en el espacio de nombres más interno, debe usar una cadena de calificación con los nombres de todos los espacios de nombres de la jerarquía de anidamiento.  
  
## Nivel de acceso  
 Se tratan los espacios de nombres como si tienen un nivel de acceso de `Public` .  Se puede tener acceso a un espacio de nombres desde el código del mismo proyecto, desde otros proyectos que hacen referencia al proyecto y desde los ensamblados creados a partir del proyecto.  
  
 Los elementos de programación declarados en el nivel del espacio de nombres, es decir, dentro de un espacio de nombres pero no dentro de cualquier otro elemento, pueden tener acceso de tipo `Public` o `Friend`.  Si no se especifica, el nivel de acceso de dichos elementos usa `Friend` de manera predeterminada.  Los elementos que puede declarar en el nivel de espacio de nombres incluyen clases, estructuras, módulos, interfaces, enumeraciones y delegados.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
## Espacio de nombres de la raz  
 Todos los nombres de espacios de nombres del proyecto se basan en un *espacio de nombres raíz*.  Visual Studio asigna el nombre de proyecto como el espacio de nombres de raíz predeterminado para todo el código del proyecto.  Por ejemplo, si el proyecto se denomina `Payroll`, sus elementos de programación pertenecen al espacio de nombres `Payroll`.  Si declara `Namespace funding`, el nombre completo de ese espacio de nombres es `Payroll.funding`.  
  
 Si desea especificar un espacio de nombres existente en una instrucción `Namespace`, como en el ejemplo de la clase de lista genérica, puede establecer el espacio de nombres de la raíz en un valor nulo.  Para ello, en el menú **Proyecto**, haga clic en **Propiedades del proyecto** y borre la entrada **Espacio de nombres de la raíz** para dejar el cuadro vacío.  Si no ha realizado esto en el ejemplo de la clase de lista genérica, el compilador de Visual Basic considera `System.Collections.Generic` como un nuevo espacio de nombres en el proyecto `Payroll`, con el nombre completo `Payroll.System.Collections.Generic`.  
  
 También puede utilizar la palabra clave `Global` para hacer referencia a los elementos de espacios de nombres definidos fuera del proyecto.  Esto permite conservar el nombre del proyecto como espacio de nombres de la raíz.  Así se reduce la posibilidad de combinar involuntariamente los elementos de programación con aquéllos de los espacios de nombres existentes.  Para obtener más información, vea “palabra clave Global en la sección de nombres completos” en [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 La palabra clave de `Global` también se puede utilizar en una instrucción namespace.  Esto permite definir un espacio de nombres fuera del proyecto.  Para obtener más información, vea “palabra clave Global en la sección de las instrucciones de espacio de nombres” en [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 **el solucionar problemas.** El espacio de nombres de la raíz puede provocar concatenaciones inesperadas de nombres de espacio de nombres.  Si hace referencia a espacios de nombres definidos fuera del proyecto, el compilador de Visual Basic puede generarlos como espacios de nombres anidados dentro del espacio de nombres de la raíz.  En este caso, el compilador no reconoce los tipos ya definidos en los espacios de nombres externos.  Para evitar esto, establece el espacio de nombres en un valor nulo como se describe en “espacio de nombres,” o usar la palabra clave de `Global` para tener acceso a los elementos de espacios de nombres externos.  
  
## Atributos y modificadores  
 No puede aplicar atributos a un espacio de nombres.  Los atributos incorporan información a los metadatos del ensamblado, que no son significativos para los clasificadores de origen como los espacios de nombres.  
  
 No puede aplicar modificadores de acceso ni de procedimiento ni cualquier otro modificador a un espacio de nombres.  Dado que no es un tipo, estos modificadores no son significativos.  
  
## Ejemplo  
 En el ejemplo siguiente se declaran dos espacios de nombres, uno anidado en el otro.  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_1.vb)]  
  
## Ejemplo  
 En el siguiente ejemplo se declaran varios espacios de nombres anidados en una única línea; este ejemplo es equivalente al anterior.  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_2.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se tiene acceso a la clase definida en los ejemplos anteriores.  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_3.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se define el esqueleto de una nueva clase de lista genérica y se agrega al espacio de nombres <xref:System.Collections.Generic?displayProperty=fullName>.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## Vea también  
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)