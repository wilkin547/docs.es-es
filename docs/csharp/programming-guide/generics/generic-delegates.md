---
title: 'Delegados genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: ff19b3d71858552158a8ae5d0ab362a86dc98e65
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423494"
---
# <a name="generic-delegates-c-programming-guide"></a>Delegados genéricos (Guía de programación de C#)
Un [delegado](../../../csharp/language-reference/keywords/delegate.md) puede definir sus propios parámetros de tipo. El código que hace referencia al delegado genérico puede especificar el tipo de argumento para crear un tipo construido abierto, igual que al crear una instancia de una clase genérica o al llamar a un método genérico, como se muestra en el siguiente ejemplo:  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 C# 2.0 tiene una nueva característica denominada conversión de grupo de métodos, que se aplica a los tipos delegados concretos y genéricos, y permite escribir la línea anterior con esta sintaxis simplificada:  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 Los delegados definidos dentro de una clase genérica pueden usar los parámetros de tipo de la clase genérica de la misma manera que lo hacen los métodos de clase.  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 El código que hace referencia al delegado debe especificar el argumento de tipo de la clase contenedora, de la siguiente manera:  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 Los delegados genéricos son especialmente útiles para definir eventos basados en el patrón de diseño habitual porque el argumento del remitente puede estar fuertemente tipado y ya no tiene que convertirse a y de <xref:System.Object>.  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Introducción a los genéricos](../../../csharp/programming-guide/generics/index.md)
- [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md)
- [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md)
- [Interfaces genéricas](../../../csharp/programming-guide/generics/generic-interfaces.md)
- [Delegados](../../../csharp/programming-guide/delegates/index.md)
- [Genéricos](~/docs/standard/generics/index.md)
