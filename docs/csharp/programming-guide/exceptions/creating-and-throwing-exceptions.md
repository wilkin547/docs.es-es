---
title: Creación y producción de excepciones - Guía de programación de C#
description: Aprenda a crear e iniciar excepciones. Se usan excepciones para indicar que se ha producido un error mientras se ejecutaba un programa.
ms.date: 12/09/2020
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
ms.openlocfilehash: a6998c5b274736b290460808ad4c7cb22be7ebf6
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110213"
---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a>Crear y producir excepciones (Guía de programación de C#)

Las excepciones se usan para indicar que se ha producido un error mientras se ejecutaba el programa. Se crean los objetos de excepción que describen un error y, luego, se *producen* con la palabra clave [throw](../../language-reference/keywords/throw.md). Después, el tiempo de ejecución busca el controlador de excepciones más compatible.

Los programadores deberían producir excepciones cuando una o varias de las siguientes condiciones sean verdaderas:

- El método no puede finalizar su función definida. Por ejemplo, si un parámetro de un método tiene un valor no válido:
  :::code language="csharp" source="snippets/exceptions/Program.cs" ID="CantComplete":::
- Se realiza una llamada inadecuada a un objeto, en función del estado del objeto. Un ejemplo podría ser intentar escribir en un archivo de solo lectura. En los casos en los que un estado de objeto no permite una operación, genere una instancia de <xref:System.InvalidOperationException> o un objeto con base en una derivación de esta clase. El código siguiente es un ejemplo de un método que genera un objeto <xref:System.InvalidOperationException>:
  :::code language="csharp" source="snippets/exceptions/ProgramLog.cs" ID="ProgramLog":::
- Cuando un argumento de un método genera una excepción. En este caso, se debe detectar la excepción original y se debe crear una instancia de <xref:System.ArgumentException>. La excepción original debe pasarse al constructor de <xref:System.ArgumentException> como el parámetro <xref:System.Exception.InnerException%2A>:
  :::code language="csharp" source="snippets/exceptions/Program.cs" ID="InvalidArg":::

Las excepciones contienen una propiedad denominada <xref:System.Exception.StackTrace%2A>. Esta cadena contiene el nombre de los métodos de la pila de llamadas actual, junto con el nombre de archivo y el número de la línea en la que se ha producido la excepción para cada método. Common Language Runtime (CLR) crea automáticamente un objeto <xref:System.Exception.StackTrace%2A> desde el punto de la instrucción `throw`, de manera que todas las excepciones se deben producir desde el punto en el que debe comenzar el seguimiento de la pila.

Todas las excepciones contienen una propiedad denominada <xref:System.Exception.Message%2A>. Esta cadena debe establecerse para que explique el motivo de la excepción. No se debe colocar información confidencial en materia de seguridad en el texto del mensaje. Además de <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contiene una propiedad denominada <xref:System.ArgumentException.ParamName%2A> que debe establecerse en el nombre del argumento que ha provocado que se genere la excepción. En un establecedor de propiedades, <xref:System.ArgumentException.ParamName%2A> debe establecerse en `value`.

Los métodos públicos y protegidos generan excepciones siempre que no puedan finalizar sus funciones previstas. La clase de excepciones generada es la excepción más específica disponible que se ajuste a las condiciones de error. Estas excepciones se deben documentar como parte de la funcionalidad de la clase, y las clases derivadas o actualizaciones de la clase original deben mantener el mismo comportamiento para la compatibilidad con versiones anteriores.

## <a name="things-to-avoid-when-throwing-exceptions"></a>Aspectos que se deben evitar al producir excepciones

En la siguiente lista se identifican los procedimientos que se deben evitar al producir excepciones:

- No use excepciones para cambiar el flujo de un programa como parte de la ejecución normal. Use excepciones para notificar y controlar condiciones de error.
- Las excepciones no se deben devolver como un parámetro o valor devuelto en lugar de producirse.
- No genere <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType> ni <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> de manera intencionada desde su propio código fuente.
- No cree excepciones que se puedan producir en el modo de depuración, pero no en el modo de lanzamiento. Para identificar los errores en tiempo de ejecución durante la fase de desarrollo, use la aserción de depuración.

## <a name="defining-exception-classes"></a>Definir clases de excepción

Los programas pueden producir una clase de excepción predefinida en el espacio de nombres <xref:System> (excepto en los casos indicados anteriormente) o crear sus propias clases de excepción mediante la derivación de <xref:System.Exception>. Las clases derivadas deben definir al menos cuatro constructores: un constructor sin parámetros, uno que establezca la propiedad de mensaje y otro que establezca las propiedades <xref:System.Exception.Message%2A> y <xref:System.Exception.InnerException%2A>. El cuarto constructor se usa para serializar la excepción. Las nuevas clases de excepción deben ser serializables. Por ejemplo:

:::code language="csharp" source="snippets/exceptions/InvalidDepartmentException.cs" id="DefineExceptionClass":::

Agregue propiedades nuevas a la clase de excepción cuando los datos que proporcionan sean útiles para resolver la excepción. Si se agregan nuevas propiedades a la clase de excepción derivada, se debe invalidar `ToString()` para devolver la información agregada.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea las secciones [Excepciones](~/_csharplang/spec/exceptions.md) y [La instrucción throw](~/_csharplang/spec/statements.md#the-throw-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- [Jerarquía de excepciones](../../../standard/exceptions/index.md)
