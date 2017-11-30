---
title: "Cómo: Realizar escuchas de varias solicitudes de cancelación"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>Cómo: Realizar escuchas de varias solicitudes de cancelación
Este ejemplo muestra cómo escuchar dos tokens de cancelación simultáneamente, por lo que puede cancelar una operación si uno de los tokens lo solicita.  
  
> [!NOTE]
>  Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno. Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos. Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla «Solo mi código» en **herramientas, opciones, depuración, General**.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> método se usa para combinar dos tokens en uno. Esto permite que el token que se pasan a métodos que toman la cancelación de un solo token como argumento. En el ejemplo se muestra un escenario común en el que un método debe observar un token pasado desde fuera de la clase y un token generado dentro de la clase.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Cuando el token vinculado produce una <xref:System.OperationCanceledException>, el token que se pasa a la excepción es el token vinculado, no uno de los tokens del predecesor. Para determinar cuál de los tokens se canceló, compruebe el estado de los tokens del predecesor directamente.  
  
 En este ejemplo, <xref:System.AggregateException> nunca se debería iniciar, pero se detecta aquí porque en situaciones del mundo real cualquier otra excepción además <xref:System.OperationCanceledException> que se producen en el delegado de la tarea se encapsulan en un <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Vea también  
 [Cancelación en subprocesos administrados](../../../docs/standard/threading/cancellation-in-managed-threads.md)
