---
title: 'Mitigación: Compatibilidad del lápiz y la entrada táctil basados en el puntero'
description: Conozca los efectos que tiene habilitar una pila de lápiz/entrada táctil opcional de WPF para aplicaciones de WPF destinadas a .NET Framework 4.7.
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: d0c0effeaa727c615dddc3b92cdd34aafde65705
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475429"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="9d844-103">Mitigación: compatibilidad del lápiz y la entrada táctil basados en el puntero</span><span class="sxs-lookup"><span data-stu-id="9d844-103">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="9d844-104">Las aplicaciones de WPF que se destinan a .NET Framework 4.7 y que se ejecutan en Windows a partir de Windows 10 Creators Update pueden habilitar la pila de lápiz/entada táctil de WPF basada en `WM_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="9d844-104">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="9d844-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="9d844-105">Impact</span></span>

<span data-ttu-id="9d844-106">Los desarrolladores que no habiliten explícitamente la compatibilidad del lápiz o la entrada táctil basados en puntero no deberían percibir ningún cambio en el comportamiento del lápiz o de la entrad táctil de WPF.</span><span class="sxs-lookup"><span data-stu-id="9d844-106">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="9d844-107">A continuación se muestran problemas conocidos actuales con la pila de lápiz o de entrada táctil basados en `WM_POINTER`:</span><span class="sxs-lookup"><span data-stu-id="9d844-107">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="9d844-108">No se admiten las entradas manuscritas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9d844-108">No support for real-time inking.</span></span>

   <span data-ttu-id="9d844-109">A pesar de que los complementos de lápiz y entrada manuscrita siguen funcionando, se procesan en el subproceso de la interfaz de usuario, que puede provocar un rendimiento deficiente.</span><span class="sxs-lookup"><span data-stu-id="9d844-109">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="9d844-110">El comportamiento cambia debido a las modificaciones en la promoción de los eventos de lápiz o de entrada táctil a los eventos de mouse.</span><span class="sxs-lookup"><span data-stu-id="9d844-110">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="9d844-111">La manipulación puede comportarse de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="9d844-111">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="9d844-112">Arrastrar y colocar no mostrará la información adecuada para la entrada táctil.</span><span class="sxs-lookup"><span data-stu-id="9d844-112">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="9d844-113">(Esto no afecta a la entrada de lápiz).</span><span class="sxs-lookup"><span data-stu-id="9d844-113">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="9d844-114">Arrastrar y colocar ya no se puede iniciar en los eventos de lápiz/entrada táctil.</span><span class="sxs-lookup"><span data-stu-id="9d844-114">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="9d844-115">Esto puede hacer que la aplicación deje de responder hasta que se detecte la entrada del mouse.</span><span class="sxs-lookup"><span data-stu-id="9d844-115">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="9d844-116">En su lugar, los desarrolladores deben iniciar Arrastrar y colocar en los eventos del mouse.</span><span class="sxs-lookup"><span data-stu-id="9d844-116">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="9d844-117">Inclusión de la compatibilidad del lápiz o la entrada táctil basados en WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="9d844-117">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="9d844-118">Los desarrolladores que quieran habilitar esta pila pueden agregar lo siguiente al archivo *app.config* de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d844-118">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="9d844-119">Si se quita esta entrada o se establece su valor en `false`, se desactiva esta pila opcional.</span><span class="sxs-lookup"><span data-stu-id="9d844-119">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d844-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d844-120">See also</span></span>

- [<span data-ttu-id="9d844-121">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="9d844-121">Application compatibility</span></span>](application-compatibility.md)
