---
title: Agrupar resultados por claves contiguas
description: "Cómo agrupar resultados por claves contiguas."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ddd028a3aad5186ef6773b32e9f9e8e1cbff95fc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="group-results-by-contiguous-keys"></a>Agrupar resultados por claves contiguas

En el ejemplo siguiente se muestra cómo agrupar elementos en fragmentos que representan subsecuencias de claves contiguas. Por ejemplo, suponga que tiene la siguiente secuencia de pares clave-valor:  
  
|Clave|Valor|  
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
  
 [!code-cs[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 Para usar el método de extensión en el proyecto, copie la clase estática `MyExtensions` en un archivo de código fuente nuevo o ya existente y, si es necesario, agregue una directiva `using` para el espacio de nombres donde se encuentra.  
  
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)   
 

