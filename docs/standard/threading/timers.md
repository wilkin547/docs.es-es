---
title: Temporizadores
description: Obtenga información sobre los temporizadores de .NET que se pueden usar en un entorno multiproceso.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: c9d0b085285705af79f0fafa212867b5571863ba
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188723"
---
# <a name="timers"></a>Temporizadores

.NET proporciona dos temporizadores que se pueden usar en un entorno multiproceso:

- <xref:System.Threading.Timer?displayProperty=nameWithType>, que ejecuta un único método de devolución de llamada en un subproceso <xref:System.Threading.ThreadPool> a intervalos regulares.
- <xref:System.Timers.Timer?displayProperty=nameWithType>, que de forma predeterminada genera un evento en un subproceso <xref:System.Threading.ThreadPool> a intervalos regulares.

> [!NOTE]
> Algunas implementaciones de .NET pueden incluir temporizadores adicionales:
>
> - <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: un componente de Windows Forms que produce un evento a intervalos regulares. El componente no tiene interfaz de usuario y está diseñado para su uso en un entorno de un único subproceso.  
> - <xref:System.Web.UI.Timer?displayProperty=nameWithType>: un componente de ASP.NET que realiza postbacks de página web asincrónicos o sincrónicos en un intervalo definido.
> - <xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: un temporizador que se integra en la cola de <xref:System.Windows.Threading.Dispatcher> que se procesa en un intervalo de tiempo especificado y con una prioridad especificada.

## <a name="the-systemthreadingtimer-class"></a>La clase System.Threading.Timer

La clase <xref:System.Threading.Timer?displayProperty=nameWithType> permite llamar de forma continua a un delegado en intervalos de tiempo especificados. Esta clase también se puede usar para programar una sola llamada a un delegado en un intervalo de tiempo especificado. El delegado se ejecuta en un subproceso <xref:System.Threading.ThreadPool>.

Cuando se crea un objeto <xref:System.Threading.Timer?displayProperty=nameWithType>, se especifica un delegado <xref:System.Threading.TimerCallback> que define el método de devolución de llamada, un objeto de estado opcional que se pasa a la devolución de llamada, la cantidad de tiempo de retraso antes de la primera invocación de la devolución de llamada y el intervalo de tiempo entre las invocaciones de devolución de llamada. Para cancelar un temporizador pendiente, llame a la función <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se crea un temporizador que llama al delegado proporcionado por primera vez después de un segundo (1000 milisegundos) y, después, lo llama cada dos segundos. El objeto de estado del ejemplo se usa para contar el número de veces que se llama al delegado. El temporizador se detiene cuando el delegado se ha llamado al menos 10 veces.

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

Para obtener más información y ejemplos, vea <xref:System.Threading.Timer?displayProperty=nameWithType>.

## <a name="the-systemtimerstimer-class"></a>La clase System.Timers.Timer

Otro temporizador que se puede usar en un entorno multiproceso es <xref:System.Timers.Timer?displayProperty=nameWithType> que, de forma predeterminada, genera un evento en un subproceso <xref:System.Threading.ThreadPool>.

Cuando se crea un objeto <xref:System.Timers.Timer?displayProperty=nameWithType>, se puede especificar el intervalo de tiempo en el que se va a generar un evento <xref:System.Timers.Timer.Elapsed>. Use la propiedad <xref:System.Timers.Timer.Enabled%2A> para indicar si un temporizador debe generar un evento <xref:System.Timers.Timer.Elapsed>. Si necesita que un evento <xref:System.Timers.Timer.Elapsed> se genere solo una vez cuando haya transcurrido el intervalo especificado, establezca <xref:System.Timers.Timer.AutoReset%2A> en `false`. El valor predeterminado de la propiedad <xref:System.Timers.Timer.AutoReset%2A> es `true`, lo que significa que un evento <xref:System.Timers.Timer.Elapsed> se genera periódicamente durante el intervalo definido por la propiedad <xref:System.Timers.Timer.Interval%2A>.

Para obtener más información y ejemplos, vea <xref:System.Timers.Timer?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [Objetos y características de subprocesos](threading-objects-and-features.md)
