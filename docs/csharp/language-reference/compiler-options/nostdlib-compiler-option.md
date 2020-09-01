---
description: -nostdlib (Opciones del compilador de C#)
title: -nostdlib (Opciones del compilador de C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 214918b32f1f1276eb936e66daba3d372a1e9228
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125103"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (Opciones del compilador de C#)

**-nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.

## <a name="syntax"></a>Sintaxis

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>Observaciones

Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.

Si no se especifica **-nostdlib**, el archivo mscorlib.dll se importa en el programa (equivale a especificar **-nostdlib-**). Especificar **-nostdlib** es lo mismo que especificar **-nostdlib+**.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Para establecer esta opción del compilador en Visual Studio

> [!NOTE]
> Las instrucciones siguientes solo se aplican a Visual Studio 2015 (y versiones anteriores). La propiedad de compilación **No hacer referencia a mscorlib.dll** no existe en Visual Studio.

1. Abra la página **Propiedades** del proyecto.

2. Haga clic en la página de propiedades de **Compilar** .

3. Haga clic en el botón **Avanzadas** .

4. Modifique la propiedad **No hacer referencia al archivo mscorlib.dll** .

### <a name="to-set-this-compiler-option-programmatically"></a>Para establecer esta opción del compilador mediante programación

Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
