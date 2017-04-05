---
title: Control de versiones de .NET Core
description: Control de versiones de .NET Core
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f6f684b1-1d2c-4105-8376-7c1959e23803
translationtype: Human Translation
ms.sourcegitcommit: 519253bd6dc105afb138268c62347c29a6072fbb
ms.openlocfilehash: 7be49f3ac7a7806e631eacf5004343919654881e
ms.lasthandoff: 04/05/2017

---

# <a name="net-core-versioning"></a>Control de versiones de .NET Core

.NET Core es una plataforma de [paquetes de NuGet](../packages.md) y marcos y que se distribuye como una unidad. Cada uno de estos niveles de plataforma puede tener una versión distinta para proporcionar agilidad al producto y describir de forma precisa sus cambios. Aunque hay bastante flexibilidad en el control de versiones, existe el deseo de controlar la versión de la plataforma como una unidad para que el producto sea más fácil de comprender.

El producto es, en algunos aspectos, único, y se describe y entrega como un paquete mediante un administrador de paquetes (NuGet). Aunque .NET Core se suele adquirir normalmente como un SDK independiente, el SDK es en gran medida una experiencia cómoda a través de NuGet y, por tanto, no se diferencia de los paquetes. Como resultado, el control de versiones es lo primero, en términos de paquetes y otras experiencias de control de versiones que vienen a partir de ahí.

## <a name="semantic-versioning"></a>Control de versiones semántico

.NET Core usa [Versionamiento Semántico (SemVer)](http://semver.org/), que adopta el uso de control de versiones major.minor.patch mediante las diversas partes del número de versión para describir el grado y tipo de cambio.

La siguiente plantilla de control de versiones se aplica normalmente a .NET Core. Hay casos donde se ha adaptado al control de versiones existente. Estos casos se describen más adelante en este documento. Por ejemplo, los marcos solo están pensados para representar las funcionalidades de plataforma y API, lo cual se alinea con el control de versiones principales/secundarias.

### <a name="versioning-form"></a>Formulario de control de versiones

MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]

### <a name="decision-tree"></a>Árbol de decisión

MAJOR (Principal) cuando:
  - quita compatibilidad con una plataforma
  - adopta una versión MAJOR (Principal) más reciente de una dependencia existente 
  - deshabilita de forma predeterminada una peculiaridad de compatibilidad

SECUNDARIA cuando:
  - agrega área de superficie de API pública 
  - agregar nuevo comportamiento
  - adoptar una versión MINOR (Secundaria) más reciente de una dependencia existente
  - introducir una nueva dependencia 
  
PATCH (Revisión) cuando:
  - realiza correcciones de errores
  - agrega compatibilidad con una plataforma más reciente
  - adopta una versión más reciente de PATCH (Revisión) de una dependencia existente
  - cualquier otro cambio (no capturado de otro modo)

A la hora de determinar qué aumentar cuando hay varios cambios, elija la clase de cambio más alta.

## <a name="versioning-scheme"></a>Esquema de control de versiones

.NET Core se puede definir como una versión y se asignará esta de la manera siguiente:

- Una implementación de entorno de ejecución y marco, distribuida en paquetes. Cada paquete tiene una versión independiente, en especial para el control de versiones de revisión.
- Un conjunto de metapaquetes que hacen referencia a paquetes específicos como una unidad con versión. Los metapaquetes tienen versiones independientemente de los paquetes.
- Un conjunto de marcos (por ejemplo, `netstandard`) que representa un conjunto de API cada vez mayor, descrito como un conjunto de instantáneas con versión.

### <a name="packages"></a>Paquetes

