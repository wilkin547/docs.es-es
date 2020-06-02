---
title: Excepciones y rendimiento
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: a558547f0e6770e7e76ca31f760d6e2f55c712db
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289790"
---
# <a name="exceptions-and-performance"></a>Excepciones y rendimiento
Un problema común relacionado con las excepciones es que si se usan excepciones para el código que genera un error de forma rutinaria, el rendimiento de la implementación será inaceptable. Este es un problema válido. Cuando un miembro produce una excepción, su rendimiento puede ser un orden de magnitud más lento. Sin embargo, es posible lograr un buen rendimiento al tiempo que se respetan estrictamente las instrucciones de excepción que no permiten el uso de códigos de error. Dos patrones que se describen en esta sección sugieren maneras de hacerlo.

 ❌No utilice códigos de error debido a las preocupaciones de que las excepciones podrían afectar negativamente al rendimiento.

 Para mejorar el rendimiento, es posible usar el patrón Tester-doer o el patrón try-Parse, que se describe en las dos secciones siguientes.

## <a name="tester-doer-pattern"></a>Evaluador: patrón doer
 A veces, el rendimiento de un miembro de generación de excepciones se puede mejorar dividiendo el miembro en dos. Echemos un vistazo al <xref:System.Collections.Generic.ICollection%601.Add%2A> método de la <xref:System.Collections.Generic.ICollection%601> interfaz.

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 El método `Add` produce si la colección es de solo lectura. Puede tratarse de un problema de rendimiento en escenarios en los que se espera que la llamada al método no se realice con frecuencia. Una de las formas de mitigar el problema consiste en probar si se puede escribir en la colección antes de intentar agregar un valor.

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly` , se conoce como evaluador. El miembro que se utiliza para realizar una operación de inicio potencial, el `Add` método en nuestro ejemplo, se conoce como doer.

 ✔️ CONSIDERE el patrón Tester-doer para los miembros que podrían producir excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.

## <a name="try-parse-pattern"></a>Patrón try-Parse
 En el caso de las API extremadamente sensibles al rendimiento, se debe usar un patrón aún más rápido que el patrón Tester-doer descrito en la sección anterior. El patrón llama a para ajustar el nombre del miembro con el fin de convertir un caso de prueba bien definido en una parte de la semántica de los miembros. Por ejemplo, <xref:System.DateTime> define un <xref:System.DateTime.Parse%2A> método que produce una excepción si se produce un error en el análisis de una cadena. También define un método correspondiente <xref:System.DateTime.TryParse%2A> que intenta analizar, pero devuelve false si el análisis no se realiza correctamente y devuelve el resultado de un análisis correcto mediante un `out` parámetro.

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 Al usar este patrón, es importante definir la funcionalidad try en términos estrictos. Si se produce un error en el miembro por cualquier motivo que no sea el try bien definido, el miembro todavía debe producir una excepción correspondiente.

 ✔️ CONSIDERE el patrón try-Parse para los miembros que podrían producir excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.

 ✔️ usar el prefijo "Try" y el tipo de valor devuelto booleano para los métodos que implementan este patrón.

 ✔️ proporcionan un miembro de generación de excepciones para cada miembro mediante el patrón try-Parse.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de diseño de excepciones](exceptions.md)
