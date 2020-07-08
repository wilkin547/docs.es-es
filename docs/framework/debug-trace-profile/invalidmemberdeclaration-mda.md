---
title: MDA de invalidMemberDeclaration
description: Revise el Asistente para la depuración administrada invalidMemberDeclaration, que se invoca si se devuelve un valor HRESULT de error a COM sin llamar al método administrado.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 5dbfba2baec3263d91746c06379438e97a81f005
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051719"
---
# <a name="invalidmemberdeclaration-mda"></a>MDA de invalidMemberDeclaration
El asistente para la depuración administrada (MDA) de `invalidMemberDeclaration` se activa para informar acerca de un error que se produce a la hora de determinar cómo serializar los parámetros de un miembro al que se va a llamar desde COM.  
  
## <a name="symptoms"></a>Síntomas  
 Se devuelve a COM un valor HRESULT de error sin que se haya llamado al método administrado.  
  
## <a name="cause"></a>Causa  
 Esto probablemente se debe a un atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatible en uno de los parámetros.  
  
## <a name="resolution"></a>Resolución  
 Especifique los atributos <xref:System.Runtime.InteropServices.MarshalAsAttribute> válidos en los parámetros.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Output  
 Mensaje informativo que contiene el nombre de miembro, el nombre de tipo y el mensaje de error.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
