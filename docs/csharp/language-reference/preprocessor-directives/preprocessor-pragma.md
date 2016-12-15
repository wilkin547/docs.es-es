---
title: "#pragma (Referencia de C#) | Microsoft Docs"
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
  - "#pragma"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma (directiva) [C#]"
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #pragma (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#pragma` proporciona instrucciones especiales al compilador para la compilación del archivo en el que aparece.  Las instrucciones deben ser compatibles con el compilador.  Es decir, no puede utilizar `#pragma` para crear instrucciones de preprocesamiento personalizadas.  El compilador de Microsoft C\# admite las dos instrucciones `#pragma` siguientes:  
  
 [\#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [Suma de comprobación \#pragma](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## Sintaxis  
  
```  
#pragma pragma-name pragma-arguments  
```  
  
#### Parámetros  
 `pragma-name`  
 El nombre de una directiva pragma reconocida.  
  
 `pragma-arguments`  
 Argumentos específicos del pragma.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [\#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)   
 [Suma de comprobación \#pragma](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)