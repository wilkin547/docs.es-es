---
title: MDA de failedQI
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
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: 15
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 313676abe0732fcd4f3285c5c1f935302695d3cc
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="failedqi-mda"></a>MDA de failedQI
El asistente para la depuración administrada (MDA) `failedQI` se activa cuando Runtime llama a `QueryInterface` en un puntero de interfaz COM en nombre de un contenedor al que se puede llamar en tiempo de ejecución (RCW) y la llamada `QueryInterface` falla.
  
  
## <a name="symptoms"></a>Síntomas  
 No se puede realizar una conversión en un contenedor RCW o se produce un error inesperado en una llamada a COM desde un contenedor RCW  
  
## <a name="cause"></a>Motivo  
  
-   La llamada se realiza desde el contexto equivocado.  
  
-   El servidor proxy registrado no puede realizar la llamada `QueryInterface` porque se intentó realizar en el contexto equivocado.  
  
-   Un servidor proxy propiedad de OLE devolvió un valor HRESULT de error.   
  
## <a name="resolution"></a>Resolución  
 Consulte la documentación sobre reglas COM recogida en el sitio de MSDN.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Si no se puede realizar la llamada `QueryInterface`, el contexto cambia y es necesario volver a intentar realizar la llamada `QueryInterface` para ver si el motivo del error era un contexto incorrecto.  
  
## <a name="output"></a>Resultado  
 El nombre administrado de la interfaz, el GUID de la interfaz y el valor HRESULT del error.   
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnóstico de errores con asistentes para la depuración administrada](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)

