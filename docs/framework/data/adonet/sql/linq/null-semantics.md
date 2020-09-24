---
title: Semántica de null
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: 739ee95be45d7d64a4ad1678837b9706a533f07d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147546"
---
# <a name="null-semantics"></a>Semántica de null

En la tabla siguiente se proporcionan vínculos a varias partes de la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación donde `null` `Nothing` se tratan los problemas de (en Visual Basic).  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Desajustes de tipos entre SQL y CLR](sql-clr-type-mismatches.md)|La sección relativa a la semántica de valores NULL de este tema incluye la explicación del valor booleano de SQL de tres Estados frente al Common Language Runtime de dos Estados (CLR) <xref:System.Boolean> , el literal `Nothing` (Visual Basic) y `null` (C#), y otros problemas similares.|  
|[Traslación del operador de consulta estándar](standard-query-operator-translation.md)|La sección relativa a la semántica de valores Null de este tema describe la semántica de comparación de valores Null en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[System.String (Métodos)](system-string-methods.md)|La sección "Diferencias respecto a .NET" de este tema describe cómo un valor 0 devuelto de <xref:System.String.LastIndexOf%2A> podría significar que la cadena es nula o que la posición encontrada es 0.|  
|[Calcular la suma de valores de una secuencia numérica](compute-the-sum-of-values-in-a-numeric-sequence.md)|Describe cómo el <xref:System.Linq.Enumerable.Sum%2A> operador se evalúa como `null` ( `Nothing` en Visual Basic) en lugar de 0 para una secuencia que solo contiene valores NULL o para una secuencia vacía.|  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos y funciones](data-types-and-functions.md)
