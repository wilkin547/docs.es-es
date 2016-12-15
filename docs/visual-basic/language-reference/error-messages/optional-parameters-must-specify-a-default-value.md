---
title: "Los par&#225;metros opcionales deben especificar un valor predeterminado | Microsoft Docs"
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
  - "vbc30812"
  - "bc30812"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30812"
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Los par&#225;metros opcionales deben especificar un valor predeterminado
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los parámetros opcionales deben proporcionar valores predeterminados que se puedan usar si algún procedimiento de llamada no indica ningún parámetro.  
  
 **Identificador de error:** BC30812  
  
### Para corregir este error  
  
-   Especifique los valores predeterminados para los parámetros opcionales; por ejemplo:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## Vea también  
 [Optional](../../../visual-basic/language-reference/modifiers/optional.md)