---
title: Utilizar el bloque Try/Catch para detectar excepciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 852df5cb3eeea2ee5fa44ddce2f97e9c4f8d8b5a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185209"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Cómo usar el bloque Try/Catch para detectar excepciones

Coloque las secciones del código que pueden iniciar excepciones en un bloque `try` y coloque el código que controla las excepciones en un bloque `catch`. El bloque `catch` es una serie de instrucciones que comienzan con la palabra clave `catch`, seguido de un tipo de excepción y la acción que se debe realizar.

El siguiente ejemplo de código usa un bloque `try`/`catch` para detectar una posible excepción. El método `Main` contiene un bloque `try` con una instrucción de <xref:System.IO.StreamReader> que abre un archivo de datos denominado `data.txt` y escribe una cadena del archivo. Después del bloque `try` aparece un bloque `catch` que detecta cualquier excepción que se produzca desde el bloque `try`.

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

Common Language Runtime detecta las excepciones que no se detectan mediante un bloque Catch. Dependiendo de cómo esté configurado el runtime, aparece un cuadro de diálogo de depuración, el programa deja de ejecutarse y aparece un cuadro de diálogo con información sobre la excepción o bien se imprime un error en STDERR.

> [!NOTE] 
> Prácticamente cualquier línea de código puede originar una excepción, especialmente las excepciones iniciadas por Common Language Runtime, como <xref:System.OutOfMemoryException>. La mayoría de las aplicaciones no tienen que tratar con estas excepciones, pero debe tener en cuenta esta posibilidad al escribir bibliotecas que puedan usar otros usuarios. Para obtener sugerencias sobre cuándo establecer el código en un bloque Try, consulte [Procedimientos recomendados para excepciones](best-practices-for-exceptions.md).

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
