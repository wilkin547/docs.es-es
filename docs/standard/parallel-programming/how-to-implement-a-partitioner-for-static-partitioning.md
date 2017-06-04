---
title: "How to: Implement a Partitioner for Static Partitioning | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, how to create a static partitioner"
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Implement a Partitioner for Static Partitioning
En el siguiente ejemplo se muestra una manera de implementar un particionador personalizado simple para PLINQ que realiza la creación de particiones estáticas.  Dado que el particionador no admite las particiones dinámicas, no se puede usar de <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>.  Este particionador determinado podría proporcionar más velocidad que el particionador del intervalo predeterminado para los orígenes de datos en los que cada elemento requiere una cantidad creciente de tiempo de proceso.  
  
## Ejemplo  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Las particiones de este ejemplo están basadas en la hipótesis de un aumento lineal del tiempo de proceso por cada elemento.  En la práctica, podría ser difícil predecir los tiempos de proceso de esta manera.  Si está utilizando un particionador estático con un origen de datos concreto, puede optimizar la fórmula de creación de particiones del origen, agregar lógica de equilibrio de carga o emplear un enfoque de creación de particiones de los fragmentos, como se muestra en [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## Vea también  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)