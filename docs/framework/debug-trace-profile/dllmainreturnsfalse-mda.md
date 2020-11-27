---
title: MDA de dllMainReturnsFalse
description: Obtenga información sobre el Asistente para la depuración administrada de dllMainReturnsFalse en .NET. Este MDA se activa si se produce un error de inicialización de DLL.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 83f38c4918c1354477627b70a62e60cbdc7de275
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273521"
---
# <a name="dllmainreturnsfalse-mda"></a>MDA de dllMainReturnsFalse

El asistente para la depuración administrada (MDA) `dllMainReturnsFalse` se activa si la función administrada `DllMain` de un ensamblado de usuario denominado con la razón DLL_PROCESS_ATTACH devuelve FALSE.  
  
## <a name="symptoms"></a>Síntomas  

 La función `DllMain` devuelve FALSE, lo que indica que no se ha ejecutado correctamente. Esto puede causar problemas indeterminados, ya que las funciones `DllMain` normalmente contienen código de inicialización importante.  
  
## <a name="cause"></a>Causa  

 La función `DllMain` se denomina con la razón DLL_PROCESS_ATTACH para la inicialización del archivo DLL tras la carga. Si devuelve FALSE, significa que se ha producido un error en la inicialización del archivo DLL.  
  
## <a name="resolution"></a>Solución  

 Analice el código de la función `DllMain` del archivo DLL erróneo e identifique la causa del error de inicialización.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  

 Este MDA no tiene ningún efecto en el CLR. Solo notifica datos sobre el valor devuelto de `DllMain`.  
  
## <a name="output"></a>Resultados  

 Un mensaje que indica que una función `DllMain`, denominada con la razón DLL_PROCESS_ATTACH, ha devuelto FALSE. Tenga en cuenta que este MDA solo se activa si `DllMain` se implementa en código administrado.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
