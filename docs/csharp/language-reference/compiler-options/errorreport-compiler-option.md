---
description: -errorreport (Opciones del compilador de C#)
title: -errorreport (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 6238ac392ff99d18d9cc7ea07e23b08ff235c14f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173235"
---
# <a name="-errorreport-c-compiler-options"></a>-errorreport (Opciones del compilador de C#)

Esta opción proporciona una forma cómoda de notificar un error interno del compilador de C# a Microsoft.

> [!NOTE]
> En Windows Vista y Windows Server 2008, la configuración de informes de errores para Visual Studio no reemplaza la configuración realizada a través de Informe de errores de Windows (WER). La configuración de WER siempre tiene prioridad sobre la configuración de informes de errores de Visual Studio.

## <a name="syntax"></a>Sintaxis

```console
-errorreport:{ none | prompt | queue | send }
```

## <a name="arguments"></a>Argumentos

 **Ninguna**  
 No se recopilarán informes sobre errores internos del compilador ni se enviarán a Microsoft.

 **prompt**: pregunta si desea enviar un informe cuando recibe un error interno del compilador. **prompt** es el valor predeterminado cuando se compila una aplicación en el entorno de desarrollo.

 **queue**: pone en cola el informe de error. Cuando inicia sesión con credenciales administrativas, puede notificar los errores que se han producido desde la última vez que ha iniciado sesión. No se le solicitará que envíe informes de error más de una vez cada tres días. **queue** es el valor predeterminado cuando se compila una aplicación en la línea de comandos.

 **send**: envía automáticamente informes de errores internos del compilador a Microsoft. Para habilitar esta opción, debe aceptar la directiva de recopilación de datos de Microsoft. La primera vez que especifique **-errorreport:send** en un equipo, un mensaje del compilador le remitirá a un sitio web que contiene la directiva de recopilación de datos de Microsoft.

## <a name="remarks"></a>Comentarios

 Cuando el compilador no puede procesar un archivo de código fuente, se produce un error interno del compilador (ICE). Cuando se produce un ICE, el compilador no genera un archivo de salida ni otro tipo de diagnóstico útil que pueda usar para corregir el código.

 En versiones anteriores, cuando recibía un ICE, se le recomendaba que se pusiera en contacto con los servicios de soporte técnico de Microsoft para informar del problema. Mediante el uso de **-errorreport**, puede proporcionar información sobre los ICE al equipo de Visual C#. Sus informes de error pueden ayudar a mejorar las futuras versiones del compilador.

 La capacidad de un usuario de enviar informes depende de los permisos de directiva de equipo y de usuario.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra la página **Propiedades** del proyecto. Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).

2. Haga clic en la página de propiedades de **Compilar**.

3. Haga clic en el botón **Avanzadas** .

4. Modifique la propiedad **Informe de errores internos del compilador**.

 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
