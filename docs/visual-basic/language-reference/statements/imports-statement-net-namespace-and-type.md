---
title: "Instrucci&#243;n Imports (Tipo y espacio de nombres de .NET) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Imports"
  - "imports"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "alias [Visual Basic], importación"
  - "alias [Visual Basic], Imports (instrucción)"
  - "elementos contenedores [Visual Basic]"
  - "nombres de elementos declarados [Visual Basic], calificación"
  - "elementos declarados [Visual Basic], elementos contenedores"
  - "importar alias [Visual Basic]"
  - "importaciones [Visual Basic]"
  - "Imports (instrucción) [Visual Basic]"
  - "Imports (instrucción) [Visual Basic], sintaxis"
  - "espacios de nombres [Visual Basic], importar"
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: 40
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 40
---
# Instrucci&#243;n Imports (Tipo y espacio de nombres de .NET)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Permite hacer referencia a nombres de tipo sin calificación de espacio de nombres.  
  
## Sintaxis  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`aliasname`|Opcional.  Un *alias de importación* o nombre por el que el código puede hacer referencia a `namespace` en lugar de a la cadena calificada completa.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Obligatorio.  Nombre completo del espacio de nombres que se importa.  Puede ser una cadena de espacios de nombres anidada a cualquier nivel.|  
|`element`|Opcional.  El nombre de un elemento de programación declarado en el espacio de nombres.  Puede ser cualquier elemento contenedor.|  
  
## Comentarios  
 La instrucción `Imports`  permite hacer referencia directamente a los tipos incluidos en un espacio de nombres especificado.  
  
 Puede proporcionar un único nombre de espacio de nombres o una cadena de espacios de nombres anidados.  Cada espacio de nombres anidado se separa del espacio de nombres de nivel más alto siguiente con un punto \(`.`\), como se muestra en el ejemplo siguiente.  
  
 `Imports System.Collections.Generic`  
  
 Cada archivo de código fuente puede contener cualquier número de instrucciones `Imports`.  Éstas deben seguir las declaraciones de opción existentes, como la instrucción `Option Strict`, y deben preceder a cualquier declaración de elemento de programación como `Module` o `Class`.  
  
 Sólo puede utilizar `Imports` en el nivel de archivo.  Esto significa que el contexto de declaración para la importación debe ser un archivo de código fuente y no puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque.  
  
 Observe que la instrucción `Imports` no pone a disposición de su proyecto elementos de otros proyectos y ensamblados.  La importación no sustituye el establecimiento de una referencia.  Sólo quita la necesidad de calificar nombres que ya están disponibles para su proyecto.  Para obtener más información, vea "Importar elementos contenedores" en [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Puede definir instrucciones implícitas `Imports` mediante [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  Para obtener más información, vea [Cómo: Agregar o quitar espacios de nombres importados \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
## Alias de importación  
 Un *alias de importación* define el alias de un espacio de nombres o tipo.  Los alias de importación son útiles cuando es necesario utilizar elementos con el mismo nombre declarado en uno o más espacios de nombres.  Para obtener más información y un ejemplo, vea "Calificar un nombre de elemento" en [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 No se deben declarar miembros en el nivel de módulo que tengan el mismo nombre que `aliasname`.  Si lo hace, el compilador de Visual Basic sólo utiliza `aliasname` para el miembro declarado y deja de reconocerlo como un alias de importación.  
  
 Aunque la sintaxis empleada para declarar un alias de importación es como la que se usa para importar un prefijo del espacio de nombres XML, los resultados son diferentes.  Un alias de importación se puede usar como una expresión en el código, mientras que un prefijo de espacio de nombres XML únicamente se puede usar en literales de XML o en propiedades de eje de XML, como el prefijo para un elemento calificado o nombre de atributo.  
  
### Nombres de elemento  
 Si proporciona `element`, debe representar un *elemento contenedor*, es decir, un elemento de programación que puede contener otros elementos.  Los elementos contenedores incluyen clases, estructuras, módulos, interfaces y enumeraciones.  
  
 El ámbito de los elementos que se vuelven disponibles mediante una instrucción `Imports` depende de si especifica `element`.  Si especifica sólo `namespace`, todos los miembros con nombre único de ese espacio de nombres y miembros de elementos contenedores dentro de dicho espacio de nombres, están disponibles sin calificación.  Si especifica `namespace` y `element`, sólo los miembros de ese elemento están disponibles sin calificación.  
  
## Ejemplo  
 El ejemplo siguiente devuelve todas las carpetas del directorio C:\\ utilizando la clase <xref:System.IO.DirectoryInfo>.  
  
 El código no tiene ninguna instrucción `Imports` en la parte superior del archivo.  Por lo tanto, las referencias `DirectoryInfo`, <xref:System.Text.StringBuilder> y <xref:Microsoft.VisualBasic.ControlChars.CrLf> son completas con los espacios de nombres.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_1.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se incluyen instrucciones `Imports` de los espacios de nombres a los que se hace referencia.  Por lo tanto, los tipos no debe ser completo con los espacios de nombres.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_3.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se incluyen instrucciones `Imports` que crean alias para los espacios de nombres a los que se hace referencia.  Los tipos están calificados con los alias.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_5.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se incluyen instrucciones `Imports` que crean alias para los tipos a los que se hace referencia.  Se utilizan alias para especificar los tipos.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_7.vb)]  
  
## Vea también  
 [Namespace \(Instrucción\)](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports \(Instrucción, Espacio de nombres XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)