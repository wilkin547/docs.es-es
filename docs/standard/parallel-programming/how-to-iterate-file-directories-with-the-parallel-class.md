---
title: "Cómo: Recorrer en iteración directorios con la clase paralela"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3ac1af7922e1bbd81f4dfcee256f5c8892294003
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a>Cómo: Recorrer en iteración directorios con la clase paralela
En muchos casos, la iteración de archivo es una operación que se puede paralelizar fácilmente. El tema [Cómo: Recorrer en iteración directorios con PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) muestra la manera más fácil de realizar esta tarea para muchos escenarios. Sin embargo, pueden surgir complicaciones cuando el código tiene que tratar con los muchos tipos de excepciones que pueden surgir al obtener acceso al sistema de archivos. En el ejemplo siguiente se muestra un enfoque para el problema. Usa una iteración basada en la pila para recorrer todos los archivos y carpetas en un directorio especificado y habilita el código para detectar y controlar diversas excepciones. Por supuesto, la forma de controlar las excepciones depende de usted.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se recorren los directorios secuencialmente, pero se procesan los archivos en paralelo. Este enfoque es probablemente el mejor cuando hay una tasa alta de directorios y archivos. También es posible ejecutar la iteración de directorio y obtener acceso a cada archivo secuencialmente. Probablemente no es eficaz paralelizar ambos bucles a menos que esté dirigido específicamente a un equipo con un gran número de procesadores. Sin embargo, como en todos los casos, se debe probar exhaustivamente la aplicación para determinar el mejor enfoque.  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 En este ejemplo, la E/S de archivo se realiza de forma sincrónica. Al trabajar con archivos grandes o conexiones de red lentas, puede ser preferible obtener acceso a los archivos de forma asincrónica. Puede combinar las técnicas de E/S asincrónica con la iteración paralela. Para más información, consulte [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) (TPL y la programación asincrónica tradicional de .NET).  
  
 El ejemplo utiliza la variable local `fileCount` para mantener un número total de archivos procesados. Dado que varias tareas podrían tener acceso simultáneamente a la variable, el acceso a la misma se sincroniza llamando al método <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>.  
  
 Tenga en cuenta que si se produce una excepción en el subproceso principal, los subprocesos que inicia el método <xref:System.Threading.Tasks.Parallel.ForEach%2A> podrían seguir ejecutándose. Para detener estos subprocesos, puede establecer una variable booleana en los controladores de excepciones y comprobar su valor en cada iteración del bucle paralelo. Si el valor indica que se ha iniciado una excepción, use la variable <xref:System.Threading.Tasks.ParallelLoopState> para detener o interrumpir el bucle. Para más información, vea [Cómo: Detener o interrumpir un bucle Parallel.For](http://msdn.microsoft.com/library/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e).  
  
## <a name="see-also"></a>Vea también  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)
