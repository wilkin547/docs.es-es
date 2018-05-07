---
title: Semántica de null
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: b80d198b81e28b0fe1d0107dd04a9694c3069868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="null-semantics"></a>Semántica de null
En la tabla siguiente proporciona vínculos a distintas partes de la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación donde `null` (`Nothing` en Visual Basic) se analizan los problemas.  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Desajustes de tipos entre SQL y CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|La sección "Semántica de valores Null" de este tema incluye la descripción de los tres estados valor booleano SQL frente a common language runtime (CLR) de dos estados <xref:System.Boolean>, el literal `Nothing` (Visual Basic) y `null` (C#) y otros problemas similares.|  
|[Traslación del operador de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|La sección relativa a la semántica de valores Null de este tema describe la semántica de comparación de valores Null en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[System.String (Métodos)](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|La sección "Diferencias respecto a .NET" de este tema describe cómo un valor 0 devuelto de <xref:System.String.LastIndexOf%2A> podría significar que la cadena es nula o que la posición encontrada es 0.|  
|[Cálculo de la suma de valores de una secuencia numérica](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|Describe cómo el <xref:System.Linq.Enumerable.Sum%2A> operando se evalúa como a `null` (`Nothing` en Visual Basic) en lugar de 0 para una secuencia que solo contiene valores nulos o para una secuencia vacía.|  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
