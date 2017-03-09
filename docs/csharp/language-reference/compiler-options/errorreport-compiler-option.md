---
title: "/errorreport (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/errorreport"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-errorreport compiler option [C#]"
  - "errorreport compiler option [C#]"
  - "/errorreport compiler option [C#]"
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 35
---
# /errorreport (C# Compiler Options)
Esta opción proporciona una forma cómoda de informar de un error interno del compilador de C\# a Microsoft.  
  
> [!NOTE]
>  En Windows Vista y Windows Server 2008, los valores de notificación de errores que se establecen para Visual Studio no invalidan los valores establecidos a través de Informe de errores de Windows \(WER\).  Los valores de WER siempre tienen preferencia sobre los valores de notificación de errores de Visual Studio.  
  
## Sintaxis  
  
```  
/errorreport:{ none | prompt | queue | send }  
```  
  
## Argumentos  
 **none**  
 No se recopilarán informes sobre errores internos del compilador ni se enviarán a Microsoft.  
  
 **prompt**  
 Pregunta si desea enviar un informe cuando recibe un error interno del compilador.  **prompt** es el valor predeterminado cuando una aplicación se compila en un entorno de desarrollo.  
  
 **queue**  
 Pone en cola el informe de errores.  Al iniciar sesión con credenciales de administrador, puede notificar todos los errores desde la última vez que inició una sesión.  Se le pedirá que envíe informes de errores cada tres días como máximo.  **queue** es el valor predeterminado cuando una aplicación está compilada en una línea de comandos.  
  
 **send**  
 Envía automáticamente los informes de errores internos del compilador a Microsoft.  Para habilitar esta opción, primero debe aceptar la directiva de recolección de datos de Microsoft.  La primera vez que especifique **\/errorreport:send** en un equipo, un mensaje del compilador le remitirá a un sitio web que contiene la directiva de recolección de datos de Microsoft.  
  
 Esta opción depende de la configuración del Registro.  Para obtener información sobre cómo establecer los valores adecuados en el registro, vea [Cómo activar el informe de errores automático en Visual Studio 2008 herramientas de línea de comandos](http://go.microsoft.com/fwlink/?LinkID=184695) en el sitio web de MSDN.  
  
## Comentarios  
 Un error interno del compilador \(ICE\) se produce cuando el compilador no puede procesar un archivo de código fuente.  Cuando aparece un ICE, el compilador no genera un archivo de salida ni otro tipo de diagnóstico útil que pueda utilizar para corregir el código.  
  
 En versiones anteriores, cuando el usuario recibía un ICE, se le solicitaba que se pusiera en contacto con los servicios de soporte técnico de Microsoft para notificar el problema.  Con **\/errorreport**, puede proporcionar la información de los ICE al equipo de Visual C\#.  Sus informes de errores pueden ayudar a mejorar las futuras versiones del compilador.  
  
 La capacidad de un usuario para enviar informes depende del equipo y de los permisos de la directiva del usuario.  
  
 Para obtener más información sobre el depurador de error, vea [Descripción de dr. Watson. para la herramienta de Windows \(Drwtsn32.exe\)](http://go.microsoft.com/fwlink/?LinkId=147286).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  Para obtener más información, vea [Compilar \(Página, Diseñador de proyectos\) \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Haga clic en el botón **Avanzada**.  
  
4.  Modifique la propiedad **Informe de errores internos del compilador**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)