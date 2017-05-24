---
title: Marcos de trabajo de destino | Microsoft Docs
description: "Información en torno a los marcos de trabajo de destino para aplicaciones y bibliotecas de .NET Core."
keywords: .NET, .NET Core, marco de trabajo, TFM
author: richlander
ms.author: mairaw
ms.date: 04/27/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
ms.translationtype: Machine Translation
ms.sourcegitcommit: 45835eb80642253f80ea630ae9db1ac766b72b9c
ms.openlocfilehash: 11c1f11e4f8354b7573d03e680cf4a8a16fa26d9
ms.contentlocale: es-es
ms.lasthandoff: 05/11/2017

---

# <a name="target-frameworks"></a>Versiones de .NET Framework de destino

Los *marcos de trabajo* definen los objetos, los métodos y las herramientas que se usan para crear aplicaciones y bibliotecas. .NET Framework se usa para crear aplicaciones y bibliotecas para ejecutar principalmente en sistemas con un sistema operativo Windows. .NET Core incluye un marco de trabajo que permite crear aplicaciones y bibliotecas que se ejecutan en distintos sistemas operativos.

Los términos *marco de trabajo* y *plataforma* a veces resultan confusos por cómo se usan en las frases. Para dificultar aún más su interpretación, el término *plataforma* tiene significados distintos en contextos diferentes. Por ejemplo, verá ".NET Core" descrito como el "marco de trabajo .NET Core" en el contexto de la creación de aplicaciones y bibliotecas y además descrito como "plataforma .NET Core" en el contexto de dónde se ejecuta el código de aplicación y biblioteca. Una *plataforma informática* describe *dónde y cómo* se ejecuta una aplicación. Dado que .NET Core ejecuta el código con [.NET Core Common Language Runtime (CoreCLR)](https://github.com/dotnet/coreclr), también es una plataforma. Lo mismo puede decirse de .NET Framework, que tiene [Common Language Runtime (CLR)](clr.md) para ejecutar el código de aplicación y biblioteca desarrollado con los objetos, los métodos y las herramientas de marco de trabajo de .NET Framework. Con frecuencia verá el término "multiplataforma" en la documentación, aunque cuando sea así, debe pensar en "para varios sistemas operativos y para varias arquitecturas (x86, x64, arm)", porque ese es el significado que el autor normalmente intenta transmitir.

Los objetos y los métodos de los marcos de trabajo se denominan interfaces de programación de aplicaciones (API). Las API de marco de trabajo se usan en [Visual Studio](https://www.visualstudio.com/), [Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/), [Visual Studio Code](https://code.visualstudio.com/) y otros entornos de desarrollo integrado (IDE) y editores para proporcionarle el conjunto correcto de objetos y métodos para desarrollar. Los marcos de trabajo también se usan en [NuGet](https://www.nuget.org/) para la producción y el uso de paquetes NuGet a fin de asegurarse de crear y usar los paquetes adecuados para los marcos de trabajo de destino en la aplicación o biblioteca.

Cuando *elige un marco de trabajo como destino* o varios, ha decidido qué conjuntos de API y qué versiones de esas API quiere usar. La referencia a los marcos de trabajo se hace de varias maneras: por nombre de producto, por nombre de marco de trabajo en formato largo o corto y por familia.

## <a name="referring-to-frameworks"></a>Referencia a los marcos de trabajo

Hay varias maneras de hacer referencia a los marcos de trabajo, la mayoría de las cuales se usa en la documentación de .NET Core. Si tomamos .NET Framework 4.6.2 como ejemplo, se usan los siguientes formatos:

**Hacer referencia a un producto**

Puede hacer referencia a un runtime o a una plataforma de .NET. Ambos son igualmente válidos.

* .NET Framework 4.6.2
* .NET 4.6.2

**Referencia a un marco de trabajo**

Puede hacer referencia a un marco de trabajo o centrar como destino un marco de trabajo con formatos largos o cortos de TFM. Ambos son igualmente válidos.

* `.NETFramework,Version=4.6.2`
* `net462`

**Referencia a una familia de marcos de trabajo**

Puede hacer referencia a una familia de marcos de trabajo con formatos largos o cortos del ID del marco de trabajo. Ambos son igualmente válidos.

* `.NETFramework`
* `net`

## <a name="latest-framework-versions"></a>Versiones más recientes de marcos de trabajo

En la tabla siguiente se define el conjunto de marcos de trabajo que puede usar, cómo se hace referencia a ellos y la versión de la [biblioteca de .NET Standard](library.md) que implementan. Estas versiones de marcos de trabajo son las últimas versiones estables. No se muestran las versiones preliminares.

| Framework             | Última versión | Moniker de la plataforma de destino (TFM) | Moniker de la plataforma de destino compacta (TFM) | Versión de .NET Standard | Metapaquete |
| :-------------------: | :------------: | :----------------------------: | :------------------------------------: | :-------------------: | :---------: |
| Estándar .NET         | 1.6.1          | .NETStandard, Versión=1.6       | netstandard1.6                         | N/D                   | [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) |
| Aplicación .NET Core | 1.1.1          | .NETCoreApp,Version=1.1        | netcoreapp1.1                          | 1.6                   | [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) |
| .NET Framework        | 4.6.2          | .NETFramework, Versión=4.6.2    | net462                                 | 1.5                   | N/D |

## <a name="supported-frameworks"></a>Marcos de trabajo admitidos

A un marco de trabajo normalmente se hace referencia mediante un moniker corto de la plataforma de destino o *TFM*. En .NET Standard, esto también se ha generalizado a *TxM* para permitir una sola referencia a varios marcos de trabajo. Los clientes de NuGet admiten los marcos de trabajo siguientes. Los equivalentes se muestran entre corchetes (`[]`).

| Name                       | Abreviatura | TFMs/TxMs                                    |
| -------------------------- | ------------ | -------------------------------------------- |
| Estándar .NET              | netstandard  | netstandard1.0                               |
|                            |              | netstandard1.1                               |
|                            |              | netstandard1.2                               |
|                            |              | netstandard1.3                               |
|                            |              | netstandard1.4                               |
|                            |              | netstandard1.5                               |
|                            |              | netstandard1.6                               |
| Núcleo de .NET                  | netcoreapp   | netcoreapp1.0                                |
|                            |              | netcoreapp1.1                                |
| .NET Framework             | net          | net11                                        |
|                            |              | net20                                        |
|                            |              | net35                                        |
|                            |              | net40                                        |
|                            |              | net403                                       |
|                            |              | net45                                        |
|                            |              | net451                                       |
|                            |              | net452                                       |
|                            |              | net46                                        |
|                            |              | net461                                       |
|                            |              | net462                                       |
| Tienda Windows              | netcore      | netcore [netcore45]                          |
|                            |              | netcore45 [win, win8]                        |
|                            |              | netcore451 [win81]                           |
| .NET Micro Framework       | netmf        | netmf                                        |
| Silverlight                | sl           | sl4                                          |
|                            |              | sl5                                          |
| Windows Phone              | wp           | wp [wp7]                                     |
|                            |              | wp7                                          |
|                            |              | wp75                                         |
|                            |              | wp8                                          |
|                            |              | wp81                                         |
|                            |              | wpa81                                        |
| Plataforma universal de Windows | uap          | uap [uap10.0]                                |
|                            |              | uap10.0 [win10] [netcore50]                  |

## <a name="deprecated-frameworks"></a>Marcos de trabajo en desuso

Los marcos de trabajo siguientes están en desuso. Los paquetes destinados a estos marcos de trabajo deben migrarse a los reemplazos indicados.

| Marco de trabajo en desuso | Replacement |
| -------------------- | ----------- |
| aspnet50             | netcoreapp  |
| aspnetcore50         |             |
| dnxcore50            |             |
| dnx                  |             |
| dnx45                |             |
| dnx451               |             |
| dnx452               |             |
| dotnet               | netstandard |
| dotnet50             |             |
| dotnet51             |             |
| dotnet52             |             |
| dotnet53             |             |
| dotnet54             |             |
| dotnet55             |             |
| dotnet56             |             |
| netcore50            | uap10.0     |
| win                  | netcore45   |
| win8                 | netcore45   |
| win81                | netcore451  |
| win10                | uap10.0     |
| winrt                | netcore45   |

## <a name="precedence"></a>Precedencia

Hay una serie de marcos de trabajo relacionados y compatibles entre sí, pero no necesariamente equivalentes:

| Framework                        | Puede usar   |
| -------------------------------- | --------- |
| uap (Plataforma universal de Windows) | win81     |
|                                  | wpa81     |
|                                  | netcore50 |
| win (Tienda Windows)              | winrt     |
|                                  | winrt45   |

## <a name="net-standard"></a>Estándar .NET

[.NET Standard](https://github.com/dotnet/standard) simplifica las referencias entre marcos de trabajo compatibles con binarios, lo que permite que un solo marco de trabajo de destino haga referencia a una combinación de otros. Para más información, vea el tema [.NET Standard Library (Biblioteca de .NET Standard)](library.md).

La herramienta de NuGet Tools [Get Nearest Framework](http://nugettoolsdev.azurewebsites.net/) simula la lógica de NuGet usada para la selección de un marco de trabajo entre los muchos recursos de marco de trabajo disponibles en un paquete según el marco de trabajo del proyecto. Para usar la herramienta, escriba un marco de trabajo del proyecto y uno o más marcos de trabajo del paquete. Seleccione el botón **Enviar**. La herramienta indica si los marcos de trabajo del paquete que se enumeran son compatibles con el marco de trabajo del proyecto que se proporciona.

## <a name="portable-class-libraries"></a>Bibliotecas de clases portables

Para más información sobre las bibliotecas de clases portables, vea la sección [Portable Class Libraries (Bibliotecas de clases portables)](https://docs.microsoft.com/nuget/schema/target-frameworks#portable-class-libraries) del tema *Target Framework (Marco de trabajo de destino)* en la documentación de NuGet. Stephen Cleary ha creado una herramienta que enumera las bibliotecas de clases portables compatibles. Para más información, vea [Framework Profiles in .NET (Perfiles de marcos de trabajo en .NET)](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html).

