---
title: Procedimiento Detectar si está instalado el complemento WPF para Firefox
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 138c212e79654b8ac875628692b49bb6a38cb695
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947880"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Procedimiento Detectar si está instalado el complemento WPF para Firefox

Permite que Windows Presentation Foundation (WPF) complemento para Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] y perder los archivos XAML para ejecutarse en el explorador Mozilla Firefox. En este tema se proporciona un script escrito en HTML y JavaScript que los administradores pueden usar para determinar si está instalado el complemento WPF para Firefox.

> [!NOTE]
> Para obtener más información sobre cómo instalar, implementar y detectar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], consulte [instalar .NET Framework para desarrolladores](../../install/guide-for-developers.md).

## <a name="example"></a>Ejemplo

Cuando el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está instalado, está configurado el equipo cliente con un complemento WPF para Firefox. El siguiente script de ejemplo comprueba si el complemento WPF para Firefox y, a continuación, muestra un mensaje de estado adecuado.

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

Si la comprobación para el complemento WPF para Firefox es correcta, se muestra el siguiente mensaje de estado:

`The WPF plug-in for Firefox is installed.`

En caso contrario, se muestra el siguiente mensaje de estado:

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>Vea también

- [Detectar si .NET Framework 3.0 está instalado](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Detectar si .NET Framework 3.5 está instalado](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md)
