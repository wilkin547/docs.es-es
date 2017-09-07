---
title: "Crear y producir excepciones (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
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
ms.openlocfilehash: 5f49b0911aa94480988987f209bc73d187451620
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a>Crear y producir excepciones (Guía de programación de C#)
Las excepciones se usan para indicar que se ha producido un error mientras se ejecutaba el programa. Se crean los objetos de excepción que describen un error y, luego, se *producen* con la palabra clave [throw](../../../csharp/language-reference/keywords/throw.md). Después, el tiempo de ejecución busca el controlador de excepciones más compatible.  
  
 Los programadores deberían producir excepciones cuando una o varias de las siguientes condiciones sean verdaderas:  
  
-   El método no puede finalizar su funcionalidad definida.  
  
     Por ejemplo, si un parámetro de un método tiene un valor no válido:  
  
     [!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]  
  
-   Se realiza una llamada inadecuada a un objeto, en función del estado del objeto.  
  
     Un ejemplo podría ser intentar escribir en un archivo de solo lectura. En los casos en los que un estado de objeto no admite una operación, produzca una instancia de <xref:System.InvalidOperationException> o un objeto basado en una derivación de esta clase. Este es un ejemplo de un método que genera un objeto <xref:System.InvalidOperationException>:  
  
     [!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]  
  
-   Cuando un argumento de un método genera una excepción.  
  
     En este caso, se debe detectar la excepción original y se debe crear una instancia de <xref:System.ArgumentException>. La excepción original debe pasarse al constructor de <xref:System.ArgumentException> como el parámetro <xref:System.Exception.InnerException%2A>:  
  
     [!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]  
  
 Las excepciones contienen una propiedad denominada <xref:System.Exception.StackTrace%2A>. Esta cadena contiene el nombre de los métodos de la pila de llamadas actual, junto con el nombre de archivo y el número de la línea en la que se ha producido la excepción para cada método. Common Language Runtime (CLR) crea automáticamente un objeto <xref:System.Exception.StackTrace%2A> desde el punto de la instrucción `throw`, de manera que todas las excepciones se deben producir desde el punto en el que debe comenzar el seguimiento de la pila.  
  
 Todas las excepciones contienen una propiedad denominada <xref:System.Exception.Message%2A>. Esta cadena debe establecerse para que explique el motivo de la excepción. Tenga en cuenta que no se debe colocar información confidencial en materia de seguridad en el texto del mensaje. Además de <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contiene una propiedad denominada <xref:System.ArgumentException.ParamName%2A> que debe establecerse en el nombre del argumento que ha provocado que se genere la excepción. En el caso de un establecedor de propiedades, <xref:System.ArgumentException.ParamName%2A> debe establecerse en `value`.  
  
 Los miembros de métodos públicos y protegidos deben producir excepciones cada vez que no puedan finalizar sus funciones previstas. La clase de excepciones que se produce debe ser la excepción más específica disponible que se ajuste a las condiciones del error. Estas excepciones se deben documentar como parte de la funcionalidad de la clase, y las clases derivadas o actualizaciones de la clase original deben mantener el mismo comportamiento para la compatibilidad con versiones anteriores.  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a>Aspectos que se deben evitar al producir excepciones  
 En la siguiente lista se identifican los procedimientos que se deben evitar al producir excepciones:  
  
-   Las excepciones no deben usarse para cambiar el flujo de un programa como parte de la ejecución normal. Las excepciones solo deben usarse para comunicar y controlar las condiciones de error.  
  
-   Las excepciones no se deben devolver como un parámetro o valor devuelto en lugar de producirse.  
  
-   No genere <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> o <xref:System.IndexOutOfRangeException?displayProperty=fullName> de manera intencionada desde su propio código fuente.  
  
-   No cree excepciones que se puedan producir en el modo de depuración, pero no en el modo de lanzamiento. Para identificar los errores en tiempo de ejecución durante la fase de desarrollo, use la aserción de depuración.  
  
## <a name="defining-exception-classes"></a>Definir clases de excepción  
 Los programas pueden producir una clase de excepción predefinida en el espacio de nombres <xref:System> (excepto en los casos indicados anteriormente) o crear sus propias clases de excepción mediante la derivación de <xref:System.Exception>. Las clases derivadas deben definir al menos cuatro constructores: un constructor predeterminado, uno que establezca la propiedad de mensaje y otro que establezca las propiedades <xref:System.Exception.Message%2A> y <xref:System.Exception.InnerException%2A>. El cuarto constructor se usa para serializar la excepción. Las nuevas clases de excepción deben ser serializables. Por ejemplo:  
  
 [!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]  
  
 Las nuevas propiedades solo deben agregarse a la clase de excepción cuando los datos que proporcionan son útiles para resolver la excepción. Si se agregan nuevas propiedades a la clase de excepción derivada, se debe invalidar `ToString()` para devolver la información agregada.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md)   
 [Exception Hierarchy](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b)  (Jerarquía de excepciones)  
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)