Los paquetes de biblioteca evolucionan y se les asignan versiones de forma independiente. Paquetes que se superponen con el sistema .NET Framework.\* Los ensamblados usan normalmente versiones 4.x y se alinean con el control de versiones de .NET Framework 4.x (una opción histórica). Los paquetes que no se superponen con las bibliotecas de .NET Framework (por ejemplo, [System.Reflection.Metadata](https://www.nuget.org/packages/System.Reflection.Metadata)) normalmente empiezan en 1.0 y se incrementan desde ahí.

Los paquetes descritos por [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) se tratan de manera especial debido ya que están en la base de la plataforma.

- Los paquetes NETStandard.Library tendrán normalmente una versión de conjunto, puesto que tienen dependencias de nivel de implementación entre ellos.
- Las API solo se agregan a los paquetes NETStandard.Library como parte de las versiones principales o secundarias de .NET Core, ya que hacerlo así requerirá agregar una nueva versión de `netstandard`. Y esto aparte de los requisitos de SemVer.

### <a name="metapackages"></a>Metapaquetes

El control de versiones de los metapaquetes de .NET Core se basa en el marco al que se asignan. Los metapaquetes adoptan al número de versión más alto del marco (por ejemplo, netstandard1.6) al que se asignan cuando se cierra el paquete. 

La versión de revisión del metapaquete se usa para representar las actualizaciones del metapaquete con el fin de hacer referencia a los paquetes actualizados. Las versiones de revisión nunca se incluyen en una versión del marco actualizada. Como consecuencia, los metapaquetes no son compatibles de forma estricta con SemVer porque su esquema de control de versiones no representa el grado de cambio en los paquetes subyacentes, sino principalmente en el nivel de API. 

Hay dos metapaquetes principales para .NET Core.

**NETStandard.Library**

- v1.6 a partir de .NET Core 1.0 (estas versiones no coincidirán normalmente o a propósito).
- Se asigna al marco `netstandard`. 
- Describe los paquetes que se consideran necesarios para el desarrollo de aplicaciones modernas y que deben implementar las plataformas .NET para que se consideren una plataforma un [.NET Standard](../../standard/library.md).

**Microsoft.NETCore.App**

- v1.0 a partir de .NET Core 1.0 (estas versiones coincidirán).
- Se asigna al marco `netcoreapp`.
- Describe los paquetes de la distribución de .NET Core.

Nota: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) es otro metapaquete de .NET Core. No se asigna a un marco determinado, así que las versiones son como un paquete.

### <a name="frameworks"></a>Marcos de trabajo

Las versiones de marco se actualizan cuando se agregan nuevas API. No tienen ningún concepto de versión de revisión, ya que representan la forma de API y no los problemas de implementación. Las versiones principales y secundarias seguirán las reglas de SemVer especificadas anteriormente.

El marco `netcoreapp` está asociado a la distribución de .NET Core. Seguirá los números de versión que usa .NET Core. Por ejemplo, cuando se lance .NET Core 2.0, tendrá como destino `netcoreapp2.0`. El marco `netstandard` no coincidirá con el esquema de control de versiones de ningún entorno de tiempo de ejecución .NET, ya que es igualmente aplicable a todos ellos.

## <a name="versioning-in-practice"></a>Control de versiones en la práctica

Diariamente hay confirmaciones y PR en los repositorios de .NET Core de GitHub, lo que da lugar a nuevas compilaciones en muchas bibliotecas. No resulta práctico crear nuevas versiones públicas de .NET Core para cada cambio. Por el contrario, los cambios se agregarán durante un período de tiempo definido de forma flexible (por ejemplo, semanas o meses) antes de crear una nueva versión de .NET Core pública que sea estable.

Una nueva versión de .NET Core podría significar varias cosas:

- Nuevas versiones de paquetes y metapaquetes.
- Nuevas versiones de distintos marcos, contando con la adición de nuevas API.
- Nueva versión de la distribución de .NET Core.

### <a name="shipping-a-patch-release"></a>Envío de una versión de revisión

Después de enviar una versión estable ce .NET Core v1.0.0, se realizan cambios en el nivel de revisión (sin nuevas API) en las bibliotecas .NET Core para corregir errores y mejorar el rendimiento y la confiabilidad. Los diversos metapaquetes se actualizan para hacer referencia a los paquetes de biblioteca de .NET Core actualizados. Los metapaquetes tienen la versión de las actualizaciones de revisiones (x.y.z). Los marcos no se actualizan. Se lanza una nueva distribución de .NET Core con un número de versión que coincide con el metapaquete `Microsoft.NETCore.App`.

A continuación puede ver la demostración de actualizaciones de versión en los siguientes ejemplos de project.json.

```
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.1"
  },
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

### <a name="shipping-a-minor-release"></a>Envío de una versión secundaria

Después de enviar una versión estable de .NET Core v1.0.0, se agregan nuevas API a las bibliotecas .NET Core para permitir nuevos escenarios. Los diversos metapaquetes se actualizan para hacer referencia a los paquetes de biblioteca de .NET Core actualizados. Los metapaquetes tienen las versiones de las actualizaciones de revisión (x.y) para que coincidan con la versión más alta del marco. Los distintos marcos se actualizan para describir las nuevas API. Se lanza una nueva distribución de .NET Core con un número de versión que coincide con el metapaquete `Microsoft.NETCore.App`.

Puede ver la demostración de actualizaciones secundarias en el siguiente archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp1.1</TargetFramework>
  </PropertyGroup>
</Project>
```

### <a name="shipping-a-major-release"></a>Envío de una versión principal

Dada una versión estable .NET Core v1.y.z, se agregan nuevas API a las bibliotecas .NET Core para permitir nuevos escenarios principales. Quizás, se quita la compatibilidad con una plataforma. Los diversos metapaquetes se actualizan para hacer referencia a los paquetes de biblioteca de .NET Core actualizados. El metapaquete `Microsoft.NETCore.App` y el marco `netcore` tienen versiones como una actualización principal (x.). Es probable que el metapaquete `NETStandard.Library` tenga la versión de una actualización secundaria (x.y) dado que se aplica a varias implementaciones de .NET. Se lanzaría una nueva distribución de .NET Core con un número de versión coincidente con el metapaquete `Microsoft.NETCore.App`.

Puede ver la demostración de actualizaciones principales en el siguiente archivo del proyecto. (Tenga en cuenta que `netcoreapp2.0` no se ha publicado).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
  </PropertyGroup>
</Project>

```

