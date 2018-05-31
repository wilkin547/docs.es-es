---
title: Serialización de un delegado como un método de devolución de llamada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff875f2807a14493ab81a9e354b5c4dcdf3d5feb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389388"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Serialización de un delegado como un método de devolución de llamada
En este ejemplo se muestra cómo pasar delegados a una función no administrada que espera recibir punteros de función. Un delegado es una clase que puede contener una referencia a un método y equivale a un puntero de función con seguridad de tipos o a una función de devolución de llamada.  
  
> [!NOTE]
>  Cuando se usa un delegado dentro de una llamada, Common Language Runtime evita la eliminación del delegado por el recolector de elementos no utilizados mientras dure esa llamada. Pero si la función no administrada almacena el delegado para usarlo al finalizar la llamada, debe impedir manualmente la recolección de elementos no utilizados hasta que finalice la función no administrada con el delegado. Para más información, vea [HandleRef (ejemplo)](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) y [GCHandle (ejemplo)](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).  
  
 En el ejemplo de devolución de llamada se usan las siguientes funciones no administradas, que se muestran con su declaración de función original:  
  
-   **TestCallBack** exportada desde PinvokeLib.dll.  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   **TestCallBack2** exportada desde PinvokeLib.dll.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) es una biblioteca personalizada no administrada que contiene una implementación para las funciones enumeradas anteriormente.  
  
 En este ejemplo, la clase `LibWrap` contiene prototipos administrados para los métodos `TestCallBack` y `TestCallBack2`. Ambos métodos pasan un delegado a una función de devolución de llamada como un parámetro. La firma del delegado debe coincidir con la firma del método al que hace referencia. Por ejemplo, los delegados `FPtr` y `FPtr2` tienen firmas idénticas a las de los métodos `DoSomething` y `DoSomething2`.  
  
## <a name="declaring-prototypes"></a>Declaración de prototipos  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a>Llamadas a funciones  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a>Vea también  
 [Diversos ejemplos de serialización](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))  
 [Tipos de datos de invocación de plataforma](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md)
