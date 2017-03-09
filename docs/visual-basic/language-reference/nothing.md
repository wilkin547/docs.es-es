---
title: "Nothing (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Nothing"
  - "vb.Nothing"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Nothing (palabra clave)"
  - "Nothing (palabra clave), sintaxis"
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# Nothing (Visual Basic)
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

Representa el valor predeterminado de cualquier tipo de datos.  para los tipos de referencia, el valor predeterminado es la referencia de `null` .  Para los tipos de valor, el valor predeterminado depende de si el tipo de valor es que acepta valores NULL.  
  
> [!NOTE]
>  Para los tipos de valor que no aceptan valores NULL, `Nothing` en Visual Basic diferencia de `null` en C\#.  En Visual Basic, si establece una variable de un tipo de valor que no aceptan valores NULL a `Nothing`, la variable se establece el valor predeterminado para el tipo declarado.  En C\#, si se asigna una variable de un tipo de valor que no aceptan valores NULL a `null`, se produce un error de compilación.  
  
## Comentarios  
 `Nothing` representa el valor predeterminado de un tipo de datos.  El valor predeterminado depende de si la variable es de un tipo de valor o un tipo de referencia.  
  
 una variable de un *tipo de valor* contiene directamente su valor.  los tipos de valor incluyen todos los datos numéricos, `Boolean`, `Char`, `Date`, todas las estructuras, y todas las enumeraciones.  Una variable *de un tipo de referencia* almacena una referencia a una instancia de objeto en memoria.  Clases, matrices, delegados, y cadenas de inclusión de los tipos de referencia.  Para obtener más información, vea [Tipos de valor y tipos de referencia](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Si la variable es de un tipo de valor, el comportamiento de `Nothing` depende de si la variable es de un tipo de datos acepta valores NULL.  Para representar un tipo de valor que acepta valores NULL, agregue un modificador de `?` a un nombre de tipo.  La asignación `Nothing` a una variable que establezca el valor en `null`.  Para obtener más información y ejemplos, vea [Tipos de valor que aceptan valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Si la variable es de un tipo de valor que no es que acepta valores NULL, la asignación de `Nothing` ella establecida en el valor predeterminado para el tipo declarado.  Si ese tipo contiene miembros de variables, se establecen los valores predeterminados de todos ellos.  En el ejemplo siguiente se ilustra todo esto para los tipos escalares.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/visualbasic/nothing_1.vb)]  
  
 Si una variable es de un tipo de referencia, asignándolo a `Nothing` conjuntos variables a una referencia de `null` del tipo de la variable.  Una variable que se establece en una referencia de `null` no está asociado a ningún objeto.  En el siguiente ejemplo se muestra cómo.  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/visualbasic/nothing_2.vb)]  
  
 Al comprobar si una variable de referencia \(o tipo de valor que acepta valores NULL\) es `null`, no utilice `= Nothing` o `<> Nothing`.  Utilice siempre `Is Nothing` o `IsNot Nothing`.  
  
 Para las cadenas en Visual Basic, la cadena vacía es `Nothing`.  Por consiguiente, `"" = Nothing` es true.  
  
 En el siguiente ejemplo se muestran comparaciones que usan los operadores `Is` e `IsNot`.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/visualbasic/nothing_3.vb)]  
  
 Si se declara una variable sin usar una cláusula `As` y se establece en `Nothing`, el tipo de la variable es `Object`.  Un ejemplo de esto es `Dim something = Nothing`.  Se produce un error de compilación en este caso `Option Strict` está y `Option Infer` está desactivado.  
  
 Cuando se asigna `Nothing` a una variable de objeto, ya no hace referencia a una instancia de objeto.  Si la variable anteriormente hacía referencia a una instancia, establecer dicha instancia en `Nothing` no causará la finalización de la misma.  Sólo después de que el recolector de elementos no utilizados \(GC\) detecte que ya no hay referencias activas, la instancia finalizará, y la memoria y los recursos del sistema asociados con ella quedarán liberados.  
  
 `Nothing` difiere del objeto de <xref:System.DBNull> , que representa una variante inicializado o una columna existente de la base de datos.  
  
## Vea también  
 [Dim \(Instrucción\)](../../visual-basic/language-reference/statements/dim-statement.md)   
 [Duración de los objetos: cómo se crean y destruyen](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Período de duración en Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Is \(Operador\)](../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot \(Operador\)](../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Tipos de valor que aceptan valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)