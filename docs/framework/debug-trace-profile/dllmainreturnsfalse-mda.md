---
title: "dllMainReturnsFalse MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), DllMain returns false"
  - "DllMainReturnsFalse MDA"
  - "DllMain function"
  - "MDAs (managed debugging assistants), DllMain returns false"
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# dllMainReturnsFalse MDA
El asistente para la depuración administrada \(MDA\) de `dllMainReturnsFalse` se activa si la función `DllMain` administrada de un ensamblado de usuario, conocida como DLL\_PROCESS\_ATTACH, devuelve FALSE.  
  
## Síntomas  
 La función `DllMain` devolvió FALSE, indicando que no se ejecutó correctamente.  Esto puede producir problemas indeterminados debido a que las funciones `DllMain` normalmente contienen código de inicialización importante.  
  
## Motivo  
 Se llama a la función `DllMain` con DLL\_PROCESS\_ATTACH para la inicialización del archivo DLL en carga.  Si devuelve FALSE, significa que se ha producido un error en la inicialización del archivo DLL.  
  
## Resolución  
 Analice el código de la función `DllMain` del archivo DLL con error e identifique la causa del error de inicialización.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  Sólo informa acerca de los datos relacionados con el valor devuelto para `DllMain`.  
  
## Resultados  
 Mensaje que indica que la función `DllMain`, denominada DLL\_PROCESS\_ATTACH, devolvió FALSE.  Hay que observar que este MDA sólo se activa si `DllMain` se implementa en código administrado.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)