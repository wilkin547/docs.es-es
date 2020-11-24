---
title: 'Tutorial: Creación de una canalización de flujos de datos'
description: Cree una canalización de flujo de entrada, que consiste en una serie de componentes o bloques de flujo de entrada. Un bloque de flujo de entrada realiza una tarea determinada para contribuir a un objetivo mayor.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow pipelines, creating with TPL
- Task Parallel Library, dataflows
- TPL dataflow library, creating dataflow pipeline
ms.assetid: 69308f82-aa22-4ac5-833d-e748533b58e8
ms.openlocfilehash: 9469bddf381ac33b35234756d4b8538500e55c6b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829939"
---
# <a name="walkthrough-creating-a-dataflow-pipeline"></a>Tutorial: Creación de una canalización de flujos de datos
Aunque puede usar los métodos <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=nameWithType> para recibir mensajes de los bloques de origen, también puede conectar los bloques de mensajes para formar una *canalización de flujo de datos*. Una canalización de flujo datos es una serie de componentes, o *bloques de flujo de datos*, de los que cada uno realiza una tarea concreta que contribuye a lograr un objetivo mayor. Cada bloque de flujo de datos de una canalización de flujo de datos realiza un determinado trabajo cuando recibe un mensaje de otro bloque de flujo de datos. Se podría establecer una analogía de esto con una cadena de montaje en la fabricación de automóviles. Mientras cada vehículo pasa a través de la línea de montaje, una estación monta el bastidor, la siguiente instala el motor y así sucesivamente. Dado que una cadena de montaje permite montar varios vehículos al mismo tiempo, proporciona un mejor rendimiento que montar de uno en uno los vehículos completos.

 En este documento se muestra una canalización de flujo de datos que descarga el libro *La Ilíada de Homero* desde un sitio web y explora el texto para encontrar coincidencias entre palabras individuales y palabras que revierten el orden de los caracteres de la primera palabra. La formación de la canalización de flujo de datos en este documento se compone de los siguientes pasos:  
  
1. Crear los bloques de flujo de datos que participan en la canalización.  
  
2. Conectar cada bloque de flujo de datos con el siguiente bloque de la canalización. Cada bloque recibe como entrada la salida del bloque anterior de la canalización.  
  
3. Para cada bloque de flujo de datos, crear una tarea de continuación que establezca el siguiente bloque en estado completado después de que finalice el bloque anterior.  
  
4. Publicar datos en el encabezado de la canalización.  
  
5. Marcar el encabezado de la canalización como completado.  
  
6. Esperar a que la canalización complete todo el trabajo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Lea [Flujo de datos](dataflow-task-parallel-library.md) antes de empezar este tutorial.  
  
