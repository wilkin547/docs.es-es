---
title: "/moduleassemblyname | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/moduleassemblyname (opción del compilador) [Visual Basic]"
  - "moduleassemblyname (opción del compilador) [Visual Basic]"
  - "-moduleassemblyname (opción del compilador) [Visual Basic]"
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /moduleassemblyname
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica el nombre del ensamblado del que formará parte este módulo.  
  
## Sintaxis  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`assembly_name`|Nombre del ensamblado del que este módulo va a formar parte.|  
  
## Comentarios  
 El compilador procesa la opción `/moduleassemblyname` solamente si se ha especificado la opción `/target:module`.  De este modo, el compilador crea un módulo.  El módulo creado por el compilador únicamente es válido para el ensamblado especificado con la opción `/moduleassemblyname`.  Si coloca el módulo en otro ensamblado, se generarán errores en tiempo de ejecución.  
  
 Se necesita la opción `/moduleassemblyname` solamente cuando se cumplen las siguientes condiciones:  
  
-   Un tipo de datos en el módulo necesita acceso a un tipo `Friend` en un ensamblado al que se hace referencia.  
  
-   El ensamblado al que se hace referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará el módulo.  
  
 Para obtener más información sobre cómo crear un módulo, vea [\/target](../../../visual-basic/reference/command-line-compiler/target.md).  Para obtener más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
> [!NOTE]
>  La opción `/moduleassemblyname` no está disponible en el entorno de desarrollo de Visual Studio; únicamente está disponible cuando se compila desde un símbolo del sistema.  
  
## Vea también  
 [Cómo: Compilar un ensamblado de varios archivos](../Topic/How%20to:%20Build%20a%20Multifile%20Assembly.md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)