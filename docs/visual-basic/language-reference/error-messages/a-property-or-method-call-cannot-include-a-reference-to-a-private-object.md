---
title: "Una llamada a una propiedad o un m&#233;todo no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID98"
dev_langs: 
  - "VB"
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Una llamada a una propiedad o un m&#233;todo no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Entre las causas posibles de este error se incluyen:  
  
-   Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.  
  
-   Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.  
  
-   Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.  
  
-   Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.  
  
### Para corregir este error  
  
1.  Quite la referencia.  
  
## Vea también  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)