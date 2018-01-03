---
title: "Funciones de devolución de llamada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4f39160e817ce04c5c15fb8299852a052d36c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="callback-functions"></a>Funciones de devolución de llamada
Una función de devolución de llamada es código dentro de una aplicación administrada que ayuda a una función DLL no administrada a completar una tarea. Las llamadas a una función de devolución de llamada pasan indirectamente desde una aplicación administrada, a través de una función DLL, y de nuevo a la implementación administrada. Algunas de las muchas funciones DLL que se llaman con la invocación de plataforma requieren una función de devolución de llamada en código administrado para ejecutarse correctamente.  
  
 Para llamar a la mayoría de las funciones DLL desde el código administrado, se crea una definición administrada de la función y, después, se llama. El proceso es sencillo.  
  
 El uso de una función DLL que requiere una función de devolución de llamada tiene algunos pasos adicionales. En primer lugar, se debe determinar si la función requiere una devolución de llamada examinando la documentación de la función. Después, habrá que crear la función de devolución de llamada en la aplicación administrada. Por último, se llama a la función DLL, pasando un puntero a la función de devolución de llamada como argumento. En la siguiente ilustración se resumen estos pasos.  
  
 ![Devolución de llamada de invocación de plataforma](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
Función de devolución de llamada e implementación  
  
 Las funciones de devolución de llamada son ideales para su uso en situaciones en las que se realiza una tarea repetidamente. Otro uso frecuente es con funciones de enumeración, como **EnumFontFamilies**, **EnumPrinters** y **EnumWindows** en la API Win32. La función **EnumWindows** enumera todas las ventanas existentes en el equipo, y llama a la función de devolución de llamada para realizar una tarea en cada ventana. Para obtener instrucciones y un ejemplo, vea [Cómo: Implementar funciones de devolución de llamada](../../../docs/framework/interop/how-to-implement-callback-functions.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Implementar funciones de devolución de llamada](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 [Llamar a una función DLL](../../../docs/framework/interop/calling-a-dll-function.md)
