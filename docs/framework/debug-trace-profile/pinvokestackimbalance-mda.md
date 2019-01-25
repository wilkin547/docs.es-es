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
ms.openlocfilehash: 9ecdfd708217f260b0c02383159fab88948029c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512325"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="dd365-102">MDA de PInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="dd365-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="dd365-103">El `PInvokeStackImbalance` Asistente para la depuración administrada (MDA) se activa cuando CLR detecta que la profundidad de pila después de una invocación de plataforma llamada no coincide con la profundidad de pila esperada, dada la convención de llamada especificada en el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo y el declaración de los parámetros en la firma administrada.</span><span class="sxs-lookup"><span data-stu-id="dd365-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="dd365-104">El MDA `PInvokeStackImbalance` solo se implementa para plataformas de x86 de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="dd365-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="dd365-105">El `PInvokeStackImbalance` MDA está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dd365-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="dd365-106">En Visual Studio 2017, el `PInvokeStackImbalance` MDA aparece en el **Managed Debugging Assistants** lista en el **configuración de excepciones** cuadro de diálogo (que se muestra al seleccionar **depurar**  >  **Windows** > **configuración de excepciones**).</span><span class="sxs-lookup"><span data-stu-id="dd365-106">In Visual Studio 2017, The `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="dd365-107">Sin embargo, activando o desactivando la **interrumpir cuando se produce** casilla de verificación no habilita ni deshabilita el MDA; solo controla si Visual Studio produce una excepción cuando se activa el MDA.</span><span class="sxs-lookup"><span data-stu-id="dd365-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="dd365-108">Síntomas</span><span class="sxs-lookup"><span data-stu-id="dd365-108">Symptoms</span></span>

<span data-ttu-id="dd365-109">Una aplicación se encuentra con una infracción de acceso o daños en la memoria cuando se realiza una llamada de invocación de plataforma o después de realizar una.</span><span class="sxs-lookup"><span data-stu-id="dd365-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="dd365-110">Motivo</span><span class="sxs-lookup"><span data-stu-id="dd365-110">Cause</span></span>

<span data-ttu-id="dd365-111">La firma administrada de la llamada de invocación de plataforma podría no coincidir con la firma no administrada del método al que se llama.</span><span class="sxs-lookup"><span data-stu-id="dd365-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="dd365-112">Esta falta de coincidencia puede deberse a que la firma administrada no declara el número correcto de parámetros o no especifica el tamaño adecuado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="dd365-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="dd365-113">El MDA también puede activarse porque la convención de llamada, posiblemente especificada por el atributo <xref:System.Runtime.InteropServices.DllImportAttribute>, no coincide con la convención de llamada no administrada.</span><span class="sxs-lookup"><span data-stu-id="dd365-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="dd365-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="dd365-114">Resolution</span></span>

<span data-ttu-id="dd365-115">Revise la firma de la invocación de plataforma administrada y la convención de llamada para confirmar que coincide con la firma y la convención de llamada del destino nativo.</span><span class="sxs-lookup"><span data-stu-id="dd365-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="dd365-116">Pruebe a especificar explícitamente la convención de llamada en ambos lados, administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="dd365-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="dd365-117">También es posible, aunque no probable, que la función no administrada haya desequilibrado la pila por algún otro motivo, por ejemplo, un error en el compilador no administrado.</span><span class="sxs-lookup"><span data-stu-id="dd365-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="dd365-118">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="dd365-118">Effect on the Runtime</span></span>

<span data-ttu-id="dd365-119">Obliga a todas las llamadas de invocación de plataforma a tomar la ruta de acceso no optimizada en CLR.</span><span class="sxs-lookup"><span data-stu-id="dd365-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="dd365-120">Salida</span><span class="sxs-lookup"><span data-stu-id="dd365-120">Output</span></span>

<span data-ttu-id="dd365-121">El mensaje del MDA indica el nombre de la llamada al método de invocación de plataforma que causa el desequilibrio de la pila.</span><span class="sxs-lookup"><span data-stu-id="dd365-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="dd365-122">Un mensaje de ejemplo de una llamada de invocación de plataforma en el método `SampleMethod` es:</span><span class="sxs-lookup"><span data-stu-id="dd365-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="dd365-123">**Una llamada a función PInvoke "SampleMethod" se haya desequilibrado la pila. Esto es probable porque la firma administrada de PInvoke no coincide con la firma no administrada de destino. Compruebe que la convención de llamada y los parámetros de la firma PInvoke coinciden con la firma no administrada de destino.**</span><span class="sxs-lookup"><span data-stu-id="dd365-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="dd365-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="dd365-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="dd365-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd365-125">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="dd365-126">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="dd365-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="dd365-127">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="dd365-127">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
