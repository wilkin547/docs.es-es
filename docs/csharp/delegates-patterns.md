---
title: Patrones comunes para delegados
description: Obtenga información sobre los patrones comunes para usar delegados en su código para evitar el acoplamiento seguro entre sus componentes.
ms.date: 06/20/2016
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.openlocfilehash: 22ab88e5b139381e3a8921baa20df035f1405146
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223689"
---
# <a name="common-patterns-for-delegates"></a>Patrones comunes para delegados

[Anterior](delegates-strongly-typed.md)

Los delegados proporcionan un mecanismo que permite que los diseños de software supongan un acoplamiento mínimo entre los componentes.

Un ejemplo excelente de este tipo de diseño es LINQ. El patrón de expresión de consulta LINQ se basa en los delegados para todas sus características. Considere este ejemplo sencillo:

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

Se filtra la secuencia solo de los números que son inferiores al valor 10.
El método `Where` usa un delegado que determina qué elementos de una secuencia pasan el filtro. Cuando crea una consulta LINQ, proporciona la implementación del delegado para este fin específico.

El prototipo para el método Where es:

```csharp
public static IEnumerable<TSource> Where<TSource> (this IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

Este ejemplo se repite con todos los métodos que forman parte de LINQ. Todos se basan en delegados para el código que administra la consulta específica. Este modelo de diseño de API es muy eficaz para obtener información y comprender.

En este ejemplo sencillo se ilustra cómo los delegados necesitan muy poco acoplamiento entre componentes. No necesita crear una clase que derive de una clase base determinada. No necesita implementar una interfaz específica.
El único requisito consiste en proporcionar la implementación de un método que sea fundamental para la tarea que nos ocupa.

## <a name="building-your-own-components-with-delegates"></a>Crear sus propios componentes con delegados

Vamos a aprovechar ese ejemplo creando un componente con un diseño que se base en delegados.

Vamos a definir un componente que pueda usarse para mensajes de registro en un sistema grande. Los componentes de la biblioteca pueden usarse en muchos entornos diferentes, en varias plataformas diferentes. Existen muchas características comunes en el componente que administra los registros. Necesitará aceptar mensajes de cualquier componente del sistema. Esos mensajes tendrán diferentes prioridades, que el componente principal puede administrar. Los mensajes deben tener marcas de tiempo en su forma de archivado final. Para escenarios más avanzados, puede filtrar mensajes por el componente de origen.

Hay un aspecto de la característica que cambiará a menudo: el lugar donde se escriben los mensajes. En algunos entornos, pueden escribirse en la consola de errores. En otros, en un archivo. Otras posibilidades incluyen el almacenamiento de bases de datos, los registros de eventos del sistema operativo u otro almacenamiento de documentos.

También hay combinaciones de salida que pueden usarse en escenarios diferentes. Puede que quiera escribir mensajes en la consola y en un archivo.

Un diseño basado en delegados proporcionará una gran flexibilidad y facilitará la compatibilidad de mecanismos de almacenamiento que pueden agregarse en el futuro.

Con este diseño, el componente de registro principal puede ser una clase no virtual, incluso sellada. Puede conectar cualquier conjunto de delegados para escribir los mensajes en un medio de almacenamiento diferente. La compatibilidad integrada para los delegados multidifusión facilita la compatibilidad de escenarios donde los mensajes deben escribirse en varias ubicaciones (un archivo y una consola).

## <a name="a-first-implementation"></a>Una primera implementación

Comencemos poco a poco: la implementación inicial aceptará mensajes nuevos y los escribirá con cualquier delegado asociado. Puede comenzar con un delegado que escriba mensajes en la consola.

[!code-csharp[LoggerImplementation](../../samples/snippets/csharp/delegates-and-events/Logger.cs#FirstImplementation "A first Logger implementation.")]

La clase estática anterior es lo más sencillo que puede funcionar. Necesitamos escribir solo la implementación para el método que escribe mensajes en la consola:

[!code-csharp[LogToConsole](../../samples/snippets/csharp/delegates-and-events/LoggingMethods.cs#LogToConsole "A Console logger.")]

Por último, necesita conectar el delegado asociándolo al delegado WriteMessage que se declara en el registrador:

[!code-csharp[ConnectDelegate](../../samples/snippets/csharp/delegates-and-events/Program.cs#ConnectDelegate "Connect to the delegate")]

## <a name="practices"></a>Procedimientos

Hasta ahora nuestro ejemplo es bastante sencillo, pero sigue mostrando algunas instrucciones importantes para los diseños que involucran a los delegados.

Con los tipos de delegado definidos en Core Framework es más sencillo para los usuarios trabajar con los delegados. No necesita definir tipos nuevos, y los desarrolladores que usen su biblioteca no necesitan aprender nuevos tipos de delegado especializados.

Las interfaces que se han usado son tan mínimas y flexibles como es posible: para crear un registrador de salida nuevo, debe crear un método. Ese método puede ser un método estático o un método de instancia. Puede tener cualquier acceso.

## <a name="formatting-output"></a>Resultados con formato

Vamos a hacer esta primera versión un poco más sólida y, después, empezaremos a crear otros mecanismos de registro.

Después, vamos a agregar algunos argumentos al método `LogMessage()` de manera que su clase de registro cree más mensajes estructurados:

[!code-csharp[Severity](../../samples/snippets/csharp/delegates-and-events/Logger.cs#Severity "Define severities")]
[!code-csharp[NextLogger](../../samples/snippets/csharp/delegates-and-events/Logger.cs#LoggerTwo "Refine the Logger")]

A continuación, vamos a usar ese argumento `Severity` para filtrar los mensajes que se envían a la salida del registro.

[!code-csharp[FinalLogger](../../samples/snippets/csharp/delegates-and-events/Logger.cs#LoggerFinal "Finish the Logger")]

## <a name="practices"></a>Procedimientos

Ha agregado características nuevas a la infraestructura de registro. Como el componente del registrador se acopla débilmente a cualquier mecanismo de salida, estas características nuevas pueden agregarse sin afectar a ningún código que implementa el delegado del registrador.

A medida que siga creando esto, verá más ejemplos de cómo este acoplamiento débil permite una mayor flexibilidad en la actualización de las partes del sitio sin que haya cambios en otras ubicaciones. De hecho, en una aplicación más grande, las clases de salida del registrador pueden estar en un ensamblado diferente, y ni siquiera necesitan volver a crearse.

## <a name="building-a-second-output-engine"></a>Crear un segundo motor de salida

El componente de registro se está desarrollando correctamente. Vamos a agregar un motor de salida más que registre mensajes en un archivo. Este será un motor de salida ligeramente más involucrado. Será una clase que encapsule las operaciones de archivo y garantice que el archivo esté siempre cerrado después de cada escritura. Eso garantiza que todos los datos se vacíen en el disco después de que se genere cada mensaje.

Aquí se muestra ese registrador basado en archivos:

[!code-csharp[FileLogger](../../samples/snippets/csharp/delegates-and-events/FileLogger.cs#FileLogger "Log to files")]

Una vez que haya creado esta clase, puede inicializarla y esta asocia su método LogMessage al componente de registrador:

[!code-csharp[FileLogger](../../samples/snippets/csharp/delegates-and-events/Program.cs#FileLogger "Log to files")]

Estos dos no son mutuamente exclusivos. Puede asociar ambos métodos de registro y generar mensajes en la consola y en un archivo:

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LoggingMethods.LogToConsole; // LoggingMethods is the static class we utilized earlier
```

