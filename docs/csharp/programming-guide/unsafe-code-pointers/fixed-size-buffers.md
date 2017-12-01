---
title: "Búferes de tamaño fijo (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3f99c2c6d477fca988fcca77de5ca5c2f8addd4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-size-buffers-c-programming-guide"></a>Búferes de tamaño fijo (Guía de programación de C#)
En C#, puede usar la instrucción [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para crear un búfer con una matriz de tamaño fijo en una estructura de datos. Esto es útil cuando se trabaja con código existente, como el código escrito en otros lenguajes, archivos DLL preexistentes o proyectos COM. La matriz fija puede tomar cualquiera de los atributos o modificadores permitidos para los miembros de structs normales. La única restricción es que el tipo de matriz debe ser `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a>Comentarios  
 En las primeras versiones de C#, declarar una estructura de tamaño fijo con el estilo de C++ era difícil, porque un struct de C# que contiene una matriz no contiene los elementos de la matriz. En su lugar, el struct contiene una referencia a los elementos.  
  
 En C# 2.0 se ha agregado la capacidad de insertar una matriz de tamaño fijo en un [struct](../../../csharp/language-reference/keywords/struct.md) cuando se usa en un bloque de código [no seguro](../../../csharp/language-reference/keywords/unsafe.md).  
  
 Por ejemplo, antes de C# 2.0, los siguientes `struct` tendrían 8 bytes de tamaño. La matriz `pathName` es una referencia a la matriz asignada en el montón:  
  
 [!code-csharp[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 Comenzando con C# 2.0, un `struct` puede contener una matriz insertada. En el siguiente ejemplo, la matriz `fixedBuffer` tiene un tamaño fijo. Para tener acceso a los elementos de la matriz, use una instrucción `fixed` para establecer un puntero al primer elemento. La instrucción `fixed` ancla una instancia de `fixedBuffer` a una ubicación concreta de la memoria.  
  
 [!code-csharp[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 El tamaño de la matriz `char` de 128 elementos es 256 bytes. Los búferes [char](../../../csharp/language-reference/keywords/char.md) de tamaño fijo siempre admiten dos bytes por carácter, independientemente de la codificación. Esto es verdadero, incluso cuando se calculan las referencias de los búferes de caracteres a los métodos API o structs con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`. Para obtener más información, consulta <xref:System.Runtime.InteropServices.CharSet>.  
  
 Otra matriz de tamaño fijo común es la matriz [bool](../../../csharp/language-reference/keywords/bool.md). Los elementos de una matriz `bool` siempre tienen un byte de tamaño. Las matrices `bool` no son adecuadas para crear matrices de bits o búferes.  
  
> [!NOTE]
>  Con excepción de la memoria creada con [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), el compilador de C# y Common Language Runtime (CLR) no realizan ninguna comprobación de saturación del búfer de seguridad. Como sucede con todo código no seguro, se ha de tener precaución.  
  
 Los búferes no seguros son diferentes de las matrices normales en los siguientes puntos:  
  
-   Solo se pueden usar búferes no seguros en un contexto no seguro.  
  
-   Los búferes no seguros siempre son vectores o matrices unidimensionales.  
  
-   La declaración de la matriz debe incluir un recuento, por ejemplo, `char id[8]`. No puede usar `char id[]` en su lugar.  
  
-   Los búferes no seguros solo pueden ser campos de instancias de structs en un contexto no seguro.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [Interoperabilidad](../../../csharp/programming-guide/interop/index.md)
