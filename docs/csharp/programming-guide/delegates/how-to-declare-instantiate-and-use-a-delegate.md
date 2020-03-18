---
title: 'Procedimiento Declarar un delegado, crear instancias del mismo y utilizarlo: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 7ac1d736e19c4dcf1c8408db944505c399762778
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712369"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a>Procedimiento Declarar un delegado, crear instancias del mismo y utilizarlo (Guía de programación de C#)
En C# 1.0 y versiones posteriores, los delegados se pueden declarar como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 C# 2.0 ofrece una forma más sencilla de escribir la declaración anterior, tal como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 En C# 2.0 y versiones posteriores, también es posible utilizar un método anónimo para declarar e inicializar un [delegado](../../language-reference/builtin-types/reference-types.md), como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 En C# 3.0 y versiones posteriores, también se pueden declarar los delegados y crear una instancia de ellos mediante una expresión lambda, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 Para obtener más información, vea [Expresiones lambda](../statements-expressions-operators/lambda-expressions.md).  
  
 En el ejemplo siguiente se ilustra cómo declarar un delegado, crear una instancia del mismo y utilizarlo La clase `BookDB` encapsula una base de datos de una librería que mantiene una base de datos de libros. Expone un método `ProcessPaperbackBooks`, que busca todos los libros de bolsillo en la base de datos y llama a un delegado para cada uno. El tipo `delegate` utilizado se denomina `ProcessBookDelegate`. La clase `Test` utiliza esta clase para imprimir los títulos y el precio medio de los libros de bolsillo.  
  
 El uso de delegados promueve una separación adecuada de la funcionalidad entre la base de datos de la librería y el código de cliente. El código de cliente no sabe cómo se almacenan los libros ni cómo el código de la biblioteca encuentra los libros de bolsillo. El código de la librería no sabe qué procesamiento se realiza con los libros de bolsillo después de que los encuentra.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a>Programación sólida  
  
- Declaración de un delegado.  
  
     La instrucción siguiente declara un nuevo tipo de delegado.  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     Cada tipo de delegado describe el número y los tipos de argumentos, y el tipo del valor devuelto de los métodos que puede encapsular. Siempre que se necesite un nuevo conjunto de tipos de argumentos o de tipos de valores devueltos, se debe declarar un nuevo tipo de delegado.  
  
- Creación de instancias de un delegado.  
  
     Después de haber declarado un tipo de delegado, debe crearse un objeto delegado y asociarse con un método particular. En el ejemplo anterior, esto se hace pasando el método `PrintTitle` al método `ProcessPaperbackBooks` como en el ejemplo siguiente:  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     Esto crea un objeto delegado nuevo asociado con el método [estático](../../language-reference/keywords/static.md)`Test.PrintTitle`. De forma similar, el método no estático `AddBookToTotal` del objeto `totaller` se pasa como en el ejemplo siguiente:  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     En ambos casos, se pasa un nuevo objeto delegado al método `ProcessPaperbackBooks`.  
  
     Después de que se ha creado un delegado, el método con el que está asociado nunca cambia; los objetos delegados son inmutables.  
  
- Llamada a un delegado.  
  
     Después de haber creado un objeto delegado, este suele pasarse a otro código que llamará al delegado. La llamada a un objeto delegado se realiza mediante la utilización del nombre de dicho objeto, seguido de los argumentos entre paréntesis que se deben pasar al delegado. A continuación se expone un ejemplo de llamada a un delegado:  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     Se puede llamar a un delegado de forma sincrónica, como en este ejemplo, o bien de forma asincrónica con los métodos `BeginInvoke` y `EndInvoke`.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Eventos](../events/index.md)
- [Delegados](./index.md)
