---
title: Procedimientos recomendados para excepciones - .NET
description: Obtenga más información sobre los procedimientos recomendados para las excepciones, como el uso de try/catch/finally, el control de condiciones habituales sin excepciones y el uso de tipos de excepción de .NET predefinidos.
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 90dda00acd32852b032fc383580c5f34022ec9b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447100"
---
# <a name="best-practices-for-exceptions"></a>Procedimientos recomendados para excepciones

Una aplicación diseñada correctamente controla las excepciones y los errores para evitar que se bloquee. En este artículo se describen los procedimientos recomendados para controlar y crear excepciones.

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a>Uso de bloques try/catch/finally para recuperarse de errores o liberar recursos

Use bloques `try`/`catch` alrededor del código que podría generar una excepción ***y*** su código podrá recuperarse de una excepción. Ordene siempre las excepciones de los bloques `catch` de la más derivada a la menos. Todas las excepciones se derivan de <xref:System.Exception>. Las excepciones más derivadas no las controla una cláusula catch que está precedida por una cláusula catch para una clase de excepción base. Cuando el código no puede recuperarse de una excepción, no capture esa excepción. Habilite los métodos más arriba en la pila de llamadas para recuperarse si es posible.

Limpie los recursos asignados con instrucciones `using` o bloques `finally`. Dé prioridad a las instrucciones `using` para limpiar automáticamente los recursos cuando se produzcan excepciones. Use bloques `finally` para limpiar los recursos que no implementan <xref:System.IDisposable>. El código de una cláusula `finally` casi siempre se ejecuta incluso cuando se producen excepciones.

## <a name="handle-common-conditions-without-throwing-exceptions"></a>Administrar condiciones comunes sin iniciar excepciones

Para las condiciones con probabilidad de producirse, pero que podrían desencadenar una excepción, considere la posibilidad de controlarlas de forma que se evite la excepción. Por ejemplo, si intenta se cerrar una conexión que ya está cerrada, obtendrá `InvalidOperationException`. Se puede evitar mediante una instrucción `if` para comprobar el estado de conexión antes de intentar cerrarla.

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

Si no comprueba el estado de la conexión antes de cerrar, se puede detectar la excepción `InvalidOperationException`.

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

El método que se elija depende de la frecuencia con la que espera que se produzca el evento.

- Utilice el control de excepciones si el evento no se produce con frecuencia, es decir, si el evento es muy excepcional e indica un error (como un final de archivo inesperado). Cuando se usa el control de excepciones, se ejecuta menos código en condiciones normales.

- Compruebe condiciones de error en el código cuando el evento se produce con frecuencia y se puede considerar como parte de la ejecución normal. Cuando se buscan condiciones de error comunes, se ejecuta menos código porque se evitan excepciones.

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Diseñar clases para que se puedan evitar excepciones

Una clase puede proporcionar métodos o propiedades que permiten evitar realizar una llamada que desencadenaría una excepción. Por ejemplo, una clase <xref:System.IO.FileStream> proporciona métodos que ayudan a determinar si se ha alcanzado el final del archivo. Esto se puede usar para evitar la excepción que se inicia si se lee más allá del final del archivo. En el ejemplo siguiente se muestra cómo leer hasta el final de un archivo sin desencadenar una excepción.

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

Otro modo de evitar excepciones es devolver un valor NULL (o el valor predeterminado) para los casos de errores muy frecuentes en lugar de iniciar una excepción. Un caso de error muy común se puede considerar como un flujo de control normal. Al devolver un valor NULL en estos casos, se minimiza el impacto en el rendimiento de una aplicación.

Para los tipos de valores, el uso de `Nullable<T>` o de valores predeterminados como indicador de error es algo que se debe tener en cuenta para la aplicación en particular. Al utilizar `Nullable<Guid>`, `default` se convierte en `null` en lugar de `Guid.Empty`. Algunas veces, agregar `Nullable<T>` puede aclarar cuando un valor está presente o ausente. Otras veces, agregar `Nullable<T>` puede crear casos adicionales para comprobar que no son necesarios, y solo sirven para crear posibles orígenes de errores.

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Iniciar excepciones en lugar de devolver un código de error

Las excepciones garantizan que los errores no pasen desapercibidos porque la llamada al código no compruebe un código de retorno.

## <a name="use-the-predefined-net-exception-types"></a>Uso de los tipos de excepción predefinidos de .NET

Solo se deben introducir nuevas clases de excepción si no se puede aplicar ningún tipo predefinido. Por ejemplo:

- Inicie una excepción <xref:System.InvalidOperationException> si un conjunto de propiedades o una llamada a un método no resultan apropiados de acuerdo con el estado actual del objeto.

- Inicie una excepción <xref:System.ArgumentException> o una de las clases predefinidas que derivan de <xref:System.ArgumentException> si se pasan parámetros no válidos.

## <a name="end-exception-class-names-with-the-word-exception"></a>Termine los nombres de clases de excepción con la palabra `Exception`

Cuando se necesite una excepción personalizada, debe ponerse el nombre apropiado y derivarla de la clase <xref:System.Exception>. Por ejemplo:

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a>Incluir tres constructores en las clases de excepciones personalizadas

