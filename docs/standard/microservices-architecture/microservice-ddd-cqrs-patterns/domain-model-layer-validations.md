---
title: Diseñar las validaciones en el nivel de modelo de dominio
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Diseñar las validaciones en el nivel de modelo de dominio
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ce3cb0c79cbd492224ce1d4ecb25cd02062f11cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="designing-validations-in-the-domain-model-layer"></a>Diseñar las validaciones en el nivel de modelo de dominio

En el diseño guiado por el dominio (DDD), las reglas de validación se pueden considerar invariables. La responsabilidad principal de un agregado es aplicar invariables en todos los cambios de estado para todas las entidades de ese agregado.

Las entidades de dominio siempre deben ser entidades válidas. Hay un número determinado de invariables para un objeto que siempre deben ser verdaderas. Por ejemplo, un objeto de un elemento de pedido siempre debe tener una cantidad que debe constar de un entero positivo, un nombre de artículo y un precio. Por lo tanto, la aplicación de invariables es responsabilidad de las entidades de dominio (en especial de la raíz agregada) y un objeto de entidad no debería poder existir si no es válido. Las reglas invariables se expresan como contratos y, si se infringen, se generan excepciones o notificaciones.

El razonamiento es que se producen muchos errores porque los objetos tienen un estado que no deberían tener nunca. A continuación se muestra una buena explicación de Greg Young, publicada en un [debate en línea](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

Ahora imaginémonos que tenemos un SendUserCreationEmailService que toma un UserProfile… ¿Cómo podemos justificar en ese servicio que Name no es nulo? ¿Lo volvemos a comprobar? O lo que es más probable: no se molesta en comprobarlo y "espera lo mejor" (espera que alguien se haya molestado en validarlo antes de enviárselo). Por supuesto, si usamos TDD, una de las primeras pruebas que deberíamos escribir es que si, al enviar un cliente con un nombre nulo, se generaría un error. Pero una vez que comenzamos a escribir estos tipos de pruebas una y otra vez nos damos cuenta de que… "Espera, si no hubiéramos dejado que Name fuera nulo, no tendríamos todas estas pruebas".

## <a name="implementing-validations-in-the-domain-model-layer"></a>Implementar las validaciones en el nivel de modelo de dominio

Las validaciones se suelen implementar en constructores de entidad de dominio o en métodos que pueden actualizar la entidad. Hay varias maneras de implementar las validaciones, como la comprobación de los datos y la generación de excepciones si se produce un error en la validación. También hay patrones más avanzados, como el uso del patrón de especificación para las validaciones y el patrón de notificación para devolver una colección de errores en lugar de devolver una excepción para cada validación mientras se produce.

### <a name="validating-conditions-and-throwing-exceptions"></a>Validar condiciones y generar excepciones

En el siguiente ejemplo de código se muestra el método de validación más sencillo en una entidad de dominio mediante la generación de una excepción. En la tabla de referencias que encontrará al final de esta sección puede ver vínculos a implementaciones más avanzadas según los patrones que hemos analizado anteriormente.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

Un ejemplo mejor demostraría la necesidad de garantizar que el estado interno no varió o que se produjeron todas las mutaciones de un método. Por ejemplo, la siguiente implementación dejaría el objeto en un estado no válido:

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

Si el valor del estado no es válido, la primera línea de dirección y la ciudad ya se han cambiado, lo cual podría invalidar la dirección.

Se puede aplicar un enfoque similar en el constructor de la entidad, generando una excepción para garantizar que la entidad sea válida una vez creada.

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>Usar atributos de validación en el modelo en función de las anotaciones de datos

Otro enfoque consiste en usar atributos de validación en función de las anotaciones de datos. Los atributos de validación permiten configurar la validación del modelo, que conceptualmente es similar a la validación en campos de tablas de base de datos. Esto incluye las restricciones, como la asignación de tipos de datos o los campos obligatorios. Entre otros tipos de validación se encuentran el de aplicar patrones a los datos para aplicar reglas de negocio, como números de tarjetas de crédito, números de teléfono o direcciones de correo electrónico. Los atributos de validación facilitan la aplicación de requisitos.

Pero, como se muestra en el código siguiente, este enfoque resultaría demasiado invasivo en un modelo DDD, porque toma una dependencia en ModelState.IsValid de Microsoft.AspNetCore.Mvc.ModelState, al que se debe llamar desde los controladores de MVC. La validación del modelo tiene lugar antes de cada acción de controlador que se invoca, y es responsabilidad del método del controlador inspeccionar el resultado de la llamada a ModelState.IsValid y reaccionar de manera apropiada. La decisión de usarlo depende del grado de asociación que quiere que tenga el modelo con esa infraestructura.

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

Pero desde la óptica del DDD, el modelo de dominio se ajusta mejor con el uso de excepciones en los métodos de comportamiento de la entidad o con la implementación de los patrones de especificación y notificación para aplicar reglas de validación. Los marcos de validación, como las anotaciones de datos en ASP.NET Core, o cualquier otro marco de validación como FluentValidation incluyen un requisito para invocar el marco de trabajo de la aplicación. Por ejemplo, al llamar al método ModelState.IsValid en las anotaciones de datos, debe invocar controladores de ASP.NET.

Puede resultar lógico usar anotaciones de datos en el nivel de aplicación en las clases ViewModel (en lugar de hacerlo en las entidades de dominio) que aceptarán la entrada a fin de permitirlas para la validación del modelo en la capa de la interfaz de usuario, pero no se debería hacer en la exclusión de validación dentro del modelo de dominio.

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Validar entidades implementando el patrón de especificación y el patrón de notificación

Por último, un enfoque más elaborado para implementar validaciones en el modelo de dominio consiste en implementar el patrón de especificación junto con el patrón de notificación, como se explica en algunos de los recursos adicionales que se muestran más adelante.

Merece la pena mencionar que también se puede usar solo uno de estos patrones (por ejemplo, validándolo manualmente con instrucciones de control, pero usando el patrón de notificación para apilar y devolver una lista de errores de validación).

### <a name="using-deferred-validation-in-the-domain"></a>Usar la validación diferida en el dominio

Hay varios métodos para tratar las validaciones diferidas en el dominio. En su libro [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) (Implementación del diseño guiado por el dominio), Vaughn Vernon habla de ellos en la sección sobre la validación.

### <a name="two-step-validation"></a>Validación en dos pasos

Plantéese también usar la validación en dos pasos. Use la validación de nivel de campo en los objetos de transferencia de datos (DTO) de comandos y la validación de nivel de dominio dentro de las entidades. Para ello, puede devolver un objeto de resultado en vez de excepciones para que resulte más fácil tratar los errores de validación.

Si usa la validación de campos con anotaciones de datos, por ejemplo, no se duplica la definición de validación. Pero la ejecución puede ser del lado servidor y del lado cliente en el caso de los DTO (comandos y ViewModels, por ejemplo).

## <a name="additional-resources"></a>Recursos adicionales

-   **Rachel Appel. Introducción a la validación de modelos en ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson. Adding validation (Adición de validación)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler. Replacing Throwing Exceptions with Notification in Validations (Reemplazar el inicio de excepciones por notificaciones en validaciones)**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **Specification and Notification Patterns (Patrones de especificación y notificación)**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **Lev Gorodinski. Validation in Domain-Driven Design (DDD) (Validación en diseños guiados por dominio)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin Jack. Domain Model Validation (Validación de modelos de dominio)**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard. Validation in a DDD world (Validación en un mundo de diseños guiados por dominio)**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[Anterior] (enumeration-classes-over-enum-types.md) [Siguiente] (client-side-validation.md)
