---
title: Calcular las referencias de un delegado como un método de devolución de llamada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
ms.openlocfilehash: c71c89e5797745144a2baed2d4846e3d9f9f26be
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114012"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Calcular las referencias de un delegado como un método de devolución de llamada
En este ejemplo se muestra cómo pasar delegados a una función no administrada que espera recibir punteros de función. Un delegado es una clase que puede contener una referencia a un método y equivale a un puntero de función con seguridad de tipos o a una función de devolución de llamada.

> [!NOTE]
> Cuando se usa un delegado dentro de una llamada, Common Language Runtime evita la eliminación del delegado por el recolector de elementos no utilizados mientras dure esa llamada. Pero si la función no administrada almacena el delegado para usarlo al finalizar la llamada, debe impedir manualmente la recolección de elementos no utilizados hasta que finalice la función no administrada con el delegado. Para más información, vea [HandleRef (ejemplo)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) y [GCHandle (ejemplo)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).

En el ejemplo de devolución de llamada se usan las siguientes funciones no administradas, que se muestran con su declaración de función original:

- `TestCallBack` exportada desde PinvokeLib.dll.

    ```cpp
    void TestCallBack(FPTR pf, int value);
    ```

- `TestCallBack2` exportada desde PinvokeLib.dll.

    ```cpp
    void TestCallBack2(FPTR2 pf2, char* value);
    ```

[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada no administrada que contiene una implementación para las funciones enumeradas anteriormente.

En este ejemplo, la clase `NativeMethods` contiene prototipos administrados para los métodos `TestCallBack` y `TestCallBack2`. Ambos métodos pasan un delegado a una función de devolución de llamada como un parámetro. La firma del delegado debe coincidir con la firma del método al que hace referencia. Por ejemplo, los delegados `FPtr` y `FPtr2` tienen firmas idénticas a las de los métodos `DoSomething` y `DoSomething2`.

## <a name="declaring-prototypes"></a>Declaración de prototipos
[!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
[!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
[!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]

## <a name="calling-functions"></a>Llamadas a funciones
[!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
[!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
[!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]

## <a name="see-also"></a>Vea también

- [Diversos ejemplos de serialización](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))
- [Tipos de datos de invocación de plataforma](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md)
