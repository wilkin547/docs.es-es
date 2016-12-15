---
title: "La expresi&#243;n tiene el tipo &#39;&lt;nombreDeTipo&gt;&#39; que es un tipo restringido y no se puede utilizar para obtener acceso a miembros heredados de &#39;Object&#39; o &#39;ValueType&#39; | Microsoft Docs"
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
  - "bc31393"
  - "vbc31393"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31393"
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La expresi&#243;n tiene el tipo &#39;&lt;nombreDeTipo&gt;&#39; que es un tipo restringido y no se puede utilizar para obtener acceso a miembros heredados de &#39;Object&#39; o &#39;ValueType&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una expresión que se evalúa como un tipo al que Common Language Runtime \(CLR\) no puede aplicar la conversión boxing, obtiene acceso a un miembro que requiere la conversión boxing.  
  
 La *conversión boxing* hace referencia al procesamiento necesario para convertir un tipo en `Object` o, a veces, en <xref:System.ValueType>.  Common Language Runtime no puede aplicar la conversión boxing a ciertos tipos de estructura, por ejemplo <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle> y <xref:System.TypedReference>.  
  
 Esta expresión intenta utilizar el tipo restringido para llamar a un método heredado de <xref:System.Object> o <xref:System.ValueType>, como <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>.  Para obtener acceso a este método, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ha intentado una conversión boxing implícita que produce este error.  
  
 **Identificador de error:** BC31393  
  
### Para corregir este error  
  
1.  Busque la expresión que se evalúa como el tipo mencionado.  
  
2.  Busque el apartado de su instrucción que intenta llamar al método heredado de <xref:System.Object> o <xref:System.ValueType>.  
  
3.  Vuelva a escribir la instrucción para evitar la llamada al método.  
  
## Vea también  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)