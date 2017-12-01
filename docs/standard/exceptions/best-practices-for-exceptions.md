---
title: Procedimientos recomendados para excepciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
caps.latest.revision: "28"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87f9287c3714416ee5d6b63f3c9db311bb97b131
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2017
---
# <a name="best-practices-for-exceptions"></a>Procedimientos recomendados para excepciones

Una aplicación diseñada correctamente controla las excepciones y los errores para evitar que se bloquee. En este artículo se describen los procedimientos recomendados para controlar y crear excepciones.

## <a name="use-trycatchfinally-blocks"></a>Uso de bloques Try/Catch/Finally

Use bloques de código `try`/`catch`/`finally` que podría generar una excepción. 

Ordene siempre las excepciones de los bloques `catch` de la más específica a la menos.

Use un bloque `finally` para limpiar los recursos, tanto si puede recuperarlos como si no.

## <a name="handle-common-conditions-without-throwing-exceptions"></a>Administrar condiciones comunes sin iniciar excepciones

Para las condiciones con probabilidad de producirse, pero que podrían desencadenar una excepción, considere la posibilidad de controlarlas de forma que se evite la excepción. Por ejemplo, si intenta se cerrar una conexión que ya está cerrada, obtendrá `InvalidOperationException`. Se puede evitar mediante una instrucción `if` para comprobar el estado de conexión antes de intentar cerrarla.

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  

Si no comprueba el estado de la conexión antes de cerrar, se puede detectar la excepción `InvalidOperationException`.

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  

El método que se elija depende de la frecuencia con la que espera que se produzca el evento.

- Utilice el control de excepciones si el evento no se produce con frecuencia, es decir, si el evento es muy excepcional e indica un error (como un final de archivo inesperado). Cuando se usa el control de excepciones, se ejecuta menos código en condiciones normales.

- Compruebe condiciones de error en el código cuando el evento se produce con frecuencia y se puede considerar como parte de la ejecución normal. Cuando se buscan condiciones de error comunes, se ejecuta menos código porque se evitan excepciones.

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Diseñar clases para que se puedan evitar excepciones

Una clase puede proporcionar métodos o propiedades que permiten evitar realizar una llamada que desencadenaría una excepción. Por ejemplo, una clase <xref:System.IO.FileStream> proporciona métodos que ayudan a determinar si se ha alcanzado el final del archivo. Esto se puede usar para evitar la excepción que se inicia si se lee más allá del final del archivo. En el ejemplo siguiente se muestra cómo leer hasta el final de un archivo sin desencadenar una excepción.

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  

Otro modo de evitar excepciones es devolver NULL para los casos de errores muy frecuentes en lugar de iniciar una excepción. Un caso de error muy común se puede considerar como un flujo de control normal. Al devolver un valor null en estos casos, se minimiza el impacto en el rendimiento de una aplicación.

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Iniciar excepciones en lugar de devolver un código de error

Las excepciones garantizan que los errores no pasen desapercibidos porque la llamada al código no compruebe un código de retorno. 

## <a name="use-the-predefined-net-exception-types"></a>Uso de los tipos de excepción predefinidos de .NET

Solo se deben introducir nuevas clases de excepción si no se puede aplicar ningún tipo predefinido. Por ejemplo:

- Inicie una excepción <xref:System.InvalidOperationException> si un conjunto de propiedades o una llamada a un método no resultan apropiados de acuerdo con el estado actual del objeto.

- Inicie una excepción <xref:System.ArgumentException> o una de las clases predefinidas que derivan de <xref:System.ArgumentException> si se pasan parámetros no válidos.

## <a name="end-exception-class-names-with-the-word-exception"></a>Termine los nombres de clases de excepción con la palabra `Exception`

Cuando se necesite una excepción personalizada, debe ponerse el nombre apropiado y derivarla de la clase <xref:System.Exception>. Por ejemplo:

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  

## <a name="include-three-constructors-in-custom-exception-classes"></a>Incluir tres constructores en las clases de excepciones personalizadas

Use al menos tres constructores comunes al crear sus propias clases de excepción: el constructor predeterminado, un constructor que tome un mensaje de cadena y un constructor que tome un mensaje de cadena y una excepción interna.

