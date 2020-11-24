---
title: Procedimiento para usar Parallel.Invoke para ejecutar operaciones en paralelo
description: Vea cómo usar el método Parallel.Invoke en la biblioteca TPL, que realiza operaciones paralelas en un origen de datos compartido en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 6ec8f03216cc6225e909f5dc3128469047826166
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825486"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Procedimiento para usar Parallel.Invoke para ejecutar operaciones en paralelo

En este ejemplo se muestra cómo paralelizar operaciones usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> en Task Parallel Library. Se realizan tres operaciones en un origen de datos compartido. Las operaciones se pueden ejecutar en paralelo de manera sencilla, ya que ninguna de ellas modifica el origen.

> [!NOTE]
> En esta documentación, se utilizan expresiones lambda para definir delegados en la TPL. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, vea [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md).

## <a name="example"></a>Ejemplo

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

Con <xref:System.Threading.Tasks.Parallel.Invoke%2A>, solo tiene que expresar qué acciones quiere ejecutar simultáneamente y el tiempo de ejecución controla todos los detalles de programación de los subprocesos, incluido el ajuste automático del número de núcleos en el equipo host.

En este ejemplo se paralelizan las operaciones, no los datos. Como método alternativo, puede paralelizar los consultas de LINQ mediante PLINQ y ejecutar las consultas de forma secuencial. También puede paralelizar los datos con PLINQ. Otra opción consiste en paralelizar las consultas y las tareas. Aunque la sobrecarga resultante podría reducir el rendimiento en equipos host con relativamente pocos procesadores, se ajusta mejor en equipos con varios procesadores.

## <a name="compile-the-code"></a>Compilar el código

Copie y pegue el ejemplo completo en un proyecto de Microsoft Visual Studio y presione **F5**.

## <a name="see-also"></a>Vea también

- [Programación en paralelo](index.md)
- [Cómo: Cancelar una tarea y sus elementos secundarios](how-to-cancel-a-task-and-its-children.md)
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
