---
title: "Longitud de registro incorrecta | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID59"
dev_langs: 
  - "VB"
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Longitud de registro incorrecta
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Entre las causas posibles de este error están:  
  
-   La longitud de una variable de registro especificada en una instrucción `FileGet`, `FileGetObject`, `FilePut` o `FilePutObject` es distinta de la longitud especificada en la instrucción `FileOpen` correspondiente.  
  
-   La variable de una instrucción `FilePut` o `FilePutObject` es o incluye una cadena de longitud variable.  
  
-   La variable de una instrucción `FilePut` o `FilePutObject` es o incluye un tipo `Variant`**.**.  
  
### Para corregir este error  
  
1.  Asegúrese de que la suma de los tamaños de las variables de longitud fija del tipo definido por el usuario que define el tipo de variable de registro es la misma que el valor establecido en la cláusula `Len` de la instrucción `FileOpen`.  
  
2.  Si la variable de una instrucción `FilePut` o `FilePutObject` es o incluye una cadena de longitud variable, asegúrese de que la cadena de longitud variable tiene al menos 2 caracteres menos que la longitud del registro especificada en la cláusula `Len` de la instrucción `FileOpen`.  
  
3.  Si la variable de una instrucción `FilePut` o `FilePutObject` es o incluye un tipo `Variant` asegúrese de que la cadena de longitud variable tiene al menos 4 bytes menos que la longitud del registro especificada en la cláusula `Len` de la instrucción `FileOpen`.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>