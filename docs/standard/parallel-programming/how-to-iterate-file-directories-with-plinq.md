---
title: "How to: Iterate File Directories with PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PLINQ queries, how to iterate directories"
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Iterate File Directories with PLINQ
En este ejemplo se muestran dos maneras sencillas de paralelizar las operaciones en los directorios de archivos.  En la primera consulta se usa el método <xref:System.IO.Directory.GetFiles%2A> para rellenar una matriz de nombres de archivo en un directorio y todos los subdirectorios.  Este método no devuelve ningún valor hasta que se rellena la matriz completa y, por consiguiente, puede presentar la latencia al principio de la operación.  Sin embargo, una vez que se rellena la matriz, PLINQ puede procesarla en paralelo muy rápidamente.  
  
 En la segunda consulta se usan los métodos estáticos <xref:System.IO.Directory.EnumerateDirectories%2A> y <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, que empiezan a devolver resultados inmediatamente.  Este enfoque puede ofrecer mayor velocidad cuando se itera en árboles de directorios grandes, aunque, en comparación con el primer ejemplo, el tiempo de procesamiento puede depender de muchos factores.  
  
> [!WARNING]
>  Estos ejemplos se han diseñado para mostrar el uso y podrían no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  Para obtener más información sobre la aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo iterar en los directorios de archivos en escenarios simples cuando se tiene acceso a todos los directorios en el árbol, los tamaños de archivo no son muy grandes y los tiempos de acceso no son significativos.  Este enfoque implica un período de latencia al principio mientras la matriz de nombres de archivo se construye.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo iterar en los directorios de archivos en escenarios simples cuando se tiene acceso a todos los directorios en el árbol, los tamaños de archivo no son muy grandes y los tiempos de acceso no son significativos.  Este enfoque empieza a producir resultados más rápidamente que el ejemplo anterior.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Al usar <xref:System.IO.Directory.GetFiles%2A>, asegúrese de que tiene permisos suficientes en todos los directorios del árbol.  De lo contrario, se producirá una excepción y no se devolverá ningún resultado.  Al usar <xref:System.IO.Directory.EnumerateDirectories%2A> en una consulta PLINQ, es problemático controlar las excepciones de E\/S de una forma correcta que permita continuar con la iteración.  Si el código debe controlar las excepciones de E\/S o de acceso no autorizado, debe considerar el enfoque descrito en [Cómo: Recorrer en iteración directorios con la clase paralela](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Si la latencia de E\/S es un problema, por ejemplo con E\/S de archivo de una red, considere utilizar una de las técnicas de E\/S asincrónicas descritas en [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) y en este [entrada de blog](http://go.microsoft.com/fwlink/?LinkID=186458).  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)