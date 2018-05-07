---
title: MDA de pInvokeStackImbalance
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9938db3f4a3d054fde52139c166fb6a2e2a402df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="pinvokestackimbalance-mda"></a>MDA de pInvokeStackImbalance
El Asistente para la depuración administrada (MDA) `pInvokeStackImbalance` se activa cuando CLR detecta que la profundidad de la pila después de la llamada de invocación de plataforma no coincide con la profundidad de pila esperada, según la convención de llamada especificada en el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> y la declaración de los parámetros en la firma administrada.  
  
> [!NOTE]
>  El MDA `pInvokeStackImbalance` solo se implementa para plataformas de x86 de 32 bits.  
  
> [!NOTE]
>  En .NET Framework versión 3.5, el MDA `pInvokeStackImbalance` está deshabilitado de forma predeterminada. Cuando se usa la versión 3.5 de .NET Framework con Visual Studio 2005, el MDA `pInvokeStackImbalance` aparecerá en la lista **Asistentes para la depuración administrada** en el cuadro de diálogo **Excepciones** (que se muestra al hacer clic en **Excepciones** en el menú **Depurar**). Pero activar o desactivar la casilla **Thrown** para `pInvokeStackImbalance` no habilita ni deshabilita el MDA; solo controla si Visual Studio inicia una excepción cuando se activa el MDA.  
  
## <a name="symptoms"></a>Síntomas  
 Una aplicación se encuentra con una infracción de acceso o daños en la memoria cuando se realiza una llamada de invocación de plataforma o después de realizar una.  
  
## <a name="cause"></a>Motivo  
 La firma administrada de la llamada de invocación de plataforma podría no coincidir con la firma no administrada del método al que se llama.  Esta falta de coincidencia puede deberse a que la firma administrada no declara el número correcto de parámetros o no especifica el tamaño adecuado para los parámetros.  El MDA también puede activarse porque la convención de llamada, posiblemente especificada por el atributo <xref:System.Runtime.InteropServices.DllImportAttribute>, no coincide con la convención de llamada no administrada.  
  
## <a name="resolution"></a>Resolución  
 Revise la firma de la invocación de plataforma administrada y la convención de llamada para confirmar que coincide con la firma y la convención de llamada del destino nativo.  Pruebe a especificar explícitamente la convención de llamada en ambos lados, administrado y no administrado. También es posible, aunque no probable, que la función no administrada haya desequilibrado la pila por algún otro motivo, por ejemplo, un error en el compilador no administrado.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Obliga a todas las llamadas de invocación de plataforma a tomar la ruta de acceso no optimizada en CLR.  
  
## <a name="output"></a>Salida  
 El mensaje del MDA indica el nombre de la llamada al método de invocación de plataforma que causa el desequilibrio de la pila.  Un mensaje de ejemplo de una llamada de invocación de plataforma en el método `SampleMethod` es:  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)
