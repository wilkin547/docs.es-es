---
description: Mas información sobre -errorreport
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: b6fa10482e6852a819303074b4662f02eb8d1f88
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475947"
---
# <a name="-errorreport"></a>-errorreport

Especifica cómo debe documentar el compilador de Visual Basic los errores internos del compilador.

## <a name="syntax"></a>Sintaxis

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Comentarios

Esta opción ofrece una manera cómoda de notificar un error interno del compilador (ICE) de Visual Basic al equipo de Visual Basic en Microsoft. De forma predeterminada, el compilador no envía ninguna información a Microsoft. Aunque si se produce un error interno del compilador, esta opción le permite notificar el error a Microsoft. Esa información ayudará a los ingenieros de Microsoft a identificar la causa y puede que ayude a mejorar la próxima versión de Visual Basic.

La capacidad de un usuario de enviar informes depende de los permisos de las directivas de máquina y de usuario.

En la siguiente tabla se resumen los efectos de la opción `-errorreport`.

|Opción|Comportamiento|
|---|---|
|`prompt`|Si se produce un error interno del compilador, se abre un cuadro de diálogo para que pueda ver los datos exactos recopilados por el compilador. Puede determinar si hay información confidencial en el informe de errores y tomar una decisión sobre si se debe enviar a Microsoft. Si decide enviarlo y la configuración de las directivas de máquina y de usuario lo permite, el compilador enviará los datos a Microsoft.|
|`queue`|Pone en cola el informe de error. Cuando inicie sesión con privilegios de administrador, puede informar de los errores desde la última vez que inició sesión (no se le pedirá que envíe informes de errores más de una vez cada tres días). Se trata del comportamiento predeterminado cuando no se especifica la opción `-errorreport`.|
|`send`|Si se produce un error interno del compilador y la configuración de las directivas de máquina y de usuario lo permite, el compilador envía los datos a Microsoft.<br /><br /> La opción `-errorreport:send` intenta enviar automáticamente información de errores a Microsoft si los informes se han habilitado en la configuración del sistema del [Informe de errores de Windows](/windows/desktop/wer/windows-error-reporting). |
|`none`|Si se produce un error interno del compilador, no se recopilará ni se enviará a Microsoft.|

El compilador envía datos que incluyen la pila en el momento del error, que normalmente incluye algún código fuente. Si se usa `-errorreport` con la opción [-bugreport](bugreport.md), se envía el archivo de origen completo.

Esta opción se utiliza mejor con la opción [-bugreport](bugreport.md), ya que permite a los ingenieros de Microsoft reproducir más fácilmente el error.

> [!NOTE]
> La opción `-errorreport` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos.

## <a name="example"></a>Ejemplo

El código siguiente intenta compilar `T2.vb` y, si el compilador encuentra un error interno del compilador, le pedirá que envíe el informe de errores a Microsoft.

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [-bugreport](bugreport.md)
