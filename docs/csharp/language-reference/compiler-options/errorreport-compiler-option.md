---
title: -errorreport (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /errorreport
dev_langs:
- CSharp
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34e7e3b8c6a9f645ec1b359095c2d289afd1370a
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="errorreport-c-compiler-options"></a>/errorreport (Opciones del compilador de C#)
Esta opción proporciona una forma cómoda de notificar un error interno del compilador de C# a Microsoft.  
  
> [!NOTE]
>  En Windows Vista y Windows Server 2008, la configuración de informes de errores para Visual Studio no reemplaza la configuración realizada a través de Informe de errores de Windows (WER). La configuración de WER siempre tiene prioridad sobre la configuración de informes de errores de Visual Studio.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a>Argumentos  
 **none**  
 No se recopilarán informes sobre errores internos del compilador ni se enviarán a Microsoft.  
  
 **prompt**  
 Pregunta si desea enviar un informe cuando recibe un error interno del compilador. **prompt** es el valor predeterminado cuando se compila una aplicación en el entorno de desarrollo.  
  
 **queue**  
 Pone en cola el informe de error. Cuando inicia sesión con credenciales administrativas, puede notificar los errores que se han producido desde la última vez que ha iniciado sesión. No se le solicitará que envíe informes de error más de una vez cada tres días. **queue** es el valor predeterminado cuando se compila una aplicación en la línea de comandos.  
  
 **send**  
 Envía automáticamente informes de errores internos del compilador a Microsoft. Para habilitar esta opción, debe aceptar la directiva de recopilación de datos de Microsoft. La primera vez que especifique **/errorreport:send** en un equipo, un mensaje del compilador le remitirá a un sitio web que contiene la directiva de recopilación de datos de Microsoft.  
  
 Esta opción depende de la configuración del Registro. Para obtener información sobre cómo establecer los valores apropiados en el Registro, vea las instrucciones sobre [cómo activar la creación automática de informes de errores en las herramientas de línea de comandos de Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695) en el sitio web de MSDN.  
  
## <a name="remarks"></a>Comentarios  
 Cuando el compilador no puede procesar un archivo de código fuente, se produce un error interno del compilador (ICE). Cuando se produce un ICE, el compilador no genera un archivo de salida ni otro tipo de diagnóstico útil que pueda usar para corregir el código.  
  
 En versiones anteriores, cuando recibía un ICE, se le recomendaba que se pusiera en contacto con los servicios de soporte técnico de Microsoft para informar del problema. Mediante el uso de **/errorreport**, puede proporcionar información sobre los ICE al equipo de Visual C#. Sus informes de error pueden ayudar a mejorar las futuras versiones del compilador.  
  
 La capacidad de un usuario de enviar informes depende de los permisos de directiva de equipo y de usuario.  
  
 Para obtener más información sobre el depurador de errores, vea [Descripción de la herramienta Dr. Watson para Windows (Drwtsn32.exe)](http://go.microsoft.com/fwlink/?LinkId=147286).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto. Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](https://docs.microsoft.com/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **Informe de errores internos del compilador**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
