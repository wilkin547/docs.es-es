---
title: "Callback Functions | Microsoft Docs"
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
  - "callback function"
  - "platform invoke, calling unmanaged functions"
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Callback Functions
Una función de devolución de llamada es código de una aplicación administrada que ayuda a las funciones no administradas de un archivo DLL a completar sus tareas.  Las llamadas a una función de devolución de llamada se pasan indirectamente desde una aplicación administrada, a través de una función de un archivo DLL, y de vuelta a la implementación administrada.  Algunas de las muchas funciones de archivos DLL a las que se llama con la invocación de plataforma requieren una función de devolución de llamada en código administrado para ejecutarse correctamente.  
  
 Para llamar a la mayoría de las funciones de archivos DLL desde código administrado, se crea una definición administrada de la función y, a continuación, se la llama.  El proceso es bastante sencillo.  
  
 Para utilizar una función de un archivo DLL que requiere una función de devolución de llamada hay que llevar a cabo ciertos pasos adicionales.  En primer lugar, hay que determinar si la función requiere una devolución de llamada estudiando la documentación de la función.  Después, hay que crear la función de devolución de llamada en la aplicación administrada.  Finalmente, se llama a la función del archivo DLL, pasándole un puntero a la función de devolución de llamada como argumento.  En la siguiente ilustración se resumen estos pasos.  
  
 ![Devolución de llamadas de invocación de plataforma](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
Función de devolución de llamada e implementación  
  
 Las funciones de devolución de llamada son ideales para utilizarlas en situaciones en las que una tarea se realiza repetidas veces.  Otro uso frecuente es con funciones de enumeración, como **EnumFontFamilies**, **EnumPrinters** y **EnumWindows** en la API Win32.  La función **EnumWindows** enumera todas las ventanas existentes en su equipo, llamando a la función de devolución de llamada para realizar una tarea en cada ventana.  Para obtener instrucciones y un ejemplo, vea [Cómo: Implementar funciones de devolución de llamada](../../../docs/framework/interop/how-to-implement-callback-functions.md).  
  
## Vea también  
 [How to: Implement Callback Functions](../../../docs/framework/interop/how-to-implement-callback-functions.md)   
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)