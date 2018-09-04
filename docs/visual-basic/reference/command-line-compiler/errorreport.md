---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509678"
---
# <a name="-errorreport"></a>-errorreport

Especifica cómo el compilador de Visual Basic debe notificar errores internos del compilador.

## <a name="syntax"></a>Sintaxis

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Comentarios

Esta opción proporciona una forma cómoda para notificar un error interno del compilador de Visual Basic (ICE) al equipo de Visual Basic a Microsoft. De forma predeterminada, el compilador no envía ninguna información a Microsoft. Sin embargo, si se produce un error interno del compilador, esta opción le permite notificar el error a Microsoft. Esta información le ayudará a los ingenieros de Microsoft a identificar la causa y puede ayudar a mejorar la próxima versión de Visual Basic.

Capacidad de un usuario para enviar informes depende de los permisos de directiva de equipo y usuario.

En la tabla siguiente se resume el efecto de la `-errorreport` opción.

|Opción|Comportamiento|
|---|---|
|`prompt`|Si se produce un error interno del compilador, aparece un cuadro de diálogo para que pueda ver los datos exactos que el compilador recopilado. Puede determinar si no hay ninguna información confidencial en el informe de errores y tomar una decisión sobre si se envían a Microsoft. Si decide que debe enviarla, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.|
|`queue`|Pone en cola el informe de error. Cuando inicie sesión con privilegios de administrador, puede notificar los errores desde la última vez que se ha iniciado sesión (no se le indicará que envíe informes de errores más de una vez cada tres días). Este es el comportamiento predeterminado cuando el `-errorreport` no se especifica la opción.|
|`send`|Si se produce un error interno del compilador, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.<br /><br /> La opción `-errorreport:send` intenta enviar automáticamente información de errores a Microsoft si el informe está habilitado por la [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) configuración del sistema. |
|`none`|Si se produce un error interno del compilador, no se recopila o envía a Microsoft.|

El compilador envía los datos que incluyen la pila en el momento del error, que normalmente incluye código fuente. Si `-errorreport` se usa con el [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, se envía el archivo de código fuente.

Esta opción se usa mejor con la [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, ya que permite a los ingenieros de Microsoft más fácil reproducen el error.

> [!NOTE]
> El `-errorreport` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.

## <a name="example"></a>Ejemplo

El código siguiente intenta compilar `T2.vb`, y si el compilador encuentra un error interno del compilador, pregunta si desea enviar el informe de errores a Microsoft.

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
