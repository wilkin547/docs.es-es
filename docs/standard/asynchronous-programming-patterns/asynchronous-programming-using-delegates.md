---
title: Programación asincrónica mediante delegados
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
ms.openlocfilehash: 05e574536abe4eac823b7b74369f5b191724e5b5
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889262"
---
# <a name="asynchronous-programming-using-delegates"></a>Programación asincrónica mediante delegados

Los delegados permiten llamar a métodos sincrónicos de forma asincrónica. Cuando se llama a un delegado sincrónicamente, el método `Invoke` llama al método de destino directamente en el subproceso actual. Si se llama al método `BeginInvoke`, Common Language Runtime (CLR) coloca la solicitud en cola y devuelve inmediatamente el control al elemento que lo llamó. El método de destino se llama asincrónicamente desde un subproceso del grupo de subprocesos. El subproceso original, que envió la solicitud, puede continuar ejecutándose en paralelo con el método de destino. Si se ha especificado un método de devolución de llamada en la llamada al método `BeginInvoke`, el método de devolución de llamada se llama cuando finaliza el método de destino. En el método de devolución de llamada, el método `EndInvoke` obtiene el valor devuelto y cualquier parámetro de entrada y salida o de solo salida. Si no se especifica ningún método de devolución de llamada al llamar a `BeginInvoke`, se puede llamar a `EndInvoke` desde el subproceso que llamó a `BeginInvoke`.  
  
> [!IMPORTANT]
> Los compiladores deben emitir clases de delegados con los métodos `Invoke`, `BeginInvoke` y `EndInvoke` mediante la firma de delegados que especifique el usuario. Los métodos `BeginInvoke` y `EndInvoke` deben representarse como nativos. Debido a que estos métodos están marcados como nativos, Common Language Runtime proporciona automáticamente la implementación en el momento en que se carga la clase. El cargador se asegura de que no se reemplazarán.  
  
## <a name="in-this-section"></a>En esta sección  
 [Llamada a métodos sincrónicos de forma asincrónica](calling-synchronous-methods-asynchronously.md)  
 Describe el uso de los delegados para realizar llamadas asincrónicas a métodos ordinarios y proporciona ejemplos de código sencillos en los que se muestran los cuatro mecanismos que existen para esperar a que una llamada asincrónica devuelva datos.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md)  
 Se describe la programación asincrónica en .NET.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Delegate>
