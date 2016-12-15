---
title: "Argumento no opcional (Visual Basic) | Microsoft Docs"
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
  - "vbrID449"
dev_langs: 
  - "VB"
ms.assetid: 76e7bcf3-24ed-4cd5-945b-b98f1c76944b
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Argumento no opcional (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El número y los tipos de argumentos deben coincidir con los esperados.  O hay un número incorrecto de argumentos o se ha omitido un argumento no opcional.  Un argumento sólo puede omitirse de una llamada a un procedimiento definido por el usuario si se ha declarado `Optional` en la definición de procedimiento.  
  
### Para corregir este error  
  
1.  Proporcione todos los argumentos necesarios.  
  
2.  Asegúrese de que los argumentos omitidos son opcionales.  Si no es así, proporcione el argumento en la llamada o declare el parámetro `Optional` en la definición.  
  
## Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)