Después, incluso en la misma aplicación, puede quitar uno de los delegados sin ocasionar ningún otro problema en el sistema:

```csharp
Logger.WriteMessage -= LoggingMethods.LogToConsole;
```

## <a name="practices"></a>Procedimientos

Ahora, ha agregado un segundo controlador de salida para el subsistema de registro.
Este necesita un poco más de infraestructura para admitir correctamente el sistema de archivos. El delegado es un método de instancia. También es un método privado.
No existe ninguna necesidad de una mayor accesibilidad porque la infraestructura de delegado puede conectarse a los delegados.

En segundo lugar, el diseño basado en delegados permite varios métodos de salida sin ningún código adicional. No necesita crear ninguna infraestructura adicional para admitir varios métodos de salida. Simplemente se convierten en otro método en la lista de invocación.

Preste una atención especial al código del método de salida de registro de archivo. Se codifica para garantizar que no produce ninguna excepción. Aunque esto no siempre es estrictamente necesario, a menudo es un buen procedimiento. Si cualquiera de los métodos de delegado produce una excepción, los delegados restantes que se encuentran en la invocación no se invocarán.

Como última observación, el registrador de archivos debe administrar sus recursos abriendo y cerrando el archivo en cada mensaje de registro. Puede optar por mantener el archivo abierto e implementar IDisposable para cerrar el archivo cuando termine.
Cualquier método tiene sus ventajas e inconvenientes. Ambos crean un poco más de acoplamiento entre las clases.

Ningún código de la clase de registrador necesitará actualizarse para admitir cualquier escenario.

## <a name="handling-null-delegates"></a>Control de delegados NULL

Por último, vamos a actualizar el método LogMessage de manera que sea sólido para esos casos en los que no se selecciona ningún mecanismo de salida. La implementación actual producirá `NullReferenceException` cuando el delegado `WriteMessage` no tenga una lista de invocación asociada.
Puede que prefiera un diseño que continúe silenciosamente cuando no se haya asociado ningún método. Esto es sencillo con el operador condicional NULL, combinado con el método `Delegate.Invoke()`:

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

El operador condicional NULL (`?.`) crea un cortocircuito cuando el operando izquierdo (`WriteMessage` en este caso) es NULL, lo que significa que no se realiza ningún intento para registrar un mensaje.

No encontrará el método `Invoke()` en la documentación de `System.Delegate` o `System.MulticastDelegate`. El compilador genera un método `Invoke` con seguridad de tipos para cualquier tipo de delegado declarado. En este ejemplo, eso significa que `Invoke` toma un solo argumento `string` y tiene un tipo de valor devuelto void.

## <a name="summary-of-practices"></a>Resumen de procedimientos

Ha observado los comienzos de un componente de registro que puede expandirse con otros sistemas de escritura y otras características. Con el uso de delegados en el diseño, estos componentes diferentes están acoplados muy débilmente. Esto ofrece varias ventajas. Es muy sencillo crear mecanismos de salida nuevos y asociarlos al sistema. Estos otros mecanismos solo necesitan un método: el método que escribe el mensaje de registro. Es un diseño que es muy resistente cuando se agregan características nuevas. El contrato que se necesita para cualquier sistema de escritura es implementar un método. Ese método puede ser un método estático o de instancia. Puede ser público, privado o de cualquier otro acceso legal.

La clase de registrador puede realizar cualquier número de cambios o mejoras sin producir cambios importantes. Como cualquier clase, no puede modificar la API pública sin el riesgo de que se produzcan cambios importantes. Pero, como el acoplamiento entre el registrador y cualquier motor de salida se realiza solo mediante el delegado, ningún otro tipo (como interfaces o clases base) está involucrado. El acoplamiento es lo más pequeño posible.

[Siguiente](events-overview.md)
