---
title: 'Tutorial: Crear tipos de bloques de flujos de datos personalizados'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
ms.openlocfilehash: 37857e465bf4089dbeecc4cfd532d0702f795495
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284707"
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>Tutorial: Crear tipos de bloques de flujos de datos personalizados
Aunque la biblioteca de flujo de datos TPL proporciona varios tipos de bloques de flujo de datos que permiten una variedad de funciones, también puede crear tipos de bloques personalizados. En este documento se describe cómo crear un tipo de bloque de flujo de datos que implementa un comportamiento personalizado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Lea [Flujo de datos](dataflow-task-parallel-library.md) antes de leer este documento.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="defining-the-sliding-window-dataflow-block"></a>Definición de un bloque de flujo de datos de ventana deslizante  
 Considere la posibilidad de que una aplicación de flujo de datos requiera que los valores de entrada se almacenen en búfer y que el resultado se muestre en un tipo de ventana deslizante. Por ejemplo, para los valores de entrada {0, 1, 2, 3, 4, 5} y un tamaño de ventana de tres, un bloque de flujo de datos de ventana deslizante produce las matrices de salida {0, 1, 2}, {1, 2, 3}, {2, 3, 4} y {3, 4, 5}. En las secciones siguientes se describen dos maneras de crear un tipo de bloque de flujo de datos que implementa este comportamiento personalizado. La primera técnica utiliza el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> para combinar la funcionalidad de un objeto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y un objeto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> en un bloque propagador. La segunda técnica define una clase que deriva de <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> y combina la funcionalidad existente para llevar a cabo un comportamiento personalizado.  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>Uso del método encapsulador para definir el bloque de flujo de datos de ventana deslizante  
 En el ejemplo siguiente se usa el método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> para crear un bloque propagador desde un origen y un destino. Un bloque propagador permite que un bloque de origen y un bloque de destino actúen como un destinatario y remitente de datos.  
  
 Esta técnica es útil cuando necesita la funcionalidad de flujo de datos personalizada, pero no necesita un tipo que proporcione métodos, propiedades o campos adicionales.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>Derivación de IPropagatorBlock para definir el bloque de flujo de datos de ventana deslizante  
 En el ejemplo siguiente se muestra la clase `SlidingWindowBlock`. Esta clase se deriva de <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> para que pueda actuar como un origen y un destino de datos. Como se muestra en el ejemplo anterior, la clase `SlidingWindowBlock` se basa en los tipos de bloques de flujo de datos existentes. Sin embargo, la clase `SlidingWindowBlock` también implementa los métodos necesarios para las interfaces <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> y <xref:System.Threading.Tasks.Dataflow.IDataflowBlock>. Todos estos métodos reenvían el trabajo a los miembros del tipo de bloque de flujo de datos predefinido. Por ejemplo, el método `Post` aplaza el trabajo para el miembro de datos `m_target`, que también es un objeto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>.  
  
 Esta técnica es útil cuando necesita la funcionalidad de flujo de datos personalizada y también necesita un tipo que proporcione métodos, propiedades o campos adicionales. Por ejemplo, la clase `SlidingWindowBlock` también deriva de <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601>, para que pueda proporcionar los métodos <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> y <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A>. La clase `SlidingWindowBlock` también muestra la extensibilidad al proporcionar la propiedad `WindowSize`, que recupera el número de elementos en la ventana deslizante.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>Ejemplo completo  
 En el ejemplo siguiente se muestra el código completo de este tutorial. También se muestra cómo usar los dos bloques de ventana deslizante en un método que escribe en el bloque, lee en él e imprime los resultados en la consola.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="see-also"></a>Vea también

- [Flujo de datos](dataflow-task-parallel-library.md)
