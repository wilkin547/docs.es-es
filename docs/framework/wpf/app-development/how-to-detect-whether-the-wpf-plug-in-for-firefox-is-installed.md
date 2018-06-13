---
title: 'Cómo: Detectar si está instalado el complemento WPF para Firefox'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: ba411d662a8e5b0c4727e23c8d507e8924b6e9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546993"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="3122f-102">Cómo: Detectar si está instalado el complemento WPF para Firefox</span><span class="sxs-lookup"><span data-stu-id="3122f-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="3122f-103">Permite que Windows Presentation Foundation (WPF) complemento para Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] perder archivos XAML que se ejecuta en el explorador Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="3122f-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="3122f-104">En este tema se proporciona un script escrito en HTML y JavaScript que los administradores pueden usar para determinar si está instalado el complemento WPF para Firefox.</span><span class="sxs-lookup"><span data-stu-id="3122f-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3122f-105">Para obtener más información sobre la instalación, implementación y detectar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], consulte [instalar .NET Framework para desarrolladores](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="3122f-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3122f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3122f-106">Example</span></span>  
 <span data-ttu-id="3122f-107">Cuando el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está instalado, está configurado el equipo cliente con un complemento WPF para Firefox.</span><span class="sxs-lookup"><span data-stu-id="3122f-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="3122f-108">El siguiente script de ejemplo comprueba si el complemento de WPF para Firefox y, a continuación, muestra un mensaje de estado adecuado.</span><span class="sxs-lookup"><span data-stu-id="3122f-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
```  
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
  
 <span data-ttu-id="3122f-109">Si la comprobación del complemento WPF para Firefox es correcta, se muestra el siguiente mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="3122f-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="3122f-110">En caso contrario, se muestra el siguiente mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="3122f-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="3122f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3122f-111">See Also</span></span>  
 [<span data-ttu-id="3122f-112">Detectar si .NET Framework 3.0 está instalado</span><span class="sxs-lookup"><span data-stu-id="3122f-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="3122f-113">Detectar si .NET Framework 3.5 está instalado</span><span class="sxs-lookup"><span data-stu-id="3122f-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [<span data-ttu-id="3122f-114">Información general sobre las aplicaciones de explorador XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="3122f-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
