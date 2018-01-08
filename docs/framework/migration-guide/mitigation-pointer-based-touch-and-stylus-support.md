---
title: "Mitigación: Compatibilidad del lápiz y la entrada táctil basados en el puntero"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
caps.latest.revision: "2"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78a7365d9bc82111ebd27f40e999c24d8f9ebfde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="30f33-102">Mitigación: Compatibilidad del lápiz y la entrada táctil basados en el puntero</span><span class="sxs-lookup"><span data-stu-id="30f33-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="30f33-103">Las aplicaciones de WPF que se destinan a .NET Framework 4.7 y que se ejecutan en sistemas Windows a partir de Windows 10 Creators Update pueden habilitar la pila de lápiz/entada táctil de WPF basado en `WM_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="30f33-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="30f33-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="30f33-104">Impact</span></span>

<span data-ttu-id="30f33-105">Los desarrolladores que no habiliten explícitamente la compatibilidad del lápiz o la entrada táctil basados en puntero no deberían percibir ningún cambio en el comportamiento del lápiz o de la entrad táctil de WPF.</span><span class="sxs-lookup"><span data-stu-id="30f33-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="30f33-106">A continuación se muestran problemas conocidos actuales con la pila de lápiz o de entrada táctil basados en `WM_POINTER`:</span><span class="sxs-lookup"><span data-stu-id="30f33-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="30f33-107">No se admiten las entradas manuscritas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="30f33-107">No support for real-time inking.</span></span>

   <span data-ttu-id="30f33-108">A pesar de que los complementos de lápiz y entrada manuscrita siguen funcionando, se procesan en el subproceso de la interfaz de usuario, que puede provocar un rendimiento deficiente.</span><span class="sxs-lookup"><span data-stu-id="30f33-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="30f33-109">El comportamiento cambia debido a las modificaciones en la promoción de los eventos de lápiz o de entrada táctil a los eventos de mouse.</span><span class="sxs-lookup"><span data-stu-id="30f33-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="30f33-110">La manipulación puede comportarse de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="30f33-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="30f33-111">Arrastrar y colocar no mostrará la información adecuada para la entrada táctil.</span><span class="sxs-lookup"><span data-stu-id="30f33-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="30f33-112">(Esto no afecta a la entrada de lápiz).</span><span class="sxs-lookup"><span data-stu-id="30f33-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="30f33-113">Arrastrar y colocar ya no se puede iniciar en los eventos de lápiz/entrada táctil.</span><span class="sxs-lookup"><span data-stu-id="30f33-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="30f33-114">Esto puede hacer que la aplicación de detenga hasta que se detecte la entrada del mouse.</span><span class="sxs-lookup"><span data-stu-id="30f33-114">This can potentially hang the application until mouse input is detected.</span></span> <span data-ttu-id="30f33-115">En su lugar, los desarrolladores deben iniciar Arrastrar y colocar en los eventos del mouse.</span><span class="sxs-lookup"><span data-stu-id="30f33-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a><span data-ttu-id="30f33-116">Inclusión de la compatibilidad del lápiz o la entrada táctil basados en WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="30f33-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="30f33-117">Los desarrolladores que deseen habilitar esta pila pueden agregar lo siguiente al archivo app.config de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="30f33-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="30f33-118">Si se quita esta entrada o se establece su valor en `false`, se desactiva esta pila opcional.</span><span class="sxs-lookup"><span data-stu-id="30f33-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="30f33-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="30f33-119">See also</span></span>

[<span data-ttu-id="30f33-120">Cambios de redestinación en .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="30f33-120">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
