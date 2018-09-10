---
title: -filealign (Opciones del compilador de C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 01ce30b9ac5997f56f29dcbbfa43a27738fa5556
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44184988"
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

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra la página **Propiedades** del proyecto.
1. Modifique la propiedad **Solo retrasar firma**.

## <a name="see-also"></a>Vea también

- [Opción -delaysign del compilador de C#](delaysign-compiler-option.md)  
- [Opción -keyfile del compilador de C#](keyfile-compiler-option.md)  
- [Opción -keycontainer del compilador de C#](keycontainer-compiler-option.md)  
- [Opciones del compilador de C#](index.md)  
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