Use al menos tres constructores comunes al crear sus propias clases de excepción: el constructor sin parámetros, un constructor que tome un mensaje de cadena y un constructor que tome un mensaje de cadena y una excepción interna.

- <xref:System.Exception.%23ctor>, que utiliza valores predeterminados.

- <xref:System.Exception.%23ctor%28System.String%29>, que acepta un mensaje de cadena.

- <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, que acepta un mensaje de cadena y una excepción interna.

Como ejemplo, vea [Cómo: Crear excepciones definidas por el usuario](how-to-create-user-defined-exceptions.md).

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Asegúrese de que los datos de excepción estén disponibles cuando el código se ejecute de forma remota

Cuando cree excepciones definidas por el usuario, debe garantizar que los metadatos de las excepciones están disponibles para el código que se ejecute de forma remota.

Por ejemplo, en las implementaciones de .NET que admiten los dominios de aplicación, pueden producirse excepciones entre dominios de aplicación. Por ejemplo, supongamos que el dominio de aplicación A crea el dominio de aplicación B, que ejecuta código que inicia una excepción. Para que el dominio de aplicación A detecte y controle la excepción correctamente, debe poder encontrar el ensamblado que contiene la excepción iniciada por el dominio de aplicación B. Si el dominio de aplicación B inicia una excepción contenida en un ensamblado en su base de aplicación pero no en la base de aplicación del dominio de aplicación A, el dominio de aplicación A no podrá encontrar la excepción y common language runtime iniciará una excepción de <xref:System.IO.FileNotFoundException>. Para evitar esta situación, puede implementar el ensamblado que contiene la información de la excepción de dos maneras:

- Ponga el ensamblado en una base de aplicación compartida por los dos dominios de aplicación.

    \- o -

- Si los dominios no comparten una base de aplicación común, firme el ensamblado que contiene la información de la excepción con un nombre seguro e impleméntelo en la caché global de ensamblados.

## <a name="use-grammatically-correct-error-messages"></a>Usar mensajes de error gramaticalmente correctos

Escriba frases claras e incluya puntuación final. Todas las oraciones de la cadena asignada a la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> deben terminar en punto. Por ejemplo, "la tabla del registro se ha desbordado". podría ser una cadena de mensaje adecuada.

## <a name="include-a-localized-string-message-in-every-exception"></a>Incluir un mensaje de cadena localizada en todas las excepciones

El mensaje de error que ve el usuario deriva de la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> de la excepción que se ha generado, y no del nombre de la clase de excepción. Normalmente, se asigna un valor a la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> pasando la cadena de mensaje al argumento `message` de un [constructor de excepciones](xref:System.Exception.%23ctor%2A).

Para las aplicaciones localizadas, debe proporcionar una cadena de mensaje localizada para todas las excepciones que la aplicación pueda desencadenar. Use archivos de recursos para proporcionar mensajes de error localizados. Para información sobre la localización de aplicaciones y la recuperación de cadenas localizadas, consulte los siguientes artículos:

- [Procedimientos: Creación de excepciones definidas por el usuario con mensajes de excepción localizados](how-to-create-localized-exception-messages.md)
- [Recursos de aplicaciones de escritorio](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>En excepciones personalizadas, proporcione propiedades adicionales según sea necesario

Únicamente proporcione información adicional para una excepción, además de la cadena del mensaje personalizado, si hay un escenario de programación en el que dicha información sea útil. Por ejemplo, <xref:System.IO.FileNotFoundException> proporciona la propiedad <xref:System.IO.FileNotFoundException.FileName>.

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Colocar instrucciones de iniciación para que el seguimiento de la pila sea útil

El seguimiento de pila comienza en la instrucción en que se produce la excepción y termina en la instrucción `catch` que detecta la excepción.

## <a name="use-exception-builder-methods"></a>Usar métodos de generador de excepciones

Es habitual que una clase produzca la misma excepción desde distintos lugares de su implementación. Para evitar el exceso de código, use métodos del asistente que creen la excepción y la devuelvan. Por ejemplo:

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

En algunos casos, es más apropiado usar el constructor de excepciones para generar la excepción. Un ejemplo es una clase de excepción global, como <xref:System.ArgumentException>.

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a>Restauración del estado cuando los métodos no se completan debido a excepciones

Los autores de llamadas deben poder asumir que no se producen efectos no deseados cuando se produce una excepción desde un método. Por ejemplo, si tiene código que transfiere dinero mediante la retirada de una cuenta y el depósito en otra, y se inicia una excepción mientras se ejecuta el depósito, no quiere que la retirada siga siendo efectiva.

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

El método anterior no produce ninguna excepción directamente, pero debe escribirse de forma defensiva para que, si se produce un error en la operación de depósito, se invierta la retirada.

Para controlar esta situación se puede detectar cualquier excepción iniciada por la transacción del depósito y revertir la retirada.

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

Este ejemplo muestra el uso de `throw` para volver a iniciar la excepción original, que puede facilitar a los autores de llamada ver la causa del problema real sin tener que examinar la propiedad <xref:System.Exception.InnerException>. Como alternativa se puede iniciar una nueva excepción e incluir la excepción original como excepción interna:

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
