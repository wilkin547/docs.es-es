---
title: MDA de invalidFunctionPointerInDelegate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c448f1e60570ae8eff9c0af0dfc942c1ed5d7599
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="invalidfunctionpointerindelegate-mda"></a>MDA de invalidFunctionPointerInDelegate
El asistente para la depuración administrada (MDA, por sus siglas en inglés) `invalidFunctionPointerInDelegate` se activa cuando un puntero de función no válido se pasa para construir un delegado sobre un puntero de función nativo.  
  
## <a name="symptoms"></a>Síntomas  
 Infracciones de acceso o deterioro inesperado de la memoria al usar un delegado sobre un puntero de función.  
  
## <a name="cause"></a>Motivo  
 El puntero de función que se especificó no es válido.  
  
## <a name="resolution"></a>Solución  
 Especifique un puntero de función válido.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Salida  
 El puntero de función no válido.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnóstico de errores con asistentes para la depuración administrada](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)

