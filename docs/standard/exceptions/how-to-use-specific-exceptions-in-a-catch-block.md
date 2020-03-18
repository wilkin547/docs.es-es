---
title: 'Cómo: Utilizar excepciones específicas en un bloque Catch'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
ms.openlocfilehash: 48b450e579263876725f96e0adfc4c16aac1d869
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160162"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a>Cómo: Utilizar excepciones específicas en un bloque Catch

En general, en programación es recomendable detectar un tipo de excepción específico en lugar de usar una instrucción `catch` básica.

Cuando se produce una excepción, se pasa a la pila y cada bloque Catch tiene la oportunidad de controlarla. El orden de las instrucciones Catch es importante. Ponga los bloques Catch dirigidos a excepciones específicas antes de un bloque Catch de excepción general o el compilador podría emitir un error. El bloque Catch adecuado se determina haciendo coincidir el tipo de la excepción con el nombre de la excepción especificada en el bloque Catch. Si no hay ningún bloque Catch específico, la excepción se detecta mediante un bloque Catch general, si existe alguno.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una <xref:System.InvalidCastException>. El ejemplo crea una clase denominada `Employee` con una propiedad única, el nivel de empleado (`Emlevel`). Un método, `PromoteEmployee`, toma un objeto e incrementa el nivel del empleado. Una <xref:System.InvalidCastException> se produce cuando una instancia de <xref:System.DateTime> se pasa al método `PromoteEmployee`.

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
