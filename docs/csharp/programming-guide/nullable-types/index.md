---
title: "Tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, tipos que aceptan valores NULL"
  - "tipos que aceptan valores NULL [C#]"
  - "tipos [C#], que aceptan valores NULL"
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
caps.handback.revision: 44
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los tipos que aceptan valores NULL son instancias del struct <xref:System.Nullable%601?displayProperty=fullName>.  Un tipo que acepta valores NULL puede representar el intervalo de valores correcto para su tipo de valor subyacente, además de un valor `null` adicional.  Por ejemplo, a un tipo `Nullable<Int32>` se le puede asignar cualquier valor entre \-2147483648 y 2147483647, o el valor `null`.  A `Nullable<bool>` se le pueden asignar los valores [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) o [null](../../../csharp/language-reference/keywords/null.md).  La posibilidad de asignar `null` a tipos numéricos y booleanos resulta especialmente útil para trabajar con bases de datos y otros tipos de datos que contienen elementos que pueden no tener un valor asignado.  Por ejemplo, un campo Boolean de una base de datos puede almacenar los valores  `true` o `false`, o puede ser indefinido.  
  
 [!code-cs[csProgGuideTypes#3](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_1.cs)]  
  
 El ejemplo mostrará este resultado:  
  
 `num = Null`  
  
 `Nullable object must have a value.`  
  
 Para obtener más ejemplos, vea [Utilizar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).  
  
## Información general acerca de los tipos que aceptan valores NULL  
 Los tipos que aceptan valores NULL tienen las características siguientes:  
  
-   Los tipos que aceptan valores NULL representan variables de tipo de valor a las que se puede asignar el valor `null`.  No se puede crear un tipo que acepta valores NULL basado en un tipo de referencia.  \(Los tipos de referencia ya admiten el valor `null`.\)  
  
-   La sintaxis `T?` es la forma abreviada de <xref:System.Nullable%601>, donde `T` es un tipo de valor.  Las dos formas son intercambiables.  
  
-   Asigne un valor a un tipo que acepte valores NULL como si se tratara de un tipo de valor normal; por ejemplo, `int? x = 10;` o `double? d = 4.108`.  Un tipo que acepta valores null también puede tener asignado el valor `null`: `int? x = null.`  
  
-   Utilice el método <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> para devolver el valor asignado o el valor predeterminado del tipo subyacente si el valor es `null`, por ejemplo `int j = x.GetValueOrDefault();`  
  
-   Utilice las propiedades de solo lectura <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> para comprobar si el valor es NULL y recuperar el valor, como se muestra en el ejemplo siguiente: `if(x.HasValue) j = x.Value;`  
  
    -   La propiedad `HasValue` devuelve `true` si la variable contiene un valor, o bien `false` si es `null`.  
  
    -   La propiedad `Value` devuelve un valor si se ha asignado uno.  De lo contrario, se inicia una excepción <xref:System.InvalidOperationException?displayProperty=fullName>.  
  
    -   El valor predeterminado para `HasValue` es `false`.  La propiedad `Value` no tiene valor predeterminado.  
  
    -   También puede usar los operadores `==` y `!=` con un tipo que acepta valores null, como se muestra en el ejemplo siguiente: `if (x != null) y = x;`  
  
-   Utilice el operador `??` para asignar un valor predeterminado que se aplicará cuando un tipo que acepta valores NULL cuyo valor actual sea `null`se asigne a un tipo que no acepte valores NULL, por ejemplo `int? x = null; int y = x ?? -1;`  
  
-   No se permite la anidación de tipos que aceptan valores NULL.  La línea siguiente no se compilará: `Nullable<Nullable<int>> n;`  
  
## Secciones relacionadas  
 Para obtener más información:  
  
-   [Utilizar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Aplicar la conversión boxing a tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [Operador ??](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.Nullable>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [C\#](../../../csharp/csharp.md)   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [¿Qué hace exactamente medio “levantado”?](http://go.microsoft.com/fwlink/?LinkId=112382)