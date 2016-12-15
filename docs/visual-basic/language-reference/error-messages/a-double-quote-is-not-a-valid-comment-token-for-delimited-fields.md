---
title: "Un car&#225;cter de comilla doble no es un s&#237;mbolo (token) de comentario v&#225;lido para campos delimitados donde EscapeQuote est&#225; establecido en True | Microsoft Docs"
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
  - "vbrTextFieldParser_InvalidComment"
dev_langs: 
  - "VB"
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Un car&#225;cter de comilla doble no es un s&#237;mbolo (token) de comentario v&#225;lido para campos delimitados donde EscapeQuote est&#225; establecido en True
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se proporcionó una comilla como delimitador para `TextFieldParser`, pero `EscapeQuotes` está establecido en `True`.  
  
### Para corregir este error  
  
-   Establezca `EscapeQuotes` en `False`.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 [Cómo: Leer archivos de texto delimitado por comas](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)