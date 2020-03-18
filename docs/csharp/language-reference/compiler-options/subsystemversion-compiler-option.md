---
title: -subsystemversion (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: d76c9424340b4b6f3c211c849b466be55eb79d1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74802034"
---
# <a name="-subsystemversion-c-compiler-options"></a>-subsystemversion (Opciones del compilador de C#)

Especifica la versión mínima del subsistema en la que se puede ejecutar el archivo ejecutable generado, lo que determina las versiones de Windows en las que se puede ejecutar el archivo ejecutable. Normalmente, esta opción garantiza que el archivo ejecutable pueda aprovechar las características de seguridad concretas que no están disponibles en versiones anteriores de Windows.

> [!NOTE]
> Para especificar el subsistema en sí mismo, use la opción del compilador [-target](./target-compiler-option.md).

## <a name="syntax"></a>Sintaxis

```console
-subsystemversion:major.minor
```

## <a name="parameters"></a>Parámetros

`major.minor`

La versión mínima requerida del subsistema, expresada en una notación de puntos para las versiones principales y secundarias. Por ejemplo, puede especificar que una aplicación no se puede ejecutar en un sistema operativo que sea anterior a Windows 7 si establece el valor de esta opción en 6.01, como se describe en la tabla que aparece más adelante en este tema. Debe especificar los valores de `major` y `minor` como números enteros.

Los ceros a la izquierda en la versión `minor` no cambian la versión, pero los ceros a la derecha sí. Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente. Se recomienda expresar la versión secundaria como dos dígitos para evitar confusiones.

## <a name="remarks"></a>Comentarios

En la tabla siguiente se enumeran las versiones de subsistema habituales de Windows.

|Versión de Windows|Versión de subsistema|
|---------------------|-----------------------|
|Windows 2000|5.00|
|Windows XP|5,01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6.01|
|Windows Server 2008|6.01|
|Windows 8|6.02|

## <a name="default-values"></a>Valores predeterminados

El valor predeterminado de la opción del compilador **-subsystemversion** depende de las condiciones de esta lista:

- El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:

  - [/target:appcontainerexe](./target-appcontainerexe-compiler-option.md)

  - [/target:winmdobj](./target-winmdobj-compiler-option.md)

  - [-platform:arm](./platform-compiler-option.md)

- El valor predeterminado es 6,00 si usa MSBuild, tiene como destino .NET Framework 4.5 y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.

- El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.

## <a name="setting-this-option"></a>Establecer esta opción

Para establecer la opción del compilador **-subsystemversion** en Visual Studio, debe abrir el archivo .csproj y especificar un valor para la propiedad `SubsystemVersion` en el XML de MSBuild. No se puede establecer esta opción en el IDE de Visual Studio. Para obtener más información, consulte la sección "Valores predeterminados" que aparece más arriba en este tema o [Propiedades comunes de proyectos de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
