---
title: Procedimiento para iterar directorios con PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
ms.openlocfilehash: abf31ea69af6a85140efb783959a9a586ef6a59e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278004"
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Procedimiento para iterar directorios con PLINQ

En este artículo se muestran dos maneras de paralelizar operaciones en directorios de archivos. La primera consulta utiliza el método <xref:System.IO.Directory.GetFiles%2A> para rellenar una matriz de nombres de archivo en un directorio y en todos los subdirectorios. Este método puede generar latencia al principio de la operación porque no realiza ninguna devolución hasta que se rellena toda la matriz. Sin embargo, una vez que se rellena la matriz, PLINQ puede procesarla en paralelo rápidamente.  
  
La segunda consulta utiliza los métodos estáticos <xref:System.IO.Directory.EnumerateDirectories%2A> y <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, que empiezan a devolver resultados inmediatamente. Este enfoque puede ser más rápido cuando esté iterando los árboles de directorio de gran tamaño, pero el tiempo de procesamiento en comparación con el primer ejemplo depende de muchos factores.  
  
> [!NOTE]
> La finalidad de estos ejemplos es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="getfiles-example"></a>Ejemplo de GetFiles

 En el ejemplo siguiente se muestra cómo iterar directorios de archivos en escenarios sencillos cuando se tiene acceso a todos los directorios del árbol, los tamaños de archivo no son grandes y los tiempos de acceso no son significativos. Este enfoque implica un período de latencia al principio, mientras que la matriz de nombres de archivo se está construyendo.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="enumeratefiles-example"></a>Ejemplo de EnumerateFiles

 En el ejemplo siguiente se muestra cómo iterar directorios de archivos en escenarios sencillos cuando se tiene acceso a todos los directorios del árbol, los tamaños de archivo no son grandes y los tiempos de acceso no son significativos. Este enfoque comienza con la generación de resultados con más rapidez que en el ejemplo anterior.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Cuando se usa <xref:System.IO.Directory.GetFiles%2A>, asegúrese de que tiene suficientes permisos en todos los directorios del árbol. De lo contrario, se producirá una excepción y no se devolverá ningún resultado. Cuando se usa <xref:System.IO.Directory.EnumerateDirectories%2A> en una consulta PLINQ, resulta problemático controlar las excepciones de E/S de una forma correcta que le permita continuar la iteración. Si el código debe administrar E/S o excepciones de acceso no autorizado, debe considerar el enfoque descrito en [Procedimiento Iteración de directorios de archivos con la clase Parallel](how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Si la latencia de E/S es un problema, por ejemplo con E/S de archivos a través de una red, considere la posibilidad de usar una de las técnicas de E/S asincrónicas descritas en [TPL y la programación asincrónica tradicional de .NET Framework](tpl-and-traditional-async-programming.md) y en esta [entrada de blog ](https://devblogs.microsoft.com/pfxteam/parallel-extensions-and-io/).  
  
## <a name="see-also"></a>Vea también

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
