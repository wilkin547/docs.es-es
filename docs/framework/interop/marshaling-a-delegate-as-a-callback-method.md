---
title: "Marshaling a Delegate as a Callback Method | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "data marshaling, Callback sample"
  - "marshaling, Callback sample"
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Marshaling a Delegate as a Callback Method
En este ejemplo se demuestra cómo pasar delegados a una función no administrada que espera recibir punteros a función.  Un delegado es una clase que puede contener una referencia a un método y equivale a un puntero a función con seguridad de tipos o una función de devolución de llamada.  
  
> [!NOTE]
>  Cuando se utiliza un delegado dentro de una llamada, Common Language Runtime lo protege contra la recolección de elementos no utilizados durante el tiempo que dure la llamada.  Sin embargo, si la función no administrada almacena el delegado para usarlo al finalizar la llamada, debe impedir manualmente la recolección de elementos no utilizados hasta que la función no administrada deje de usar el delegado.  Para obtener más información, vea [Ejemplo HandleRef](http://msdn.microsoft.com/es-es/ab23b04e-1d53-4ec7-b27a-e892d9298959) y [Ejemplo GCHandle](http://msdn.microsoft.com/es-es/6acce798-0385-4ded-a790-77da842c113f).  
  
 En el ejemplo Callback se utilizan las siguientes funciones no administradas, que se muestran con su declaración de función original:  
  
-   **TestCallBack** exportada desde PinvokeLib.dll.  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   **TestCallBack2** exportada desde PinvokeLib.dll.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](http://msdn.microsoft.com/es-es/5d1438d7-9946-489d-8ede-6c694a08f614) es una biblioteca personalizada y no administrada que contiene una implementación para las funciones enumeradas anteriormente.  
  
 En este ejemplo, la clase `LibWrap` contiene prototipos administrados para los métodos `TestCallBack` y `TestCallBack2`.  Ambos métodos pasan un delegado a una función de devolución de llamada como parámetro.  La firma del delegado debe coincidir con la del método al que hace referencia.  Por ejemplo, los delegados `FPtr` y `FPtr2` tienen firmas idénticas a las de los métodos `DoSomething` y `DoSomething2`.  
  
## Declaración de prototipos  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## Llamadas a funciones  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## Vea también  
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/es-es/a915c948-54e9-4d0f-a525-95a77fd8ed70)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/es-es/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)