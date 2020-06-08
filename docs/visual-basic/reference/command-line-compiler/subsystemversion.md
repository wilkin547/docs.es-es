---
title: -subsystemversion
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: 09ddc4bb735b645e09d34198c66dff78183592bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403088"
---
# <a name="-subsystemversion-visual-basic"></a>-subsystemversion (Visual Basic)

Especifica la versión mínima del subsistema en la que se puede ejecutar el archivo ejecutable generado, lo que determina las versiones de Windows en las que se puede ejecutar el archivo ejecutable. Normalmente, esta opción garantiza que el archivo ejecutable pueda aprovechar las características de seguridad concretas que no están disponibles en versiones anteriores de Windows.

> [!NOTE]
> Para especificar el subsistema en sí mismo, use la opción del compilador [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).

## <a name="syntax"></a>Sintaxis

```vb
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
|Windows XP|5.01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6.01|
|Windows Server 2008|6.01|
|Windows 8|6.02|

## <a name="default-values"></a>Valores predeterminados

El valor predeterminado de la opción del compilador **-subsystemversion** depende de las condiciones de esta lista:

- El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:

  - [/target:appcontainerexe](target.md)

  - [/target:winmdobj](target.md)

  - [-platform:arm](platform.md)

- El valor predeterminado es 6,00 si usa MSBuild, tiene como destino .NET Framework 4.5 y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.

- El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.

## <a name="setting-this-option"></a>Establecer esta opción

Para establecer la opción **-subsystemversion** del compilador en Visual Studio, debe abrir el archivo .vbproj y especificar un valor para la propiedad `SubsystemVersion` en el XML de MSBuild. No se puede establecer esta opción en el IDE de Visual Studio. Para obtener más información, consulte la sección "Valores predeterminados" que aparece más arriba en este tema o [Propiedades comunes de proyectos de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)

- [Propiedades de MSBuild](/visualstudio/msbuild/msbuild-properties)
