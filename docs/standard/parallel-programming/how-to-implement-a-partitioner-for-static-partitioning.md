---
title: 'Cómo: Implementar un particionador para particionamiento estático'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
ms.openlocfilehash: 22d2cf788d4726488512703356a75f84efd04250
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278511"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Cómo: Implementar un particionador para particionamiento estático
En el ejemplo siguiente se muestra una forma de implementar un particionador personalizado sencillo para PLINQ que realiza una partición estática. Dado que el particionador no admite las particiones dinámicas, no se puede usar desde <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Este particionador particular puede proporcionar velocidad con respecto al particionador por rangos predeterminado para los orígenes de datos, para los que cada elemento requieren una cantidad creciente de tiempo de procesamiento.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Las particiones de este ejemplo se basan en el supuesto de un aumento lineal del tiempo de procesamiento de cada elemento. En el mundo real, puede que sea difícil predecir los tiempos de procesamiento de esta manera. Si usa un particionador estático con un origen de datos específico, puede optimizar la fórmula de partición del origen, agregar la lógica de equilibrio de carga o usar un enfoque de partición por fragmentos, como se explica en [Cómo: Implementar las particiones dinámicas](how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>Vea también

- [Particionadores personalizados para PLINQ y TPL](custom-partitioners-for-plinq-and-tpl.md)
