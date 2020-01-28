---
title: Detectar si está instalado el complemento WPF para Firefox
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 91680859c1742e5d5443d626c81273a80504f4a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740400"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="25a1c-102">Cómo: Detectar si está instalado el complemento WPF para Firefox</span><span class="sxs-lookup"><span data-stu-id="25a1c-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="25a1c-103">El complemento de Windows Presentation Foundation (WPF) para Firefox permite que las aplicaciones de explorador XAML (XBAP) y los archivos XAML sueltos se ejecuten en el explorador de Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="25a1c-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables XAML browser applications (XBAPs) and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="25a1c-104">En este tema se proporciona un script escrito en HTML y JavaScript que los administradores pueden usar para determinar si está instalado el complemento WPF para Firefox.</span><span class="sxs-lookup"><span data-stu-id="25a1c-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="25a1c-105">Para obtener más información sobre cómo instalar, implementar y detectar el .NET Framework, consulte [instalar el .NET Framework para desarrolladores](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="25a1c-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="25a1c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25a1c-106">Example</span></span>

<span data-ttu-id="25a1c-107">Cuando se instala el .NET Framework 3,5, el equipo cliente se configura con un complemento de WPF para Firefox.</span><span class="sxs-lookup"><span data-stu-id="25a1c-107">When the .NET Framework 3.5 is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="25a1c-108">En el siguiente script de ejemplo se comprueba el complemento de WPF para Firefox y, a continuación, se muestra un mensaje de estado adecuado.</span><span class="sxs-lookup"><span data-stu-id="25a1c-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

<span data-ttu-id="25a1c-109">Si la comprobación del complemento de WPF para Firefox se realiza correctamente, se muestra el siguiente mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="25a1c-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="25a1c-110">De lo contrario, se muestra el siguiente mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="25a1c-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="25a1c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="25a1c-111">See also</span></span>

- [<span data-ttu-id="25a1c-112">Detectar si .NET Framework 3.0 está instalado</span><span class="sxs-lookup"><span data-stu-id="25a1c-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="25a1c-113">Detectar si .NET Framework 3.5 está instalado</span><span class="sxs-lookup"><span data-stu-id="25a1c-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="25a1c-114">Información general sobre las aplicaciones de explorador XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="25a1c-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
