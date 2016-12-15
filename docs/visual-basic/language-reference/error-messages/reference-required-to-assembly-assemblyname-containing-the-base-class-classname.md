---
title: "Referencia necesaria para el ensamblado &#39;&lt;nombreDeEnsamblado&gt;&#39; que contiene la clase base &#39;&lt;nombreDeClase&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30007"
  - "vbc30007"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30007"
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Referencia necesaria para el ensamblado &#39;&lt;nombreDeEnsamblado&gt;&#39; que contiene la clase base &#39;&lt;nombreDeClase&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Es necesaria una referencia para el ensamblado '\<nombreDeEnsamblado\>' que contiene la clase base '\<nombreDeClase\>'. Agregue una al proyecto.  
  
 La clase está definida en una biblioteca de vínculos dinámicos \(DLL\) o un ensamblado al que no se hace referencia directamente en el proyecto. El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] necesita una referencia para evitar la ambigüedad en caso de que la clase esté definida en más de una DLL o un ensamblado.  
  
 **Identificador de error:** BC30007  
  
### Para corregir este error  
  
-   Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.  
  
## Vea también  
 [NO ESTÁ EN LA COMPILACIÓN: Cómo: agregar o quitar referencias mediante el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project)   
 [Solucionar problemas de referencias rotas](/visual-studio/ide/troubleshooting-broken-references)