---
title: Creación y producción de excepciones - Guía de programación de C#
description: Aprenda a crear e iniciar excepciones. Se usan excepciones para indicar que se ha producido un error mientras se ejecutaba un programa.
ms.date: 07/20/2015
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
ms.openlocfilehash: 77a1e8eb4d442e66f8b9ed17a5881661a5990a35
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195498"
---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a>Crear y producir excepciones (Guía de programación de C#)

Las excepciones se usan para indicar que se ha producido un error mientras se ejecutaba el programa. Se crean los objetos de excepción que describen un error y, luego, se *producen* con la palabra clave [throw](../../language-reference/keywords/throw.md). Después, el tiempo de ejecución busca el controlador de excepciones más compatible.  
  
 Los programadores deberían producir excepciones cuando una o varias de las siguientes condiciones sean verdaderas:  
  
- El método no puede finalizar su funcionalidad definida.  
  
     Por ejemplo, si un parámetro de un método tiene un valor no válido:  
  
     [!code-csharp[csProgGuideExceptions#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#12)]  
  
- Se realiza una llamada inadecuada a un objeto, en función del estado del objeto.  
  
     Un ejemplo podría ser intentar escribir en un archivo de solo lectura. En los casos en los que un estado de objeto no admite una operación, produzca una instancia de <xref:System.InvalidOperationException> o un objeto basado en una derivación de esta clase. Este es un ejemplo de un método que genera un objeto <xref:System.InvalidOperationException>:  
  
     [!code-csharp[csProgGuideExceptions#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#13)]  
  
- Cuando un argumento de un método genera una excepción.  
  
     En este caso, se debe detectar la excepción original y se debe crear una instancia de <xref:System.ArgumentException>. La excepción original debe pasarse al constructor de <xref:System.ArgumentException> como el parámetro <xref:System.Exception.InnerException%2A>:  
  
     [!code-csharp[csProgGuideExceptions#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#14)]  
  
 Las excepciones contienen una propiedad denominada <xref:System.Exception.StackTrace%2A>. Esta cadena contiene el nombre de los métodos de la pila de llamadas actual, junto con el nombre de archivo y el número de la línea en la que se ha producido la excepción para cada método. Common Language Runtime (CLR) crea automáticamente un objeto <xref:System.Exception.StackTrace%2A> desde el punto de la instrucción `throw`, de manera que todas las excepciones se deben producir desde el punto en el que debe comenzar el seguimiento de la pila.  
  
 Todas las excepciones contienen una propiedad denominada <xref:System.Exception.Message%2A>. Esta cadena debe establecerse para que explique el motivo de la excepción. Tenga en cuenta que no se debe colocar información confidencial en materia de seguridad en el texto del mensaje. Además de <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contiene una propiedad denominada <xref:System.ArgumentException.ParamName%2A> que debe establecerse en el nombre del argumento que ha provocado que se genere la excepción. En el caso de un establecedor de propiedades, <xref:System.ArgumentException.ParamName%2A> debe establecerse en `value`.  
  
 Los métodos públicos y protegidos deben producir excepciones cada vez que no puedan finalizar sus funciones previstas. La clase de excepciones que se produce debe ser la excepción más específica disponible que se ajuste a las condiciones del error. Estas excepciones se deben documentar como parte de la funcionalidad de la clase, y las clases derivadas o actualizaciones de la clase original deben mantener el mismo comportamiento para la compatibilidad con versiones anteriores.  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a>Aspectos que se deben evitar al producir excepciones  

 En la siguiente lista se identifican los procedimientos que se deben evitar al producir excepciones:  
  
- Las excepciones no deben usarse para cambiar el flujo de un programa como parte de la ejecución normal. Las excepciones solo deben usarse para comunicar y controlar las condiciones de error.  
  
- Las excepciones no se deben devolver como un parámetro o valor devuelto en lugar de producirse.  
  
- No genere <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType> o <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> de manera intencionada desde su propio código fuente.  
  
- No cree excepciones que se puedan producir en el modo de depuración, pero no en el modo de lanzamiento. Para identificar los errores en tiempo de ejecución durante la fase de desarrollo, use la aserción de depuración.  
  
## <a name="defining-exception-classes"></a>Definir clases de excepción  

 Los programas pueden producir una clase de excepción predefinida en el espacio de nombres <xref:System> (excepto en los casos indicados anteriormente) o crear sus propias clases de excepción mediante la derivación de <xref:System.Exception>. Las clases derivadas deben definir al menos cuatro constructores: un constructor sin parámetros, uno que establezca la propiedad de mensaje y otro que establezca las propiedades <xref:System.Exception.Message%2A> y <xref:System.Exception.InnerException%2A>. El cuarto constructor se usa para serializar la excepción. Las nuevas clases de excepción deben ser serializables. Por ejemplo:  
  
 [!code-csharp[csProgGuideExceptions#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#15)]  
  
 Las nuevas propiedades solo deben agregarse a la clase de excepción cuando los datos que proporcionan son útiles para resolver la excepción. Si se agregan nuevas propiedades a la clase de excepción derivada, se debe invalidar `ToString()` para devolver la información agregada.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea las secciones [Excepciones](~/_csharplang/spec/exceptions.md) y [La instrucción throw](~/_csharplang/spec/statements.md#the-throw-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Excepciones y control de excepciones](./index.md)
- [Jerarquía de excepciones](../../../standard/exceptions/index.md)
- [Control de excepciones](./exception-handling.md)
