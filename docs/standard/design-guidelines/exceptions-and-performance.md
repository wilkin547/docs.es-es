---
description: 'Más información acerca de: Excepciones y rendimiento'
title: Excepciones y rendimiento
ms.date: 10/22/2008
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: 72b35ccca5514e56dcc04fc0a07d1f9887c4a2f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642128"
---
# <a name="exceptions-and-performance"></a>Excepciones y rendimiento

Un problema común relacionado con las excepciones es que si se usan excepciones para el código que genera errores de forma rutinaria, el rendimiento de la implementación será inaceptable. Tiene sentido que exista esta preocupación. Cuando un miembro genera una excepción, su rendimiento puede ser más lento. Sin embargo, es posible conseguir un buen rendimiento al tiempo que se respetan estrictamente las instrucciones de excepción que no permiten el uso de códigos de error. Dos patrones que se describen en esta sección sugieren varias formas de hacerlo.

 ❌ NO utilice códigos de error debido a que las excepciones podrían afectar negativamente al rendimiento.

 Para mejorar el rendimiento, es posible usar el patrón tester-doer o el patrón try-parse, que se describen en las dos secciones siguientes.

## <a name="tester-doer-pattern"></a>Patrón tester-doer

 A veces, el rendimiento de un miembro de generación de excepciones se puede mejorar dividiéndolo en dos. Echemos un vistazo al método <xref:System.Collections.Generic.ICollection%601.Add%2A> de la interfaz <xref:System.Collections.Generic.ICollection%601>.

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 El método `Add` se inicia si la colección es de solo lectura. Puede tratarse de un problema de rendimiento en escenarios en los que se espera que la llamada de método no se realice con frecuencia. Una de las formas de mitigar el problema consiste en probar si se puede escribir en la colección antes de intentar agregar un valor.

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly`, se conoce como "evaluador". Al miembro que se utiliza para realizar una operación potencialmente generadora de excepciones, el método `Add` en nuestro ejemplo, se le conoce como "doer".

 ✔️ Recomendamos el patrón tester-doer para los miembros que podrían generar excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.

## <a name="try-parse-pattern"></a>Patrón try-parse

 En el caso de las API extremadamente sensibles al rendimiento, se debe usar un patrón aún más rápido que el patrón tester-doer descrito en la sección anterior. El patrón realiza llamadas para ajustar el nombre de los miembros con el fin de convertir un caso de prueba bien definido en una parte de la semántica de los miembros. Por ejemplo, <xref:System.DateTime> define un método <xref:System.DateTime.Parse%2A> que genera una excepción si se produce un error en el análisis de una cadena. También define un método <xref:System.DateTime.TryParse%2A> correspondiente que intenta analizar, pero devuelve el valor false si el análisis no se realiza correctamente, y el resultado de un análisis correcto mediante un parámetro `out`.

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

 Al usar este patrón, es importante definir la funcionalidad try en términos estrictos. Si se produce un error en el miembro por cualquier motivo que no sea la funcionalidad try bien definida, el miembro todavía debería generar una excepción correspondiente.

 ✔️ Recomendamos el patrón try-parse para los miembros que podrían generar excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.

 ✔️ Use el prefijo "try" y el tipo de valor devuelto booleano para los métodos que implementan este patrón.

 ✔️ Proporcione un miembro de generación de excepciones para cada miembro mediante el patrón try-parse.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Instrucciones de diseño de excepciones](exceptions.md)
