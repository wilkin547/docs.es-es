---
title: "No se puede aplicar el atributo &#39;&lt;nombredeatributo&gt;&#39; m&#225;s de una vez | Microsoft Docs"
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
  - "bc30663"
  - "vbc30663"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30663"
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se puede aplicar el atributo &#39;&lt;nombredeatributo&gt;&#39; m&#225;s de una vez
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El atributo sólo puede aplicarse una vez.  El atributo `AttributeUsage` determina si un atributo puede aplicarse más de una vez.  
  
 **Identificador de error:** BC30663  
  
### Para corregir este error  
  
1.  Asegúrese de que el atributo sólo se aplica una vez.  
  
2.  Si está utilizando atributos personalizados propios, considere cambiar sus atributos `AttributeUsage` para permitir el uso de múltiples atributos, como en el ejemplo siguiente:  
  
    ```  
    <AttributeUsage(AllowMultiple := True)>  
    ```  
  
## Vea también  
 <xref:System.AttributeUsageAttribute>   
 [Crear atributos personalizados](../Topic/Creating%20Custom%20Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [AttributeUsage](../Topic/AttributeUsage%20\(C%23%20and%20Visual%20Basic\).md)