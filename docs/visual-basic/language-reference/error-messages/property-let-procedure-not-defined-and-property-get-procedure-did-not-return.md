---
title: "El procedimiento Let de la propiedad no est&#225; definido y el procedimiento Get no ha devuelto un objeto | Microsoft Docs"
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
  - "vbrID451"
dev_langs: 
  - "VB"
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El procedimiento Let de la propiedad no est&#225; definido y el procedimiento Get no ha devuelto un objeto
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Determinadas propiedades, métodos y operaciones sólo se pueden aplicar a objetos `Collection`.  Ha especificado una operación o propiedad que es exclusiva para colecciones, pero el objeto no es una colección.  
  
### Para corregir este error  
  
1.  Compruebe que ha escrito correctamente el nombre de objeto o propiedad, o compruebe que el objeto es de tipo `Collection`.  
  
2.  Busque el método `Add` utilizado para agregar el objeto a la colección a fin de asegurarse de que la sintaxis es correcta y de que ha escrito correctamente los identificadores.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Collection>