---
title: "Clrver.exe (CLR Version Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Clrver.exe"
  - "CLR Version tool"
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Clrver.exe (CLR Version Tool)
La herramienta de versión de CLR \(Clrver.exe\) notifica todas las versiones instaladas de Common Language Runtime \(CLR\) en el equipo.  
  
 Esta herramienta se instala automáticamente con Visual Studio.  Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores \(o el Símbolo del sistema de Visual Studio en Windows 7\).  Para obtener más información, vea [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## Sintaxis  
  
```  
  
clrver [option]  
```  
  
## Opciones  
  
|Opción|Descripción|  
|------------|-----------------|  
|`-all`|Muestra todos los procesos del equipo que usan CLR.|  
|*pid*|Muestra las versiones de CLR que utiliza el proceso con el identificador de proceso especificado \(PID\).|  
|`-?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## Comentarios  
 Si llama a Clrver.exe sin opciones, este muestra todas las versiones instaladas de CLR.  Si se especifica un PID para otro usuario, debe tener permisos administrativos para obtener la información de versión.  
  
> [!NOTE]
>  En Windows Vista y versiones posteriores, el Control de cuentas de usuario \(UAC\) determina los privilegios de un usuario.  Si es miembro del grupo Administradores integrados, se le asignarán dos símbolos \(tokens\) de acceso en tiempo de ejecución: un símbolo \(token\) de acceso de usuario estándar y un símbolo \(token\) de acceso de administrador.  De forma predeterminada, se le asignará el rol de usuario estándar.  Para ejecutar código que requiere permisos administrativos, primero debe elevar el nivel de sus privilegios de usuario estándar a administrador.  Para ello, inicie el símbolo del sistema haciendo clic con el botón secundario en el icono de dicho símbolo e indicando que desea ejecutarlo como administrador.  
  
 Al intentar determinar la versión de CLR para los procesos SYSTEM, LOCAL SERVICE y NETWORK SERVICE aparece un mensaje que indica que el PID no existe.  
  
## Ejemplos  
 El comando siguiente muestra todas las versiones de CLR instaladas en el equipo.  
  
 `clrver`  
  
 El comando siguiente muestra la versión de CLR que usa el proceso 128.  
  
 `clrver 128`  
  
 El comando siguiente muestra todos los procesos administrados y la versión de CLR que usan.  
  
 `Clrver -all`  
  
## Vea también  
 [Tools](../../../docs/framework/tools/index.md)   
 [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)