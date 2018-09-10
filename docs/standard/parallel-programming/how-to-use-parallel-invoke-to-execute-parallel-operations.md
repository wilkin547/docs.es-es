---
title: 'Cómo: Usar Parallel.Invoke para ejecutar operaciones paralelas'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d0870d23c5606fbdd8b4a2f78c4d8b9f4ddc93e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259641"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Cómo: Usar Parallel.Invoke para ejecutar operaciones paralelas
En este ejemplo se muestra cómo paralelizar operaciones usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> en Task Parallel Library. Se realizan tres operaciones en un origen de datos compartido. Como ninguna de ellas modifica el origen, se pueden ejecutar en paralelo de manera sencilla.  
  
> [!NOTE]
>  En esta documentación, se utilizan expresiones lambda para definir delegados en la TPL. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
 [!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]  
  
 Tenga en cuenta que con <xref:System.Threading.Tasks.Parallel.Invoke%2A>, solo tiene que expresar qué acciones quiere ejecutar simultáneamente y el tiempo de ejecución controla todos los detalles de programación de los subprocesos, incluido el ajuste automático del número de núcleos en el equipo host.  
  
 En este ejemplo se paralelizan las operaciones, no los datos. Como método alternativo, puede paralelizar los consultas de LINQ mediante PLINQ y ejecutar las consultas de forma secuencial. También puede paralelizar los datos con PLINQ. Otra opción consiste en paralelizar las consultas y las tareas. Aunque la sobrecarga resultante podría reducir el rendimiento en equipos host con relativamente pocos procesadores, se ajustaría mucho mejor en equipos con varios procesadores.  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Copie y pegue el ejemplo completo en un proyecto de Microsoft Visual Studio 2010 y presione F5.  
  
## <a name="see-also"></a>Vea también

- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
- [Cancelar una tarea y los elementos secundarios](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)  
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
