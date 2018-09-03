---
title: -nostdlib (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 70007c74efe9a41bdfc15e8fa7daf3c8fc0221ed
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484140"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (Opciones del compilador de C#)

**-nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.

## <a name="syntax"></a>Sintaxis

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>Comentarios

Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.

Si no se especifica **-nostdlib**, el archivo mscorlib.dll se importa en el programa (equivale a especificar **-nostdlib-**). Especificar **-nostdlib** es lo mismo que especificar **-nostdlib+**.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Para establecer esta opción del compilador en Visual Studio

> [!NOTE]
> Las instrucciones siguientes solo se aplican a Visual Studio 2015 (y versiones anteriores). La propiedad de compilación **No hacer referencia a mscorlib.dll** no existe en Visual Studio 2017.

1. Abra la página **Propiedades** del proyecto.

2. Haga clic en la página de propiedades de **Compilar** .

3. Haga clic en el botón **Avanzada** .

4. Modifique la propiedad **No hacer referencia al archivo mscorlib.dll** .

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
