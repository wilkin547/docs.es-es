---
title: "N&#250;mero de registro incorrecto | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID63"
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# N&#250;mero de registro incorrecto
El número de registro de la instrucción `a FileGet`, `FilePut`, `FileGetObject` o `FilePutObject` es menor o igual que cero.  
  
### Para corregir este error  
  
1.  Compruebe los cálculos usados para generar el número de registro. Compruebe la ortografía de las variables que contienen el número de registro o usadas para calcular números de registro. Un nombre de variable mal escrito se declara implícitamente y se inicializa en cero, a menos que use `Option Explicit On` en el módulo.  
  
## Vea también  
 [Option Explicit \(Instrucción\)](../../visual-basic/language-reference/statements/option-explicit-statement.md)