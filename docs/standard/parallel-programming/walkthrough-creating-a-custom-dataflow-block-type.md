---
title: 'Tutorial: Crear tipos de bloques de flujos de datos personalizados'
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
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 809b21fa6e1470890011604792d849998dd03ede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>Tutorial: Crear tipos de bloques de flujos de datos personalizados
Aunque la biblioteca de flujo de datos TPL proporciona varios tipos de bloques de flujo de datos que permiten una variedad de funciones, también puede crear tipos de bloque personalizado. Este documento describe cómo crear un tipo de bloque de flujo de datos que implementa un comportamiento personalizado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Lectura [flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) antes de leer este documento.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.  
  
## <a name="defining-the-sliding-window-dataflow-block"></a>Definir el bloque de flujo de ventana deslizante  
 Considere la posibilidad de una aplicación de flujo de datos que requiere que los valores de entrada se almacenan en búfer y de salida, a continuación, en un estilo de ventana deslizante. Por ejemplo y un tamaño de ventana de tres de los valores de entrada {0, 1, 2, 3, 4, 5}, un bloque de flujo de ventana deslizante genera las matrices de salida {0, 1, 2}, {1, 2, 3}, {2, 3, 4} y {3, 4, 5}. Las siguientes secciones describen dos formas de crear un tipo de bloque de flujo de datos que implementa este comportamiento personalizado. La primera técnica utiliza el <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> método para combinar la funcionalidad de un <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objeto y un <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> objeto en bloque uno propagador. La segunda técnica define una clase que deriva de <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> y combina la funcionalidad existente para llevar a cabo un comportamiento personalizado.  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>Mediante el método para definir el bloque de flujo de ventana deslizante a encapsular  
 En el ejemplo siguiente se usa el <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> método para crear un bloque propagador desde un origen y un destino. Un bloque propagador permite que un bloque de origen y un bloque de destino para que actúe como un receptor y remitente de los datos.  
  
 Esta técnica es útil cuando necesita funcionalidad de flujo de datos personalizados, pero no es necesario que un tipo que proporciona métodos adicionales, propiedades o campos.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>Derivar de IPropagatorBlock para definir el bloque de flujo de ventana deslizante  
 El siguiente ejemplo se muestra la `SlidingWindowBlock` clase. Esta clase se deriva de <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> para que pueda actuar como un origen y un destino de datos. Como se muestra en el ejemplo anterior, la `SlidingWindowBlock` clase se basa en los tipos de bloques de flujo de datos existente. Sin embargo, el `SlidingWindowBlock` clase también implementa los métodos necesarios para la <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, y <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> interfaces. Reenviar todos estos métodos funcionan para los miembros de tipo de bloque de flujo de datos predefinidos. Por ejemplo, el `Post` método aplaza el trabajo para el `m_target` miembro de datos, que es también un <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> objeto.  
  
 Esta técnica es útil cuando se requieren la funcionalidad de flujo de datos personalizados y también requiere un tipo que proporciona métodos adicionales, propiedades o campos. Por ejemplo, el `SlidingWindowBlock` clase también se deriva de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> para que pueda ofrecer el <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> y <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> métodos. El `SlidingWindowBlock` clase también muestra extensibilidad proporcionando la `WindowSize` propiedad, que recupera el número de elementos de la ventana deslizante.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>Ejemplo completo  
 En el ejemplo siguiente se muestra el código completo de este tutorial. También se muestra cómo usar los dos bloques de ventana deslizante en un método que escribe en el bloque, lee en ella e imprime los resultados en la consola.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o péguelo en un archivo que se denomina `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## <a name="next-steps"></a>Pasos siguientes  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
