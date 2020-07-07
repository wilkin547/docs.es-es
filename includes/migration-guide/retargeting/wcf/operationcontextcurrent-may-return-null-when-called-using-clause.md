---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614752"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>Es posible que OperationContext.Current devuelva NULL cuando se llama en una cláusula using.

#### <a name="details"></a>Detalles

Es posible que <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> devuelva `null` y que se inicie una excepción <xref:System.NullReferenceException> si todas las condiciones siguientes son verdaderas:

- Se recupera el valor de la propiedad <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> en un método que devuelve una <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.
- Se crea una instancia del objeto <xref:System.ServiceModel.OperationContextScope> en una cláusula `using`.
- Se recupera el valor de la propiedad <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> dentro de `using statement`. Por ejemplo:

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a>Sugerencia

Para solucionar este problema, puede seguir estos pasos:

- Modifique el código como se indica aquí para crear una instancia de un nuevo objeto <xref:System.ServiceModel.OperationContext.Current%2A> que no sea `null`:

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework. Esto deshabilita el flujo del <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> y restaura el comportamiento de las aplicaciones de WCF de .NET Framework 4.6.1 y versiones anteriores. Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    Si no quiere este cambio y la aplicación depende del flujo del contexto de ejecución entre los contextos de operación, puede habilitar su flujo de esta manera:

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
