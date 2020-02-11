---
title: 'Mitigación: compatibilidad del lápiz y la entrada táctil basados en el puntero'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 023c38f66611bd0022699d3f62d90c3923585012
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094480"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="fe0e4-102">Mitigación: compatibilidad del lápiz y la entrada táctil basados en el puntero</span><span class="sxs-lookup"><span data-stu-id="fe0e4-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="fe0e4-103">Las aplicaciones de WPF que se destinan a .NET Framework 4.7 y que se ejecutan en Windows a partir de Windows 10 Creators Update pueden habilitar la pila de lápiz/entada táctil de WPF basada en `WM_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-103">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="fe0e4-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="fe0e4-104">Impact</span></span>

<span data-ttu-id="fe0e4-105">Los desarrolladores que no habiliten explícitamente la compatibilidad del lápiz o la entrada táctil basados en puntero no deberían percibir ningún cambio en el comportamiento del lápiz o de la entrad táctil de WPF.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="fe0e4-106">A continuación se muestran problemas conocidos actuales con la pila de lápiz o de entrada táctil basados en `WM_POINTER`:</span><span class="sxs-lookup"><span data-stu-id="fe0e4-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="fe0e4-107">No se admiten las entradas manuscritas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-107">No support for real-time inking.</span></span>

   <span data-ttu-id="fe0e4-108">A pesar de que los complementos de lápiz y entrada manuscrita siguen funcionando, se procesan en el subproceso de la interfaz de usuario, que puede provocar un rendimiento deficiente.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="fe0e4-109">El comportamiento cambia debido a las modificaciones en la promoción de los eventos de lápiz o de entrada táctil a los eventos de mouse.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="fe0e4-110">La manipulación puede comportarse de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="fe0e4-111">Arrastrar y colocar no mostrará la información adecuada para la entrada táctil.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="fe0e4-112">(Esto no afecta a la entrada de lápiz).</span><span class="sxs-lookup"><span data-stu-id="fe0e4-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="fe0e4-113">Arrastrar y colocar ya no se puede iniciar en los eventos de lápiz/entrada táctil.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="fe0e4-114">Esto puede hacer que la aplicación deje de responder hasta que se detecte la entrada del mouse.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-114">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="fe0e4-115">En su lugar, los desarrolladores deben iniciar Arrastrar y colocar en los eventos del mouse.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="fe0e4-116">Inclusión de la compatibilidad del lápiz o la entrada táctil basados en WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="fe0e4-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="fe0e4-117">Los desarrolladores que quieran habilitar esta pila pueden agregar lo siguiente al archivo *app.config* de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-117">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="fe0e4-118">Si se quita esta entrada o se establece su valor en `false`, se desactiva esta pila opcional.</span><span class="sxs-lookup"><span data-stu-id="fe0e4-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe0e4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe0e4-119">See also</span></span>

- [<span data-ttu-id="fe0e4-120">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fe0e4-120">Application compatibility</span></span>](application-compatibility.md)
