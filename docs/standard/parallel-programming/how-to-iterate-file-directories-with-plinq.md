---
title: Procedimiento para iterar directorios con PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5da70cdca16c83b33e525aea588c02c696702ac7
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929156"
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Procedimiento para iterar directorios con PLINQ
En este ejemplo se muestran dos maneras sencillas de paralelizar operaciones en directorios de archivos. La primera consulta utiliza el método <xref:System.IO.Directory.GetFiles%2A> para rellenar una matriz de nombres de archivo en un directorio y en todos los subdirectorios. Este método no realiza ninguna devolución hasta que se rellena la matriz completa y, por lo tanto, puede presentar latencia al principio de la operación. Sin embargo, una vez que se rellena la matriz, PLINQ puede procesarla en paralelo muy rápidamente.  
  
 La segunda consulta utiliza los métodos estáticos <xref:System.IO.Directory.EnumerateDirectories%2A> y <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> que empiezan a devolver resultados inmediatamente. Este enfoque puede ser más rápido cuando recorre en iteración los árboles de directorio de gran tamaño, aunque el tiempo de procesamiento en comparación con el primer ejemplo puede depender de muchos factores.  
  
> [!WARNING]
> La finalidad de estos ejemplos es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración directorios de archivos en escenarios sencillos al tener acceso a todos los directorios del árbol, los tamaños de archivo no son muy grandes y los tiempos de acceso no son significativos. Este enfoque implica un período de latencia al principio, mientras que la matriz de nombres de archivo se está construyendo.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración directorios de archivos en escenarios sencillos al tener acceso a todos los directorios del árbol, los tamaños de archivo no son muy grandes y los tiempos de acceso no son significativos. Este enfoque comienza con la generación de resultados con más rapidez que en el ejemplo anterior.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Cuando se usa <xref:System.IO.Directory.GetFiles%2A>, asegúrese de que tiene suficientes permisos en todos los directorios del árbol. De lo contrario, se producirá una excepción y no se devolverá ningún resultado. Cuando se usa <xref:System.IO.Directory.EnumerateDirectories%2A> en una consulta PLINQ, resulta problemático controlar las excepciones de E/S de una forma correcta que le permita continuar la iteración. Si el código debe administrar E/S o excepciones de acceso no autorizado, debe considerar el enfoque descrito en [Procedimiento Iteración de directorios de archivos con la clase Parallel](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Si la latencia de E/S es un problema, por ejemplo con E/S de archivos a través de una red, considere la posibilidad de usar una de las técnicas de E/S asincrónicas descritas en [TPL y la programación asincrónica tradicional de .NET Framework](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) y en esta [entrada de blog ](https://devblogs.microsoft.com/pfxteam/parallel-extensions-and-io/).  
  
## <a name="see-also"></a>Vea también

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
