---
title: MDA de pInvokeStackImbalance
description: Revise el MDA de PInvokeStackImbalance, que se puede activar durante una infracción de acceso o daños en la memoria al realizar o seguir una llamada de invocación de plataforma.
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
ms.openlocfilehash: 89afd3fce3f2a8bffe88d45991ceeb59fc5e5b76
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803669"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="75244-103">MDA de PInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="75244-103">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="75244-104">El `PInvokeStackImbalance` Asistente para la depuración administrada (MDA) se activa cuando CLR detecta que la profundidad de la pila después de una llamada de invocación de plataforma no coincide con la profundidad de pila esperada, dada la Convención de llamada especificada en el <xref:System.Runtime.InteropServices.DllImportAttribute> atributo y la declaración de los parámetros en la firma administrada.</span><span class="sxs-lookup"><span data-stu-id="75244-104">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="75244-105">El MDA `PInvokeStackImbalance` solo se implementa para plataformas de x86 de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="75244-105">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="75244-106">El `PInvokeStackImbalance` MDA está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="75244-106">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="75244-107">En Visual Studio 2017 y versiones posteriores, el `PInvokeStackImbalance` MDA aparece en la lista **asistentes para la depuración administrada** en el cuadro de diálogo **configuración de excepciones** (que se muestra al seleccionar **depurar**  >  configuración de excepciones de**Windows**  >  **Exception Settings**).</span><span class="sxs-lookup"><span data-stu-id="75244-107">In Visual Studio 2017 and later versions, the `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="75244-108">Sin embargo, al activar o desactivar la casilla **interrumpir cuando se produce** no se habilita o deshabilita el MDA; solo controla si Visual Studio produce una excepción cuando se activa el MDA.</span><span class="sxs-lookup"><span data-stu-id="75244-108">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="75244-109">Síntomas</span><span class="sxs-lookup"><span data-stu-id="75244-109">Symptoms</span></span>

<span data-ttu-id="75244-110">Una aplicación se encuentra con una infracción de acceso o daños en la memoria cuando se realiza una llamada de invocación de plataforma o después de realizar una.</span><span class="sxs-lookup"><span data-stu-id="75244-110">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="75244-111">Causa</span><span class="sxs-lookup"><span data-stu-id="75244-111">Cause</span></span>

<span data-ttu-id="75244-112">La firma administrada de la llamada de invocación de plataforma podría no coincidir con la firma no administrada del método al que se llama.</span><span class="sxs-lookup"><span data-stu-id="75244-112">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="75244-113">Esta falta de coincidencia puede deberse a que la firma administrada no declara el número correcto de parámetros o no especifica el tamaño adecuado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="75244-113">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="75244-114">El MDA también puede activarse porque la convención de llamada, posiblemente especificada por el atributo <xref:System.Runtime.InteropServices.DllImportAttribute>, no coincide con la convención de llamada no administrada.</span><span class="sxs-lookup"><span data-stu-id="75244-114">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="75244-115">Resolución</span><span class="sxs-lookup"><span data-stu-id="75244-115">Resolution</span></span>

<span data-ttu-id="75244-116">Revise la firma de la invocación de plataforma administrada y la convención de llamada para confirmar que coincide con la firma y la convención de llamada del destino nativo.</span><span class="sxs-lookup"><span data-stu-id="75244-116">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="75244-117">Pruebe a especificar explícitamente la convención de llamada en ambos lados, administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="75244-117">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="75244-118">También es posible, aunque no probable, que la función no administrada haya desequilibrado la pila por algún otro motivo, por ejemplo, un error en el compilador no administrado.</span><span class="sxs-lookup"><span data-stu-id="75244-118">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="75244-119">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="75244-119">Effect on the Runtime</span></span>

<span data-ttu-id="75244-120">Obliga a todas las llamadas de invocación de plataforma a tomar la ruta de acceso no optimizada en CLR.</span><span class="sxs-lookup"><span data-stu-id="75244-120">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="75244-121">Output</span><span class="sxs-lookup"><span data-stu-id="75244-121">Output</span></span>

<span data-ttu-id="75244-122">El mensaje del MDA indica el nombre de la llamada al método de invocación de plataforma que causa el desequilibrio de la pila.</span><span class="sxs-lookup"><span data-stu-id="75244-122">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="75244-123">Un mensaje de ejemplo de una llamada de invocación de plataforma en el método `SampleMethod` es:</span><span class="sxs-lookup"><span data-stu-id="75244-123">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="75244-124">**Una llamada a la función PInvoke ' SampleMethod ' ha desequilibrado la pila. Probablemente, esto se debe a que la firma de PInvoke administrada no coincide con la firma de destino no administrada. Compruebe que la Convención de llamada y los parámetros de la firma PInvoke coinciden con la firma no administrada de destino.**</span><span class="sxs-lookup"><span data-stu-id="75244-124">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="75244-125">Configuración</span><span class="sxs-lookup"><span data-stu-id="75244-125">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="75244-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="75244-126">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="75244-127">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="75244-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="75244-128">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="75244-128">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
