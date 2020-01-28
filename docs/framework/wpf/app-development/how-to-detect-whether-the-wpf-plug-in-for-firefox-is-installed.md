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
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Cómo: Detectar si está instalado el complemento WPF para Firefox

El complemento de Windows Presentation Foundation (WPF) para Firefox permite que las aplicaciones de explorador XAML (XBAP) y los archivos XAML sueltos se ejecuten en el explorador de Mozilla Firefox. En este tema se proporciona un script escrito en HTML y JavaScript que los administradores pueden usar para determinar si está instalado el complemento WPF para Firefox.

> [!NOTE]
> Para obtener más información sobre cómo instalar, implementar y detectar el .NET Framework, consulte [instalar el .NET Framework para desarrolladores](../../install/guide-for-developers.md).

## <a name="example"></a>Ejemplo

Cuando se instala el .NET Framework 3,5, el equipo cliente se configura con un complemento de WPF para Firefox. En el siguiente script de ejemplo se comprueba el complemento de WPF para Firefox y, a continuación, se muestra un mensaje de estado adecuado.

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

Si la comprobación del complemento de WPF para Firefox se realiza correctamente, se muestra el siguiente mensaje de estado:

`The WPF plug-in for Firefox is installed.`

De lo contrario, se muestra el siguiente mensaje de estado:

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>Vea también

- [Detectar si .NET Framework 3.0 está instalado](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Detectar si .NET Framework 3.5 está instalado](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md)
