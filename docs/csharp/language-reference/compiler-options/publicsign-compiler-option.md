---
description: -filealign (Opciones del compilador de C#)
title: -filealign (Opciones del compilador de C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 525912c7f50aa6b51e602be7b9258f1f5907daac
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124817"
---
# <a name="-publicsign-c-compiler-options"></a>-filealign (Opciones del compilador de C#)

Esta opción hace que el compilador aplique una clave pública pero no firma el ensamblado. La opción **-publicsign** también establece un bit en el ensamblado que indica el entorno de tiempo de ejecución en el que el archivo está firmado.

## <a name="syntax"></a>Sintaxis

```console
-publicsign
```

## <a name="arguments"></a>Argumentos

Ninguno.

## <a name="remarks"></a>Comentarios

La opción **-publicsign** requiere el uso de [-keyfile](keyfile-compiler-option.md) o [-keycontainer](keycontainer-compiler-option.md). Las opciones **keyfile** o **keycontainer** especifican la clave pública.

Las opciones **-publicsign** y **-delaysign** son mutuamente excluyentes.

A veces llamada "firma falsa" o "firma OSS", la firma pública incluye la clave pública en un ensamblado de salida y establece la marca "firmado", pero en realidad no firma el ensamblado con una clave privada. Esto es útil para proyectos de código abierto donde la gente quiere crear ensamblados que sean compatibles con los ensamblados "totalmente firmados" publicados, pero que no tengan acceso a la clave privada utilizada para firmar los ensamblados. Dado que casi ningún consumidor necesita realmente comprobar si el ensamblado está completamente firmado, estos ensamblados públicamente creados se pueden utilizar en casi todos los escenarios en los que se utilizaría el ensamblado totalmente firmado.

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a>Cómo establecer esta opción del compilador en un archivo .csproj

Abra el archivo .csproj de un proyecto y agregue el elemento siguiente:

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a>Consulte también

- [Opción -delaysign del compilador de C#](delaysign-compiler-option.md)
- [Opción -keyfile del compilador de C#](keyfile-compiler-option.md)
- [Opción -keycontainer del compilador de C#](keycontainer-compiler-option.md)
- [Opciones del compilador de C#](index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
