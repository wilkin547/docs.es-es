---
title: "Cómo: Iniciar excepciones explícitamente"
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
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 02576db4b9920a367ac3111f2c2c49989ea45149
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-explicitly-throw-exceptions"></a>Cómo iniciar excepciones explícitamente

Puede iniciar explícitamente una excepción mediante la instrucción `throw`. También se puede iniciar una excepción detectada usando de nuevo la instrucción `throw`. En diseño de código, es recomendable agregar información a una excepción que se vuelve a iniciar para proporcionar más información durante la depuración.

En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una posible <xref:System.IO.FileNotFoundException>. Seguido del bloque `try` va un bloque `catch` que detecta <xref:System.IO.FileNotFoundException> y escribe un mensaje a la consola si no se encuentra el archivo de datos. La siguiente instrucción es `throw` que inicia un parámetro <xref:System.IO.FileNotFoundException> nuevo y agrega información de texto a la excepción.

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>Vea también  
[Excepciones](index.md)
