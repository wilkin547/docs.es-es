---
title: 'Constantes: Guía de programación de C#'
description: En C#, las constantes son valores literales en tiempo de compilación, que no cambian después de compilar el programa. Solo los tipos integrados de C# pueden ser constantes.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 1252e214be03f8a180fadb7667ee59f36a862040
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558431"
---
# <a name="constants-c-programming-guide"></a>Constantes (Guía de programación de C#)
Las constantes son valores inmutables que se conocen en tiempo de compilación y que no cambian durante la vida del programa. Las constantes se declaran con el modificador [const](../../language-reference/keywords/const.md). Solo los [tipos integrados](../../language-reference/builtin-types/built-in-types.md) de C# (excluido <xref:System.Object?displayProperty=nameWithType>) pueden declararse como `const`. Los tipos definidos por el usuario, incluidas las clases, las estructuras y las matrices, no pueden ser `const`. Use el modificador [readonly](../../language-reference/keywords/readonly.md) para crear una clase, una estructura o una matriz que se inicialice una vez en tiempo de ejecución (por ejemplo, en un constructor) y que posteriormente no se pueda cambiar.  
  
 C# no admite métodos, propiedades ni eventos `const`.  
  
 El tipo enum permite definir constantes con nombre para los tipos integrados enteros (por ejemplo, `int`, `uint`, `long`, etc.). Para más información, vea [enum](../../language-reference/builtin-types/enum.md).  
  
 Las constantes se deben inicializar al declararse. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#64](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#64)]  
  
 En este ejemplo la constante `Months` siempre es 12 y ni siquiera la propia clase la puede cambiar. De hecho, cuando el compilador detecta un identificador de constante en el código fuente de C# (por ejemplo, `Months`), sustituye directamente el valor literal en el código de lenguaje intermedio (IL) que genera. Dado que no hay ninguna dirección de variable asociada a una constante en tiempo de ejecución, no se pueden pasar los campos `const` por referencia ni pueden aparecer como un valor L en una expresión.  
  
> [!NOTE]
> Tenga cuidado al hacer referencia a valores de constante definidos en otro código como archivos DLL. Si una nueva versión del archivo DLL define un nuevo valor para la constante, el programa conservará el valor literal anterior hasta que se vuelva a compilar con la versión nueva.  
  
 Se pueden declarar varias constantes del mismo tipo a la vez, por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#65)]  
  
 La expresión que se usa para inicializar una constante puede hacer referencia a otra constante si no crea una referencia circular. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#66](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#66)]  
  
 Las constantes pueden marcarse como [públicas](../../language-reference/keywords/public.md), [privadas](../../language-reference/keywords/private.md), [protegidas](../../language-reference/keywords/protected.md), [internas](../../language-reference/keywords/internal.md), [protegidas internas](../../language-reference/keywords/protected-internal.md)o [privadas protegidas](../../language-reference/keywords/private-protected.md). Estos modificadores de acceso definen cómo los usuarios de la clase pueden acceder a la constante. Para más información, vea [Modificadores de acceso](./access-modifiers.md).  
  
 A las constantes se accede como si fueran campos [estáticos](../../language-reference/keywords/static.md) porque el valor de la constante es el mismo para todas las instancias del tipo. No use la palabra clave `static` para declararlas. Las expresiones que no están en la clase que define la constante deben usar el nombre de la clase, un punto y el nombre de la constante para acceder a ella. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#67](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#67)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Propiedades](./properties.md)
- [Tipos](../types/index.md)
- [readonly](../../language-reference/keywords/readonly.md)
- [Inmutabilidad en la primera parte de C#: tipos de inmutabilidad](https://docs.microsoft.com/archive/blogs/ericlippert/immutability-in-c-part-one-kinds-of-immutability)
