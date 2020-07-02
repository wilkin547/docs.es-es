---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614785"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>El uso de servicios reentrantes puede producir un interbloqueo

#### <a name="details"></a>Detalles

Se puede producir un interbloqueo en un servicio reentrante, lo que restringe las instancias del servicio a un subproceso de ejecución a la vez. Los servicios propensos a sufrir este problema tendrán el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> siguiente en su código:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>Sugerencia

Para solucionar este problema, puede seguir estos pasos:

- Establezca el modo de simultaneidad del servicio en <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> o &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Por ejemplo:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework. Esto deshabilita el flujo de <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

El valor de `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` nunca se debe establecer en `false` para los servicios reentrantes.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
