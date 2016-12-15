---
title: "El ordinal no es v&#225;lido | Microsoft Docs"
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
  - "vbrID452"
dev_langs: 
  - "VB"
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El ordinal no es v&#225;lido
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La llamada a la biblioteca de vínculos dinámicos \(DLL\) indica el uso de un número en lugar de un nombre de procedimiento, con la sintaxis `#num`.  Este error tiene las causas posibles siguientes:  
  
-   Error al intentar convertir la expresión `#num` en un ordinal.  
  
-   La expresión `#num` indicada no especifica ninguna función en el archivo DLL.  
  
-   La biblioteca de tipos posee una declaración no válida lo que produce el uso interno de un número ordinal no válido.  
  
### Para corregir este error  
  
1.  Asegúrese de que la expresión representa un número válido o llame al procedimiento por nombre.  
  
2.  Asegúrese de que `#num` identifica una función válida en la DLL.  
  
3.  Aísle la llamada a procedimiento que ha originado el problema escribiéndola como comentario del código.  Escriba una instrucción `Declare` para el procedimiento e informe del problema al proveedor de la biblioteca de tipos.  
  
## Vea también  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)