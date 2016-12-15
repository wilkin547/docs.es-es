---
title: "How to: Set Environment Variables for the Visual Studio Command Line | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.build.commandline"
dev_langs: 
  - "CSharp"
  - "CSharp"
helpviewer_keywords: 
  - "csc.exe, command-line builds"
  - "Visual C#, command-line builds"
  - "command-line compilers, Visual C#"
  - "Vsvars32.bat"
  - "builds [C#], command-line"
  - "compilers, invoking from command line"
  - "Vcvars32.bat file"
  - "command line [C#], building from"
  - "Visual C# compiler, enabling"
  - "compiling source code, from command line"
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# How to: Set Environment Variables for the Visual Studio Command Line
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El archivo vsvars32.bat establece las variables de entorno apropiadas para habilitar compilaciones desde la línea de comandos.  Para obtener más información sobre vsvars32.bat, vea el [artículo Q248802 de Knowledge Base](http://go.microsoft.com/fwlink/?LinkId=225042).  
  
 Si se instala la versión actual de Visual Studio en un equipo que también tiene una versión anterior de Visual Studio, no se deben ejecutar los archivos vsvars32.bat o vcvars32.bat de versiones diferentes en la misma ventana del símbolo del sistema.  
  
### Para ejecutar VSVARS32.BAT  
  
1.  En el menú **Inicio**, abra el **Símbolo del sistema para desarrolladores de VS2012**.  
  
2.  Cambie al subdirectorio Archivos de programa\\Microsoft Visual Studio *Version*\\Common7\\Tools o Archivos de programa \(x86\)\\Microsoft Visual Studio *Version*\\Common7\\Tools de la instalación.  
  
3.  Escriba VSVARS32 para ejecutar VSVARS32.bat.  
  
    > [!CAUTION]
    >  VSVARS32.bat puede ser diferente en equipos distintos.  No debe reemplazar un archivo VSVARS32.bat dañado o inexistente por el archivo VSVARS32.bat de otro equipo.  En su lugar, vuelva a ejecutar el programa de instalación para reemplazar el archivo que falta.  
  
## Vea también  
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)