---
title: "/recurse (C# Compiler Options) | Microsoft Docs"
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
  - "/recurse"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/recurse compiler option [C#]"
  - "recurse compiler option [C#]"
  - "-recurse compiler option [C#]"
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /recurse (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción \/recurse permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado \(dir\) o del directorio del proyecto.  
  
## Sintaxis  
  
```  
/recurse:[dir\]file  
```  
  
## Argumentos  
 `dir` \(opcional\)  
 Directorio en el que se desea iniciar la búsqueda.  Si no se especifica, la búsqueda empieza en el directorio del proyecto.  
  
 `file`  
 Los archivos que se van a buscar.  Se permiten caracteres comodín.  
  
## Comentarios  
 La opción **\/recurse** permite compilar archivos de código fuente de todos los directorios secundarios del directorio especificado \(`dir`\) o del directorio del proyecto.  
  
 El nombre de archivo se puede especificar con caracteres comodín de modo que se compilen todos los archivos del directorio del proyecto que cumplan la especificación sin tener que utilizar **\/recurse**.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## Ejemplo  
 Compila todos los archivos de C\# del directorio actual:  
  
```  
csc *.cs  
```  
  
 Compila todos los archivos de C\# del directorio dir1\\dir2 y todos sus subdirectorios, y genera dir2.dll:  
  
```  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)