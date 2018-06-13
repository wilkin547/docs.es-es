---
title: Agrupar resultados por claves contiguas
description: Cómo agrupar resultados por claves contiguas.
ms.date: 12/1/2016
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: a8d6ac133932a12154d5b23454065144c7652067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281442"
---
# <a name="group-results-by-contiguous-keys"></a>Agrupar resultados por claves contiguas

En el ejemplo siguiente se muestra cómo agrupar elementos en fragmentos que representan subsecuencias de claves contiguas. Por ejemplo, suponga que tiene la siguiente secuencia de pares clave-valor:  
  
|Key|Valor|  
|---------|-----------|  
|A|We|  
|A|think|  
|A|that|  
|B|Linq|  
|C|is|  
|A|really|  
|B|cool|  
|B|!|  
  
 Los siguientes grupos se crearán en este orden:  
  
1.  We, think, that  
  
2.  Linq  
  
3.  is  
  
4.  really  
  
5.  cool, !  
  
 La solución se implementa como un método de extensión seguro para subprocesos que devuelve sus resultados mediante transmisión por secuencias. Es decir, genera sus grupos a medida que se desplaza por la secuencia de origen. A diferencia de los operadores `group` u `orderby`, puede comenzar a devolver grupos al llamador antes de que se haya leído toda la secuencia.  
  
 La seguridad de subprocesos se logra realizando una copia de cada grupo o fragmento a medida que se recorre en iteración la secuencia de origen, tal y como se explica en los comentarios del código fuente. Si la secuencia de origen tiene una secuencia grande de elementos contiguos, Common Language Runtime puede producir una excepción <xref:System.OutOfMemoryException>.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestran el método de extensión y el código de cliente que lo usa.  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 Para usar el método de extensión en el proyecto, copie la clase estática `MyExtensions` en un archivo de código fuente nuevo o ya existente y, si es necesario, agregue una directiva `using` para el espacio de nombres donde se encuentra.  
  
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)  
 