## <a name="creating-a-console-application"></a>Crear una aplicación de consola  
 En Visual Studio, cree un proyecto Aplicación de consola de Visual C# o Visual Basic. Instale el paquete NuGet System.Threading.Tasks.Dataflow.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

 Agregue el código siguiente a su proyecto para crear la aplicación básica.  
  
 [!code-csharp[TPLDataflow_Palindromes#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#2)]
 [!code-vb[TPLDataflow_Palindromes#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromesemptymain.vb#2)]  
  
## <a name="creating-the-dataflow-blocks"></a>Creación de los bloques de flujo de datos  
 Agregue el código siguiente al método `Main` para crear los bloques de flujo de datos que participan en la canalización. En la tabla siguiente se resume el rol de cada miembro de la canalización.  
  
 [!code-csharp[TPLDataflow_Palindromes#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#3)]
 [!code-vb[TPLDataflow_Palindromes#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#3)]  
  
|Miembro|Tipo|Descripción|  
|------------|----------|-----------------|  
|`downloadString`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Descarga el texto del libro desde la Web.|  
|`createWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Separa el texto del libro en una matriz de palabras.|  
|`filterWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Quita palabras cortas y duplicados de la matriz de palabras.|  
|`findReversedWords`|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>|Busca todas las palabras de la colección de matriz de palabras filtradas cuya palabra inversa también se encuentra en la matriz de palabras.|  
|`printReversedWords`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Muestra las palabras y sus correspondientes palabras inversas en la consola.|  
  
 Aunque se podrían combinar varios pasos de la canalización de flujo de datos de este ejemplo en un solo paso, en el ejemplo se muestra el concepto de componer varias tareas de flujo de datos independientes para realizar una tarea mayor. En el ejemplo se usa <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> para permitir que cada miembro de la canalización pueda realizar una operación en sus datos de entrada y enviar los resultados al siguiente paso de la canalización. El miembro `findReversedWords` de la canalización es un objeto <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> porque genera varias salidas independientes para cada entrada. El final de la canalización, `printReversedWords`, es un objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> porque realiza una acción en su entrada y no genera una salida.  
  
## <a name="forming-the-pipeline"></a>Formación de la canalización  
 Agregue el código siguiente para conectar cada bloque con el bloque siguiente en la canalización.  
  
 Cuando se llama al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> para conectar un bloque de flujo de datos de origen a un bloque de flujo de datos de destino, el bloque de origen propaga los datos al bloque de destino a medida que los datos se encuentran disponibles. Si también proporciona <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> con <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.PropagateCompletion> establecido en true, la finalización correcta o incorrecta de un bloque de la canalización conllevará la finalización del siguiente bloque de la canalización.
  
 [!code-csharp[TPLDataflow_Palindromes#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#4)]
 [!code-vb[TPLDataflow_Palindromes#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#4)]  
  
## <a name="posting-data-to-the-pipeline"></a>Envío de datos a la canalización  
 Agregue el código siguiente para publicar la dirección URL del libro *La Ilíada de Homero* en el encabezado de la canalización de flujo de datos.  
  
 [!code-csharp[TPLDataflow_Palindromes#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#6)]
 [!code-vb[TPLDataflow_Palindromes#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#6)]  
  
 En este ejemplo se usa <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=nameWithType> para enviar datos de forma sincrónica al encabezado de la canalización. Use el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=nameWithType> cuando deba enviar datos de forma asincrónica a un nodo de flujo de datos.  
  
## <a name="completing-pipeline-activity"></a>Finalización de la actividad de canalización  
 Agregue el código siguiente para marcar el encabezado de la canalización como completado. El encabezado de la canalización propaga su finalización después de procesar todos los mensajes almacenados en búfer.
  
 [!code-csharp[TPLDataflow_Palindromes#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#7)]
 [!code-vb[TPLDataflow_Palindromes#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#7)]  
  
 En este ejemplo se envía una dirección URL a través de la canalización de flujo de datos para que se procese. Si envía más de una entrada a través de una canalización, llame al método <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=nameWithType> después de enviar toda la entrada. Puede omitir este paso si la aplicación no tiene ningún punto bien definido en el que los datos ya no están disponibles o la aplicación no tiene que esperar a que finalice la canalización.  
  
## <a name="waiting-for-the-pipeline-to-finish"></a>Espera para la finalización de la canalización  
 Agregue el código siguiente para esperar a que finalice la canalización. La operación global termina cuando finaliza la cola de la canalización.  
  
 [!code-csharp[TPLDataflow_Palindromes#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#8)]
 [!code-vb[TPLDataflow_Palindromes#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#8)]  
  
 Puede esperar la finalización del flujo de datos desde cualquier subproceso o desde varios subprocesos al mismo tiempo.  
  
## <a name="the-complete-example"></a>Ejemplo completo  
 En el ejemplo siguiente se muestra el código completo de este tutorial.  
  
 [!code-csharp[TPLDataflow_Palindromes#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#1)]
 [!code-vb[TPLDataflow_Palindromes#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#1)]  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este ejemplo se envía una dirección URL para procesarla a través de la canalización de flujo de datos. Si envía más de un valor de entrada a través de una canalización, puede introducir un formulario de paralelismo en la aplicación que se parezca a cómo se moverían las piezas en una fábrica de automóviles. Cuando el primer miembro de la canalización envía su resultado al segundo miembro, puede procesar otro elemento en paralelo mientras el segundo miembro procesa el primer resultado.  
  
 El paralelismo que se logra mediante el uso de canalizaciones de flujo de datos se conoce como *paralelismo general* porque normalmente consta de menos tareas y más grandes. También puede usar un *paralelismo específico* de tareas más pequeñas y breves en una canalización de flujo de datos. En este ejemplo, el miembro `findReversedWords` de la canalización usa [PLINQ](introduction-to-plinq.md) para procesar en paralelo varios elementos de la lista de trabajo. El uso de paralelismo de grano fino en una canalización de grano grueso puede mejorar el rendimiento global.  
  
 También puede conectar un bloque de flujo de datos de origen a varios bloques de destino para crear una *red de flujo de datos*. La versión sobrecargada del método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> toma un objeto <xref:System.Predicate%601> que define si el bloque de destino acepta cada mensaje según su valor. La mayoría de los tipos de bloques de flujo de datos que actúan como orígenes ofrecen mensajes a todos los bloques de destino conectados, siguiendo el orden en que se conectaron, hasta que uno de los bloques acepta ese mensaje. Mediante este mecanismo de filtrado, puede crear sistemas de bloques de flujo de datos conectados que dirigen determinados datos a través de una ruta de acceso y otros datos a través de otra ruta de acceso. Para ver un ejemplo que usa el filtrado para crear una red de flujo de datos, consulte [Tutorial: Uso de flujos de datos en aplicaciones de Windows Forms](walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Vea también

- [Flujo de datos](dataflow-task-parallel-library.md)
