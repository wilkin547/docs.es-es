---
title: "Semántica de null"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8d32f73c8c2095c23ec164ad40fd1ab27ef1153a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="null-semantics"></a>Semántica de null
La tabla siguiente proporciona vínculos a varias partes de la documentación de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] donde se analizan los problemas de valores `null` (`Nothing` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]).  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Desajustes de tipos entre SQL y CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|La sección relativa a la semántica de valores Null de este tema analiza el valor booleano SQL de tres estados frente al objeto <xref:System.Boolean>de dos estados de Common Language Runtime (CLR), los valores literales `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) y `null` (C#), y otros problemas similares.|  
|[Traslación del operador de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|La sección relativa a la semántica de valores Null de este tema describe la semántica de comparación de valores Null en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[System.String (Métodos)](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|La sección "Diferencias respecto a .NET" de este tema describe cómo un valor 0 devuelto de <xref:System.String.LastIndexOf%2A> podría significar que la cadena es nula o que la posición encontrada es 0.|  
|[Cálculo de la suma de valores de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|Describe cómo el operador <xref:System.Linq.Enumerable.Sum%2A> se evalúa como `null` (`Nothing` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) en lugar de 0 para una secuencia que solo contiene valores nulos o para una secuencia vacía.|  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
