---
title: "Palabra clave predeterminada en código genérico (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b5f5995b720d377717a5fff8a5e7e6e2196c612c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="default-keyword-in-generic-code-c-programming-guide"></a>Palabra clave predeterminada en código genérico (Guía de programación de C#)
En las clases y los métodos genéricos, un problema que aparece es cómo asignar un valor predeterminado a un T de tipo parametrizado cuando no conoce la siguiente información de antemano:  
  
-   Si T será un tipo de referencia o un tipo de valor.  
  
-   Si T es un tipo de valor, si será un valor numérico o un struct.  
  
 Con una variable t de un T de tipo parametrizado, la instrucción t = null solo es válida si T es un tipo de referencia y t = 0 solo funcionará para tipos de valor numérico pero no para structs. La solución es usar la palabra clave `default`, que devolverá NULL para los tipos de referencia y cero para los tipos de valor numérico. Para los structs, devolverá cada miembro del struct inicializado en cero o NULL dependiendo de si son tipos de referencia o valor. Para los tipos de valor que aceptan valores NULL, se devuelve <xref:System.Nullable%601?displayProperty=fullName> de manera predeterminada, que se inicializa como cualquier struct.  
  
 El ejemplo siguiente de la clase `GenericList<T>` muestra cómo usar la palabra clave `default`. Para obtener más información, vea [Información general de genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-code_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Genéricos](~/docs/standard/generics/index.md)

