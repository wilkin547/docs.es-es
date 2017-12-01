---
title: "Diseñar las validaciones en el nivel de modelo de dominio"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar las validaciones en el nivel de modelo de dominio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a>Diseñar las validaciones en el nivel de modelo de dominio

En el DDD, reglas de validación pueden considerarse como invariables. La responsabilidad principal de un agregado es exigir las invariantes en todos los cambios de estado para todas las entidades dentro de ese agregado.

Las entidades de dominio deben ser siempre entidades válidas. Hay un número determinado de invariables para un objeto que siempre debe ser true. Por ejemplo, un objeto de elemento de pedido siempre debe tener una cantidad que debe ser un entero positivo, además de un nombre de artículo y precio. Por lo tanto, el cumplimiento de las invariantes es responsabilidad de las entidades de dominio (especialmente tratándose de la raíz agregada) y un objeto de entidad no debe ser capaz de existir sin necesidad de ser válido. Reglas invariables simplemente se expresan como contratos y las excepciones o las notificaciones se generan cuando se infringen.

El razonamiento es que se producen muchos errores porque los objetos están en un estado en que nunca deberían haber estado. La siguiente es una buena explicación de Greg Young en un [discusión en línea](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

Vamos a proponer que ahora tenemos un SendUserCreationEmailService que toma UserProfile... ¿cómo podemos se racionalizar en ese servicio que no sea nulo nombre? ¿Se comprueba lo nuevo? O con mayor probabilidad... simplemente no pierda tiempo para comprobar y "esperar para obtener la mejor": esperar a que alguien obtienes para validar antes de enviarlo a usted. Por supuesto, utilizar TDD una de las primeras pruebas que se deben escribir es que si se envían a un cliente con un nombre nulo que debe generar un error. Pero una vez comience a escribir estos tipos de pruebas y otra vez sabemos... "esperar si nunca se permite nombre para convertirse en null no tenemos todas estas pruebas"

## <a name="implementing-validations-in-the-domain-model-layer"></a>Implementación de validaciones en el nivel de modelo de dominio

Validaciones normalmente se implementan en los constructores de la entidad de dominio o en los métodos que pueden actualizar la entidad. Hay varias maneras de implementar las validaciones, como datos de comprobación y generación de excepciones si se produce un error en la validación. También hay patrones más avanzadas, como utilizar el modelo de especificación para validaciones y el patrón de notificación para devolver una colección de errores en lugar de devolver una excepción para cada validación mientras se ejecuta.

### <a name="validating-conditions-and-throwing-exceptions"></a>Validar las condiciones y producir excepciones

En el ejemplo de código siguiente se muestra el método más sencillo para la validación en una entidad del dominio lanza una excepción. En la tabla de referencias al final de esta sección puede ver vínculos a las implementaciones más avanzadas según los patrones que hemos analizado anteriormente.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

Un ejemplo mejor sería demuestra que era necesario para asegurarse de que el estado interno no cambió o que se ha producido la de las mutaciones para un método. Por ejemplo, la siguiente implementación dejaría el objeto en un estado no válido:

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

Si el valor del estado no es válido, la primera línea de dirección y la ciudad ya han cambiado. La dirección que puede que no sean válidos.

Un enfoque similar puede usarse en el constructor de la entidad, cuando se genera una excepción para asegurarse de que la entidad es válido una vez que se crea.

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>Uso de atributos de validación en el modelo en función de las anotaciones de datos

Otro enfoque consiste en utilizar atributos de validación en función de las anotaciones de datos. Atributos de validación proporcionan una manera de configurar la validación del modelo, que es similar conceptualmente a la validación en los campos de tablas de base de datos. Esto incluye las restricciones como la asignación de tipos de datos o campos obligatorios. Otros tipos de validación aplicar patrones a datos que se va a aplicar las reglas de negocios, como un número de tarjeta de crédito, número de teléfono o dirección de correo electrónico. Atributos de validación facilitan la tarea exigir requisitos.

Sin embargo, como se muestra en el código siguiente, este enfoque sería demasiado intrusivo en un modelo DDD, porque toma una dependencia en ModelState.IsValid de Microsoft.AspNetCore.Mvc.ModelState, que se debe llamar desde los controladores MVC. La validación del modelo se produce antes de cada acción de controlador que se invoca y es responsabilidad del método de controlador para inspeccionar el resultado de llamada ModelState.IsValid y reaccionar de manera apropiada. La decisión de usar depende de cómo estrechamente desea que el modelo con el que la infraestructura.

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

Sin embargo, desde un punto de vista DDD, el modelo de dominio es mejor guardar eficiente con el uso de excepciones en métodos de comportamiento de la entidad, o mediante la implementación de los patrones de especificación y notificación para exigir reglas de validación. Marcos de validación como anotaciones de datos en ASP.NET Core o ningún otro marco de validación como FluentValidation llevan un requisito para invocar el marco de aplicación. Por ejemplo, al llamar al método ModelState.IsValid en las anotaciones de datos, debe invocar controladores de ASP.NET.

Puede tener sentido usar anotaciones de datos en el nivel de aplicación en las clases de ViewModel (en lugar de las entidades de dominio) que acepta datos proporcionados, para permitir la validación del modelo dentro de la capa de interfaz de usuario. Sin embargo, esto no debería realizarse en la exclusión de validación en el modelo de dominio.

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Validar entidades al implementar el patrón de especificación y la notificación

Por último, un enfoque más elaborado para implementar las validaciones en el modelo de dominio es al implementar el patrón de especificación junto con el patrón de notificación, como se explica en algunos de los recursos adicionales que se muestra más adelante.

Merece la pena mencionar que también puede usar solo uno de esos patrones, por ejemplo, validación manual con las instrucciones de control, pero utilizando el modelo de notificación de la pila y devolver una lista de errores de validación.

### <a name="using-deferred-validation-in-the-domain"></a>Usar validación diferida en el dominio

Hay varios enfoques para tratar con aplazada validaciones en el dominio. En su libro [Implementing Domain-Driven diseño](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon describe estas opciones en la sección sobre la validación.

### <a name="two-step-validation"></a>Validación de dos pasos

Considere también la validación de dos pasos. Utilizar la validación de nivel de campo en la validación de nivel de dominio dentro de las entidades y los objetos de transferencia de comandos datos (dto). Para ello, puede devolver un objeto de resultado en su lugar, las excepciones para que resulten más fáciles de tratar los errores de validación.

Usar la validación de campos con las anotaciones de datos, por ejemplo, no duplica la definición de validación. Sin embargo, la ejecución, puede ser servidor y cliente en el caso de Dto (comandos y ViewModels, por ejemplo).

## <a name="additional-resources"></a>Recursos adicionales

-   **Rachel Appel. Introducción a la validación del modelo en MVC de ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson. Agregar validación**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler. Reemplazar producir excepciones con notificación de validaciones**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **Especificación y patrones de notificación**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **Lev Gorodinski. Validación de diseño basado en dominio (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin conector. Validación del modelo de dominio**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard. Validación en un mundo DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[Anterior] (enumeración-clases-over-enum-types.md) [siguiente] (validation.md de lado de cliente)
