---
title: "How to: Listen for Multiple Cancellation Requests | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cancellation tokens, joining"
  - "LinkedTokenSource, how to"
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Multiple Cancellation Requests
En este ejemplo se muestra cómo escuchar dos tokens de cancelación simultáneamente de manera que pueda cancelar una operación si uno de los tokens lo solicita.  
  
> [!NOTE]
>  Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno.  Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en los ejemplos siguientes.  Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" bajo **Herramientas, Opciones, Depuración, General**.  
  
## Ejemplo  
 En el ejemplo siguiente se usa el método <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> para combinar dos tokens en uno.  Esto permite pasar el token a métodos que solo toman un token de cancelación como argumento.  En el ejemplo se muestra un escenario común en el que un método debe observar un token pasado desde fuera de la clase y un token generado dentro de la clase.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Cuando el token vinculado produce <xref:System.OperationCanceledException>, el token que se pasa a la excepción es el token vinculado, no uno de los token del predecesor.  Para determinar cuál de los tokens se canceló, compruebe el estado de los tokens del predecesor directamente.  
  
 En este ejemplo, <xref:System.AggregateException> no se debe producir nunca, pero se detecta aquí porque en los escenarios reales todas las demás excepciones aparte de <xref:System.OperationCanceledException> que se producen desde el delegado de la tarea se encapsulan en una excepción <xref:System.OperationCanceledException>.  
  
## Vea también  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)