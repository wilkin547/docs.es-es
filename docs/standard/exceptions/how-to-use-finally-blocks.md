---
title: "Cómo: Utilizar bloques Finally"
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
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 325be4836d661369326fbe3ea1f8b252bf251f3c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-finally-blocks"></a>Cómo usar bloques Finally

Cuando se produce una excepción, se detiene la ejecución y se proporciona el control al controlador de excepciones adecuado. A menudo, esto significa que se omiten líneas de código que esperaba que se ejecuten. Se debe realizar alguna limpieza de recursos, como cerrar un archivo, aunque se inicie una excepción. Para ello, puede usar un bloque `finally`. Un bloque `finally` siempre se ejecuta, independientemente de si se inicia una excepción.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una <xref:System.ArgumentOutOfRangeException>. El método `Main` crea dos matrices e intenta copiar una en la otra. La acción genera un <xref:System.ArgumentOutOfRangeException> y el error se escribe en la consola. Este bloque `finally` se ejecuta independientemente del resultado de la acción de copia.

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a>Vea también  
[Excepciones](index.md)   
