---
title: Marcas de características
description: Implementar marcas de características en aplicaciones nativas en la nube que aprovechan App de Azure configuración
ms.date: 05/03/2020
ms.openlocfilehash: 72e1bfe777854a74fcac926811caf97e59986146
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83398324"
---
# <a name="feature-flags"></a>Marcas de características

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En el capítulo 1, afirmamos que la nube nativa es mucho más rápida y ágil. Los usuarios esperan una capacidad de respuesta rápida, características innovadoras y sin tiempo de inactividad. `Feature flags`son una técnica de implementación moderna que ayuda a aumentar la agilidad de las aplicaciones nativas en la nube. Permiten implementar nuevas características en un entorno de producción, pero restringen su disponibilidad. Con el gesto de un conmutador, puede activar una nueva característica para usuarios específicos sin necesidad de reiniciar la aplicación ni implementar código nuevo. Separan la versión de las nuevas características de la implementación del código.

Las marcas de características se basan en la lógica condicional que controla la visibilidad de la funcionalidad de los usuarios en tiempo de ejecución. En los sistemas modernos nativos en la nube, es habitual implementar nuevas características en producción pronto, pero probarlas con un público limitado. A medida que aumenta la confianza, la característica se puede implementar incrementalmente en audiencias más amplias.

Otros casos de uso de las marcas de características son:

- Restrinja la funcionalidad Premium a grupos de clientes específicos dispuestos a pagar mayores tarifas de suscripción.
- Estabilice un sistema mediante la desactivación rápida de una característica problemática, evitando los riesgos de una reversión o de una revisión inmediata.
- Deshabilite una característica opcional con un alto consumo de recursos durante períodos de uso máximo.
- Lleve `experimental feature releases` a los pequeños segmentos de usuario para validar la viabilidad y popularidad.

Las marcas de características también fomentan el `trunk-based` desarrollo. Es un modelo de bifurcación de control de código fuente en el que los desarrolladores colaboran en características de una sola rama. El enfoque minimiza el riesgo y la complejidad de combinar grandes cantidades de ramas de características de ejecución prolongada. Las características no estarán disponibles hasta que se activen.

## <a name="implementing-feature-flags"></a>Implementar marcas de características

En esencia, una marca de características es una referencia a un simple `decision object` . Devuelve un estado booleano de `on` o `off` . Normalmente, la marca contiene un bloque de código que encapsula una funcionalidad de característica. El estado de la marca determina si ese bloque de código se ejecuta para un usuario determinado. En la figura 10-11 se muestra la implementación de.

```c#
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

**Figura 10-11** : implementación de la marca de características simple.

Observe cómo este enfoque separa la lógica de decisión del código de la característica.

En el capítulo 1, analizamos el `Twelve-Factor App` . La guía recomienda mantener los valores de configuración externos del código ejecutable de la aplicación. Cuando sea necesario, la configuración se puede leer desde el origen externo. Los valores de configuración de marcas de características también deben ser independientes de su código base. Al externalizar la configuración de marca en un repositorio independiente, puede cambiar el estado de la marca sin modificar y volver a implementar la aplicación.

[App de Azure configuración](https://docs.microsoft.com/azure/azure-app-configuration/overview) proporciona un repositorio centralizado para las marcas de características. Con él, puede definir diferentes tipos de marcas de características y manipular sus Estados de forma rápida y confiable. Agregue las bibliotecas de cliente de configuración de aplicaciones a la aplicación para habilitar la funcionalidad de marca de características. Se admiten varias plataformas de lenguaje de programación.

Las marcas de características se pueden implementar fácilmente en un [servicio de ASP.net Core](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core). La instalación de las bibliotecas de administración de características de .NET y el proveedor de configuración de aplicaciones permiten agregar mediante declaración marcas de características al código. Habilitan `FeatureGate` atributos para que no tenga que escribir instrucciones if manualmente en el código base.

Una vez configurada en la clase startup, puede Agregar funcionalidad de marca de características en el nivel de controlador, acción o middleware. En la figura 10-12 se muestra la implementación de la acción y el controlador:

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public class ProductController : Controller
{
    ...
}
```

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public IActionResult UpdateProductStatus()
{
    return ObjectResult(ProductDto);
}
```

**Figura 10-12** : implementación de la marca de características en un controlador y una acción.

Si una marca de características está deshabilitada, el usuario recibirá un código de estado 404 (no encontrado) sin cuerpo de respuesta.

Las marcas de características también se pueden insertar directamente en clases de C#. En la figura 10-13 se muestra la inyección de marcas de características:

```c#
public class ProductController : Controller
{
    private readonly IFeatureManager _featureManager;

    public ProductController(IFeatureManager featureManager)
    {
        _featureManager = featureManager;
    }
}
```

**Figura 10-13** : inserción de la marca de características en una clase.

Las bibliotecas de administración de características administran el ciclo de vida de las marcas de características en segundo plano. Por ejemplo, para minimizar un número elevado de llamadas al almacén de configuración, la memoria caché de las bibliotecas indica el estado de una duración especificada. Pueden garantizar la inmutabilidad de los Estados de marca durante una llamada de solicitud. También ofrecen un `Point-in-time snapshot` . Puede reconstruir el historial de cualquier valor de clave y proporcionar su valor anterior en cualquier momento en los siete días anteriores.

>[!div class="step-by-step"]
>[Anterior](devops.md)
>[Siguiente](infrastructure-as-code.md)