* <xref:System.Exception.%23ctor>, que usa los valores predeterminados.
  
* <xref:System.Exception.%23ctor%28System.String%29>, que acepta un mensaje de cadena.  
  
* <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, que acepta un mensaje de cadena y una excepción interna.  
  
Por ejemplo, consulte [Cómo: Crear excepciones definidas por el usuario](how-to-create-user-defined-exceptions.md).

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Asegúrese de que los datos de excepción estén disponibles cuando el código se ejecute de forma remota

Cuando cree excepciones definidas por el usuario, debe garantizar que los metadatos de las excepciones están disponibles para el código que se ejecute de forma remota. 

Por ejemplo, en las implementaciones de .NET que admita los dominios de aplicación, pueden producirse excepciones entre dominios de aplicación. Por ejemplo, supongamos que el dominio de aplicación A crea el dominio de aplicación B, que ejecuta código que inicia una excepción. Para que el dominio de aplicación A detecte y controle la excepción correctamente, debe poder encontrar el ensamblado que contiene la excepción iniciada por el dominio de aplicación B. Si el dominio de aplicación B inicia una excepción contenida en un ensamblado en su base de aplicación pero no en la base de aplicación del dominio de aplicación A, el dominio de aplicación A no podrá encontrar la excepción y common language runtime iniciará una excepción de <xref:System.IO.FileNotFoundException>. Para evitar esta situación, puede implementar el ensamblado que contiene la información de la excepción de dos maneras:

- Ponga el ensamblado en una base de aplicación compartida por los dos dominios de aplicación.

    \- o -

- Si los dominios no comparten una base de aplicación común, firme el ensamblado que contiene la información de la excepción con un nombre seguro e impleméntelo en la caché global de ensamblados.

## <a name="include-a-localized-description-string-in-every-exception"></a>Incluir una cadena descriptiva localizada en todas las excepciones

El mensaje de error que ve el usuario deriva de la cadena descriptiva de la excepción que se inició y no del nombre de la clase de excepción.

## <a name="use-grammatically-correct-error-messages"></a>Usar mensajes de error gramaticalmente correctos

Escriba frases claras e incluya puntuación final. Cara oración de una cadena descriptiva de una excepción debe acabar con un punto. Por ejemplo, "la tabla del registro se ha desbordado." sería una cadena de descripción adecuada.

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>En excepciones personalizadas, proporcione propiedades adicionales según sea necesario

Únicamente proporcione información adicional para una excepción (además de la cadena descriptiva) si hay un escenario de programación en que dicha información sea útil. Por ejemplo, <xref:System.IO.FileNotFoundException> proporciona la propiedad <xref:System.IO.FileNotFoundException.FileName>.

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Colocar instrucciones de iniciación para que el seguimiento de la pila sea útil

El seguimiento de pila comienza en la instrucción en que se produce la excepción y termina en la instrucción `catch` que detecta la excepción.

## <a name="use-exception-builder-methods"></a>Usar métodos de generador de excepciones

Es habitual que una clase produzca la misma excepción desde distintos lugares de su implementación. Para evitar el exceso de código, use métodos auxiliares que creen la excepción y la devuelvan. Por ejemplo:

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
En algunos casos, es más apropiado usar el constructor de excepciones para generar la excepción. Un ejemplo es una clase de excepción globales, como <xref:System.ArgumentException>.

## <a name="clean-up-intermediate-results-when-throwing-an-exception"></a>Eliminar los resultados intermedios cuando se inicie una excepción

Los autores de llamadas deben poder asumir que no se producen efectos no deseados cuando se produce una excepción desde un método. Por ejemplo, si tiene código que transfiere dinero mediante la retirada de una cuenta y el depósito en otra, y se inicia una excepción mientras se ejecuta el depósito, no quiere que la retirada siga siendo efectiva.

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

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

Este ejemplo muestra el uso de `throw` para volver a iniciar la excepción original, que puede facilitar a los autores de llamada ver la causa del problema real sin tener que examinar la propiedad <xref:System.Exception.InnerException>. Como alternativa se puede iniciar una nueva excepción e incluir la excepción original como excepción interna:

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a>Vea también  
[Excepciones](index.md)
