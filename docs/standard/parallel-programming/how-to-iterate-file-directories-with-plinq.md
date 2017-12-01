---
title: "Cómo: Recorrer en iteración directorios con PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40fd9f64b5702f5205b7817f3de1e0a8709c5a63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Cómo: Recorrer en iteración directorios con PLINQ
En este ejemplo se muestra dos maneras sencillas para paralelizar operaciones en directorios de archivos. La primera consulta utiliza la <xref:System.IO.Directory.GetFiles%2A> método para rellenar una matriz de nombres de archivo en un directorio y todos los subdirectorios. Este método no devuelve hasta que se rellena la matriz completa y, por lo tanto, puede presentar latencia al principio de la operación. Sin embargo, una vez que se rellene la matriz, PLINQ puede procesarlo en paralelo muy rápidamente.  
  
 La segunda consulta utiliza el método estático <xref:System.IO.Directory.EnumerateDirectories%2A> y <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> métodos que empezar a devolver resultados inmediatamente. Este enfoque puede ser más rápida cuando recorre en iteración los árboles de directorio de gran tamaño, aunque el tiempo de procesamiento en comparación con el primer ejemplo puede depende de muchos factores.  
  
> [!WARNING]
>  Estos ejemplos están diseñados para mostrar el uso y podrían no ejecutarse más rápido que LINQ secuencial equivalente para consultar objetos. Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración directorios de archivos en escenarios sencillos al tener acceso a todos los directorios en el árbol, los tamaños de archivo no son muy grandes y los tiempos de acceso no son significativos. Este enfoque implica un período de latencia al principio, mientras que la matriz de nombres de archivo se está construyendo.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración directorios de archivos en escenarios sencillos al tener acceso a todos los directorios en el árbol, los tamaños de archivo no son muy grandes y los tiempos de acceso no son significativos. Este enfoque comienza producen resultados más rápido que el ejemplo anterior.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Cuando se usa <xref:System.IO.Directory.GetFiles%2A>, asegúrese de que tiene suficientes permisos en todos los directorios en el árbol. De lo contrario se producirá una excepción y no se devolverá ningún resultado. Cuando se usa el <xref:System.IO.Directory.EnumerateDirectories%2A> en una consulta PLINQ, resulta problemática para controlar las excepciones de E/S de forma correcta que le permite continuar la iteración. Si el código debe administrar E/S o las excepciones de acceso no autorizado, debe considerar el enfoque descrito en [Cómo: recorrer en iteración directorios con la clase Parallel](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Si la latencia de E/S es un problema, por ejemplo con E/S de archivos a través de una red, considere el uso de una de las técnicas de E/S asincrónicas se describe en [TPL y .NET Framework programación asincrónica tradicional de](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) y en este [entrada de blog ](http://go.microsoft.com/fwlink/?LinkID=186458).  
  
## <a name="see-also"></a>Vea también  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
