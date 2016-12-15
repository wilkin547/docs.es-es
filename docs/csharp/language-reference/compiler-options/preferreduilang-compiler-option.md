---
title: "/preferreduilang (C# Compiler Options) | Microsoft Docs"
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
  - "/preferreduilang"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "preferreduilang compiler option [C#]"
  - "/preferreduilang compiler option [C#]"
  - "-preferreduilang compiler option [C#]"
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /preferreduilang (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Mediante la opción del compilador `/preferreduilang` , puede especificar el lenguaje en el que la salida del compilador de C\#, como los mensajes de error.  
  
## Sintaxis  
  
```  
/preferreduilang: language  
```  
  
## Argumentos  
 `language`  
 [nombre del lenguaje](http://go.microsoft.com/fwlink/p/?LinkId=236992) De lenguaje para los resultados del compilador.  
  
## Comentarios  
 Puede utilizar la opción del compilador `/preferreduilang` de especificar el idioma que desea que el compilador de C\# para utilizar para los mensajes de error y la otra salida desde la línea de comandos.  Si el paquete de idioma para el lenguaje no está instalado, la configuración de idioma del sistema operativo se utiliza en su lugar, y no se notifica ningún error.  
  
```c#  
csc.exe /preferreduilang:ja-JP  
```  
  
## Requisitos  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)