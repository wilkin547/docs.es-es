---
title: "Instrucci&#243;n Const (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Const"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Const (instrucción) [Visual Basic]"
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Instrucci&#243;n Const (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara y define una o más constantes.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## Elementos  
 `attributelist`  
 Opcional.  Lista de atributos que se aplican a todas las constantes declaradas en esta instrucción.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares \("`<`" y "`>`"\).  
  
 `accessmodifier`  
 Opcional.  Utilícelo para especificar qué código puede tener acceso a estas constantes.  Puede ser [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend` o [Private](../../../visual-basic/language-reference/modifiers/private.md).  
  
 `Shadows`  
 Opcional.  Utilícelo para volver a declarar y ocultar un elemento de programación de una clase base.  Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Obligatorio.  Lista de constantes de miembros que se declaran en esta instrucción.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Cada `constant` tiene la sintaxis y las partes siguientes:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Parte|Descripción|  
|-----------|-----------------|  
|`constantname`|Obligatorio.  Nombre de la constante.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Obligatorio si `Option Strict` es `On`.  Tipo de datos de la constante.|  
|`initializer`|Obligatorio.  Expresión que se evalúa en tiempo de compilación y se asigna a la constante.|  
  
## Comentarios  
 Si en su aplicación tiene un valor que nunca cambia, puede definir una constante con nombre y usarla en lugar de un valor literal.  Un nombre es más fácil de recordar que un valor.  Puede definir la constante sólo una vez y utilizarla en muchos lugares de su código.  Si en una versión posterior necesita volver a definir el valor, la instrucción `Const` es el único lugar donde es necesario realizar el cambio.  
  
 Sólo puede utilizar `Const` en el nivel de módulo o de procedimiento.  Esto significa que el *contexto de declaración* de una variable tiene que ser una clase, estructura, módulo, procedimiento o bloque, y no puede ser un archivo de código fuente, espacio de nombres o interfaz.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Las constantes locales \(contenidas en un procedimiento\) tienen un valor predeterminado de acceso público y no puede utilizar ningún modificador de acceso en ellas.  Las constantes de clases y miembros de módulo \(externas a cualquier procedimiento\) tienen como valor predeterminado el acceso privado, y las constantes de miembro de estructura tienen como valor predeterminado el acceso público.  Puede ajustar sus niveles de acceso con los modificadores de acceso.  
  
## Reglas  
  
-   **Contexto de la declaración.** Una constante declarada en el nivel de módulo, fuera de cualquier procedimiento, es una *constante de miembros*; es un miembro de la clase, estructura o módulo que la declara.  
  
     Una constante declarada en el nivel de procedimiento es una *constante local*; es local al procedimiento o bloque que la declara.  
  
-   **Atributos.** Sólo puede aplicar los atributos a las constantes de miembro, no a las constantes locales.  Un atributo aporta información a los metadatos del ensamblado, que no son significativos para el almacenamiento temporal como constantes locales.  
  
-   **Modificadores.** De manera predeterminada, todas las constantes son `Shared`, `Static` y `ReadOnly`.  No puede utilizar ninguna de estas palabras clave al declarar una constante.  
  
     En el nivel de procedimiento, no puede utilizar `Shadows` ni ningún modificador de acceso para declarar constantes locales.  
  
-   **Varias constantes.** Puede declarar varias constantes en la misma instrucción de declaración, especificando la parte `constantname` para cada una.  Las constantes múltiples se separan por comas.  
  
## Reglas de tipos de datos  
  
-   **Tipos de datos.** La instrucción `Const` puede declarar el tipo de datos de una variable.  Puede especificar cualquier tipo de datos o el nombre de una enumeración.  
  
-   **Tipo predeterminado.** Si no especifica `datatype`, la constante toma el tipo de datos de `initializer`.  Si se especifica `datatype` e `initializer`, el tipo de datos de `initializer` debe ser convertible a `datatype`.  Si ni `datatype` ni `initializer` están presentes, el tipo de datos utiliza `Object` de manera predeterminada.  
  
-   **Tipos diferentes.** Puede especificar distintos tipos de datos para las diferentes constantes utilizando una cláusula `As` independiente para cada variable que declare.  Sin embargo, no puede declarar varias constantes para que sean del mismo tipo utilizando una cláusula `As` común.  
  
-   **Inicialización.** Debe inicializar el valor de cada constante en `constantlist`.  Utilice `initializer` para proporcionar una expresión que se va a asignar a la constante.  La expresión puede ser cualquier combinación de literales, otras constantes que ya estén definidas y miembros de enumeración que ya se hayan definido.  Puede utilizar operadores aritméticos y lógicos para combinar estos elementos.  
  
     No puede utilizar variables ni funciones en `initializer`.  No obstante, pueden utilizarse palabras clave de conversión como `CByte` y `CShort`.  También puede utilizar `AscW` si lo llama con un argumento constante `String` o `Char`, puesto que puede evaluarse en tiempo de compilación.  
  
## Comportamiento  
  
-   **Ámbito.** A las constantes locales sólo se puede tener acceso desde dentro de sus procedimientos o bloques.  Se puede tener acceso a las constantes de miembro desde cualquier lugar del interior de sus clases, estructuras o módulos.  
  
-   **Calificación.** El código fuera de una clase, estructura o módulo debe calificar el nombre de una constante de miembro con el nombre de esa clase, estructura o módulo.  El código situado fuera de un procedimiento o bloque no puede hacer referencia a ninguna constante local incluida dentro de ese procedimiento o bloque.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la instrucción `Const` para declarar constantes que se utilicen en lugar de valores literales.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/const-statement_1.vb)]  
  
## Ejemplo  
 Si define una constante con el tipo de datos `Object`, el compilador de Visual Basic le asigna el tipo de `initializer`, en lugar de `Object`.  En el ejemplo siguiente, la `naturalLogBase` constante tiene el tipo `Decimal` en tiempo de ejecución.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/const-statement_2.vb)]  
  
 El ejemplo anterior utiliza el método <xref:System.Type.ToString%2A> del objeto <xref:System.Type> devuelto por el [GetType \(Operador\)](../../../visual-basic/language-reference/operators/gettype-operator.md), porque <xref:System.Type> no se puede convertir a `String` utilizando `CStr`.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [\#Const \(Directiva\)](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim \(Instrucción\)](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Constantes y enumeraciones](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Constantes y enumeraciones](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)