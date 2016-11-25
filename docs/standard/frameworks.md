---
title: Marcos y destinos
description: "Explica los conceptos de los destinos de marcos al escribir código. NET."
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 09/19/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
translationtype: Human Translation
ms.sourcegitcommit: 38561c2d25c6950d166bf706f4306c867e683b04
ms.openlocfilehash: 82ba6f4abe200dc48158eac1ad3e3609feeda2c9

---

# <a name="frameworks-and-targets"></a>Marcos y destinos

El ecosistema .NET tiene un concepto de marcos de trabajo. Los marcos de trabajo definen la API que puede usar para centrar el destino en una plataforma concreta. .NET Framework 4.6 es una de esas plataformas. Los marcos de trabajo se usan en Visual Studio y en otros IDE y editores para proporcionarle el conjunto correcto de API. También se usan en NuGet, para producción y consumo de paquetes de NuGet, para asegurarse de que crea y usa los paquetes adecuados (y los recursos subyacentes) para el marco de trabajo de destino. Se puede considerar que los marcos de trabajo son las monedas clave en el ecosistema de .NET. El concepto se basa en la corrección, pretende ayudarle a usted y a sus clientes a evitar @System.MissingMethodException y a sus compañeros en el runtime.

## <a name="framework-versions"></a>Versiones de marcos de trabajo

La tabla siguiente define el conjunto de marcos de trabajo que puede usar, cómo se hace referencia a ellos y la versión de [.NET Standard Library](library.md) que implementan.

| Framework | Última versión | Moniker de la plataforma de destino (TFM) | Moniker de la plataforma de destino compacta (TFM) | Versión de .NET Standard | Metapaquete |
|:--------: | :--: | :--: | :--: | :--: | :--: | :--: |
| .NET Standard | 1.6 | .NETStandard, Versión=1.6 | netstandard1.6 | N/D | [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library)|
| Aplicación .NET Core | 1.0.1 | .NETCoreApp,Versión=1.0 | netcoreapp1.0 | 1.6 | [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App)|
| .NET Framework | 4.6.2 | .NETFramework, Versión=4.6.2 | net462 | 1.5 | N/D |

> [!NOTE]
> Estas versiones de marcos de trabajo son las últimas versiones estables. También puede haber versiones preliminares que no se describen en esta tabla.

## <a name="writing-about-frameworks"></a>Escribir sobre marcos de trabajo

Hay varias maneras de hacer referencia a los marcos de trabajo por escrito, la mayoría de las cuales se usan en esta documentación. Se describen a continuación, tanto como una leyenda para interpretar la documentación, pero también para servir de guía en el uso en otros documentos.

Si tomamos .NET Framework 4.6.1 como ejemplo, se pueden usar los siguientes formatos:

**Hacer referencia a un producto**

Puede hacer referencia a un runtime o a una plataforma de .NET.

- ".NET Framework 4.6.1"

**Hacer referencia a un marco de trabajo**

Puede hacer referencia a un marco de trabajo o centrar como destino un marco de trabajo con formatos largos o cortos de TFM. Ambas opciones son igual de válidas en general.

- `.NETFramework,Version=4.6.1`
- `net461`

**Hacer referencia a una familia de marcos de trabajo**

Puede hacer referencia a una familia de marcos de trabajo con formatos largos o cortos del ID del marco de trabajo. Ambas opciones son igual de válidas en general.

- `.NETFramework`
- `net`



<!--HONumber=Nov16_HO3-->


