---
title: Migración desde .NET Framework 1.1
description: Obtenga información sobre los pasos necesarios para ejecutar una aplicación compilada con .NET Framework 1.1 en Windows 7 o versiones posteriores.
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
ms.openlocfilehash: f2b0e21ff5dbeab3395335f52799629859fb2d90
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475273"
---
# <a name="migrate-from-the-net-framework-11"></a>Migración desde .NET Framework 1.1

Windows 7 y las versiones posteriores del sistema operativo Windows no admiten .NET Framework 1.1. En consecuencia, las aplicaciones que tienen como destino .NET Framework 1.1 no podrán ejecutarse sin modificaciones en Windows 7 o versiones posteriores del sistema operativo. En este tema describen los pasos necesarios para ejecutar una aplicación destinada a .NET Framework 1.1 en Windows 7 y versiones posteriores del sistema operativo Windows. Para más información sobre NET Framework 1.1 y Windows 8, consulte [Ejecutar aplicaciones .NET Framework 1.1 en Windows 8 y versiones posteriores](../install/run-net-framework-1-1-apps.md).

## <a name="retarget-or-recompile"></a>Redestinar o volver a compilar

Hay dos formas para conseguir que una aplicación compilada con NET Framework 1.1 se ejecute en Windows 7 o un sistema operativo de Windows posterior:

- Redestine la aplicación para que se ejecute en .NET Framework 4 y versiones posteriores. Para redestinarla, es necesario agregar un elemento [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) al archivo de configuración de la aplicación que permita ejecutarla en .NET Framework 4 y versiones posteriores. Un archivo de configuración de este tipo tendrá el formato siguiente:

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- Vuelva a compilar la aplicación con un compilador que tenga como destino .NET Framework 4 o una versión posterior. Si originalmente usó Visual Studio 2003 para desarrollar y compilar la solución, puede abrir la solución en Visual Studio 2010 y posiblemente también en versiones posteriores y usar el cuadro de diálogo **Compatibilidad del proyecto** para convertir la solución y los archivos del proyecto de los formatos utilizados en Visual Studio 2003 a los formatos de Microsoft Build Engine (MSBuild).

Independientemente de si prefiere volver a compilar o redestinar la aplicación, deberá determinar si la aplicación se ve afectada por los cambios introducidos en versiones posteriores de .NET Framework. Estos cambios son de dos tipos:

- Cambios importantes que se produjeron entre .NET Framework 1.1 y las versiones posteriores de .NET Framework.

- Tipos y miembros que se han marcado como desusados u obsoletos entre .NET Framework 1.1 y versiones posteriores de .NET Framework.

Tanto si redestina la aplicación como si vuelve a compilarla, deberá revisar los cambios importantes y los miembros y tipos obsoletos de cada versión de .NET Framework publicada después de .NET Framework 1.1.

## <a name="breaking-changes"></a>Cambios importantes

Cuando se realiza un cambio importante, en función del cambio concreto, puede haber una solución disponible tanto para las aplicaciones redestinadas como para las que se compilan de nuevo. En algunos casos, puede agregar un elemento secundario al elemento [\<runtime>](../configure-apps/file-schema/startup/supportedruntime-element.md) del archivo de configuración de la aplicación para restaurar el comportamiento anterior. Por ejemplo, el archivo de configuración siguiente restaura el comportamiento de comparación y ordenación de cadenas que se utilizaba en .NET Framework 1.1 y puede usarse tanto con una aplicación redestinada como con una aplicación que se ha compilado de nuevo.

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

Sin embargo, en algunos casos, tal vez necesite modificar el código fuente y volver a compilar la aplicación.

Para valorar el impacto que los posibles cambios importantes podrían tener en su aplicación, debe revisar las siguientes listas de cambios:

- En[Cambios importantes en .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa570326(v=msdn.10)) se muestran los cambios de .NET Framework 2.0 SP1 que pueden afectar a una aplicación destinada a .NET Framework 1.1.

- En [Cambios en .NET Framework 3.5 SP1](https://docs.microsoft.com/previous-versions/dotnet/articles/dd310284(v=msdn.10)) se indican los cambios entre .NET Framework 3.5 y .NET Framework 3.5 SP1.

- En [Incidencias de migración de .NET Framework 4](net-framework-4-migration-issues.md) se indican los cambios entre .NET Framework 3.5 SP1 y .NET Framework 4.

## <a name="obsolete-types-and-members"></a>Tipos y miembros obsoletos

El impacto de los tipos y miembros desusados es ligeramente distinto en las aplicaciones redestinadas que en las aplicaciones compiladas de nuevo. El uso de tipos y miembros obsoletos no afectará a la aplicación redestinada a menos que el tipo o miembro obsoleto se haya quitado físicamente del ensamblado. Cuando se vuelve a compilar una aplicación que utiliza tipos y miembros obsoletos, normalmente se produce una advertencia del compilador y no un error del compilador. Sin embargo, en algunos casos, se genera un error del compilador y el código que usa el tipo o miembro obsoleto no se compila correctamente. En este caso, debe volver a escribir el código fuente que llama al tipo o miembro obsoleto antes de volver a compilar la aplicación. Para obtener más información sobre los tipos y miembros obsoletos, vea [Lo obsoleto en la biblioteca de clases de .NET Framework](../whats-new/whats-obsolete.md).

Para valorar el impacto de los tipos y miembros en desuso desde la publicación de .NET Framework 2.0 SP1, vea [Lo obsoleto en la biblioteca de clases de .NET Framework](../whats-new/whats-obsolete.md). Consulte las listas de tipos y miembros obsoletos de NET Framework 2.0 SP1, .NET Framework 3.5 y .NET Framework 4.
