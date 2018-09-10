---
title: 'Cómo: Utilizar bloques Finally'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 213ab53c68a37ac0ba5f337a1d6fc32bfe6f8989
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190220"
---
# <a name="how-to-use-finally-blocks"></a>Cómo usar bloques Finally

Cuando se produce una excepción, se detiene la ejecución y se proporciona el control al controlador de excepciones adecuado. A menudo, esto significa que se omiten líneas de código que esperaba que se ejecuten. Se debe realizar alguna limpieza de recursos, como cerrar un archivo, aunque se inicie una excepción. Para ello, puede usar un bloque `finally`. Un bloque `finally` siempre se ejecuta, independientemente de si se inicia una excepción.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una <xref:System.ArgumentOutOfRangeException>. El método `Main` crea dos matrices e intenta copiar una en la otra. La acción genera un <xref:System.ArgumentOutOfRangeException> y el error se escribe en la consola. Este bloque `finally` se ejecuta independientemente del resultado de la acción de copia.

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
