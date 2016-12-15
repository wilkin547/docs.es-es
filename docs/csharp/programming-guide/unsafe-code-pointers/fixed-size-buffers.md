---
title: "B&#250;feres de tama&#241;o fijo (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "búferes de tamaño fijo [C#]"
  - "búferes no seguros [C#]"
  - "código no seguro [C#], búferes de tamaño fijo"
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# B&#250;feres de tama&#241;o fijo (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En C\#, puede utilizar la instrucción [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para crear un búfer con una matriz de tamaño fijo en una estructura de datos.  Esto es útil cuando se trabaja con código existente, como el código escrito en otros lenguajes, archivos DLL preexistentes o proyectos COM.  La matriz fija puede tomar cualquiera de los atributos o modificadores permitidos para los miembros de structs normales.  La única restricción es que el tipo de matriz debe ser `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.  
  
```  
private fixed char name[30];  
```  
  
## Comentarios  
 En las primeras versiones de C\#, declarar una estructura de tamaño fijo con el estilo de C\+\+ era difícil, porque un struct de C\# que contiene una matriz no contiene los elementos de la matriz.  En su lugar, el struct contiene una referencia a los elementos.  
  
 En C\# 2.0 se agregó la capacidad de incrustar una matriz de tamaño fijo en un objeto [struct](../../../csharp/language-reference/keywords/struct.md) cuando se utiliza en un bloque de código [no seguro](../../../csharp/language-reference/keywords/unsafe.md).  
  
 Por ejemplo, antes de C\# 2.0, los siguientes `struct` tendrían 8 bytes de tamaño.  La matriz `pathName` es una referencia a la matriz asignada en el montón:  
  
 [!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 Comenzando con C\# 2.0, un `struct` puede contener una matriz incrustada.  En el siguiente ejemplo, la matriz `fixedBuffer` tiene un tamaño fijo.  Para tener acceso a los elementos de la matriz, use una instrucción `fixed` para establecer un puntero al primer elemento.  La instrucción `fixed` ancla una instancia de `fixedBuffer` a una ubicación concreta de la memoria.  
  
 [!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 El tamaño de la matriz `char` de 128 elementos es 256 bytes.  Los búferes [char](../../../csharp/language-reference/keywords/char.md) de tamaño fijo siempre admiten dos bytes por carácter, independientemente de la codificación.  Esto es verdadero, incluso cuando se calculan las referencias de los búferes de caracteres a los métodos API o structs con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`.  Para obtener más información, vea <xref:System.Runtime.InteropServices.CharSet>.  
  
 Otra matriz de tamaño fijo común es la matriz [bool](../../../csharp/language-reference/keywords/bool.md).  Los elementos de una matriz `bool` siempre tienen un byte de tamaño.  Las matrices `bool` no son adecuadas para crear matrices de bits o búferes.  
  
> [!NOTE]
>  Con excepción de la memoria creada con [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), el compilador de C\# y Common Language Runtime \(CLR\) no realizan ninguna comprobación de saturación del búfer de seguridad.  Como sucede con todo código no seguro, se ha de tener precaución.  
  
 Los búferes no seguros son diferentes de las matrices normales en los siguientes puntos:  
  
-   Sólo se pueden utilizar búferes no seguros en un contexto no seguro.  
  
-   Los búferes no seguros siempre son vectores, o matrices unidimensionales.  
  
-   La declaración de la matriz debe incluir un recuento, por ejemplo, `char id[8]`.  No puede utilizar `char id[]` en su lugar.  
  
-   Los búferes no seguros sólo pueden ser campos de instancias de structs en un contexto no seguro.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Interoperabilidad](../../../csharp/programming-guide/interop/interoperability.md)