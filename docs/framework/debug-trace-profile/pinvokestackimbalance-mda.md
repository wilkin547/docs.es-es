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
ms.openlocfilehash: 5594166081c36fbda1e5d1a62e017aaceb7a553d
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912119"
---
# <a name="pinvokestackimbalance-mda"></a>MDA de PInvokeStackImbalance

El `PInvokeStackImbalance` Asistente para la depuración administrada (MDA) se activa cuando CLR detecta que la profundidad de pila después de una invocación de plataforma llamada no coincide con la profundidad de pila esperada, dada la convención de llamada especificada en el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo y el declaración de los parámetros en la firma administrada.

El MDA `PInvokeStackImbalance` solo se implementa para plataformas de x86 de 32 bits.

> [!NOTE]
> El `PInvokeStackImbalance` MDA está deshabilitada de forma predeterminada. En Visual Studio 2017, el `PInvokeStackImbalance` MDA aparece en el **Managed Debugging Assistants** lista en el **configuración de excepciones** cuadro de diálogo (que se muestra al seleccionar **depurar**  >  **Windows** > **configuración de excepciones**). Sin embargo, activando o desactivando la **interrumpir cuando se produce** casilla de verificación no habilita ni deshabilita el MDA; solo controla si Visual Studio produce una excepción cuando se activa el MDA.

## <a name="symptoms"></a>Síntomas

Una aplicación se encuentra con una infracción de acceso o daños en la memoria cuando se realiza una llamada de invocación de plataforma o después de realizar una.

## <a name="cause"></a>Motivo

La firma administrada de la llamada de invocación de plataforma podría no coincidir con la firma no administrada del método al que se llama.  Esta falta de coincidencia puede deberse a que la firma administrada no declara el número correcto de parámetros o no especifica el tamaño adecuado para los parámetros.  El MDA también puede activarse porque la convención de llamada, posiblemente especificada por el atributo <xref:System.Runtime.InteropServices.DllImportAttribute>, no coincide con la convención de llamada no administrada.

## <a name="resolution"></a>Resolución

Revise la firma de la invocación de plataforma administrada y la convención de llamada para confirmar que coincide con la firma y la convención de llamada del destino nativo.  Pruebe a especificar explícitamente la convención de llamada en ambos lados, administrado y no administrado. También es posible, aunque no probable, que la función no administrada haya desequilibrado la pila por algún otro motivo, por ejemplo, un error en el compilador no administrado.

## <a name="effect-on-the-runtime"></a>Efecto en el Runtime

Obliga a todas las llamadas de invocación de plataforma a tomar la ruta de acceso no optimizada en CLR.

## <a name="output"></a>Salida

El mensaje del MDA indica el nombre de la llamada al método de invocación de plataforma que causa el desequilibrio de la pila. Un mensaje de ejemplo de una llamada de invocación de plataforma en el método `SampleMethod` es:

**Una llamada a función PInvoke "SampleMethod" se haya desequilibrado la pila. Esto es probable porque la firma administrada de PInvoke no coincide con la firma no administrada de destino. Compruebe que la convención de llamada y los parámetros de la firma PInvoke coinciden con la firma no administrada de destino.**

## <a name="configuration"></a>Configuración

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)
