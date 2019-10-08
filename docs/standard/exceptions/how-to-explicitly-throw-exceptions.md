---
title: Procedimiento para iniciar excepciones explícitamente
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a71cefc0a6483dbbe6513a64d8111a07a2e5af42
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696742"
---
# <a name="how-to-explicitly-throw-exceptions"></a>Cómo iniciar excepciones explícitamente

Puede iniciar explícitamente una excepción mediante la instrucción [`throw`](../../csharp/language-reference/keywords/throw.md) de C# o la instrucción [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) de Visual Basic. También se puede iniciar una excepción detectada usando de nuevo la instrucción `throw`. En diseño de código, es recomendable agregar información a una excepción que se vuelve a iniciar para proporcionar más información durante la depuración.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una posible <xref:System.IO.FileNotFoundException>. Seguido del bloque `try` va un bloque `catch` que detecta <xref:System.IO.FileNotFoundException> y escribe un mensaje a la consola si no se encuentra el archivo de datos. La siguiente instrucción es `throw` que inicia un parámetro <xref:System.IO.FileNotFoundException> nuevo y agrega información de texto a la excepción.

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
