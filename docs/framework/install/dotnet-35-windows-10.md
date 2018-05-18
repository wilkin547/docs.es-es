---
title: Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8
description: Aprenda a instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8.
author: rlander
ms.author: mairaw
ms.date: 03/30/2018
ms.openlocfilehash: 226449b8ee7c9360e6bfdc5bfa5dfeb59f19bd2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8

Para ejecutar una aplicación en Windows 10, Windows 8.1 y Windows 8, es posible que necesite .NET Framework 3.5. También puede usar estas instrucciones para versiones anteriores de Windows.

## <a name="install-the-net-framework-35-on-demand"></a>Instalar .NET Framework 3.5 a petición

Si intenta ejecutar una aplicación que requiere .NET Framework 3.5, es posible que vea el siguiente cuadro de diálogo de configuración. Elija **Instalar esta característica** para habilitar .NET Framework 3.5. Esta opción requiere una conexión a Internet.

![Cuadro de diálogo de instalación de .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

### <a name="why-am-i-getting-this-pop-up"></a>¿Por qué recibo este elemento emergente?

Microsoft ha creado .NET Framework y proporciona un entorno para ejecutar aplicaciones. Hay diferentes versiones disponibles. Muchas empresas desarrollan sus aplicaciones para que se ejecuten con .NET Framework, y estas aplicaciones se dirigen a una versión específica. Si ve este elemento emergente, está intentando ejecutar una aplicación que requiere la versión 3.5 de .NET Framework, pero esa versión no está instalada en su sistema.

## <a name="enable-the-net-framework-35-in-control-panel"></a>Habilitar .NET Framework 3.5 en el Panel de control

Puede habilitar .NET Framework 3.5 mediante el Panel de control de Windows. Esta opción requiere una conexión a Internet.

1. Presione la tecla Windows ![logotipo de Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) del teclado, escriba "Características de Windows" y presione Entrar. Aparecerá el cuadro de diálogo **Activar o desactivar las características de Windows**.

2. Active la casilla **.NET Framework 3.5 (incluye .NET 2.0 y 3.0)**, seleccione **Aceptar** y reinicie el equipo si se le solicita.

   ![Instalación de .NET con el Panel de control](./media/dotnet-control-panel.png)

   No necesita seleccionar los elementos secundarios para la **activación HTTP de Windows Communication Foundation (WCF)** y la **activación no HTTP de Windows Communication Foundation (WCF)**, a menos que sea un desarrollador o administrador de servidores que requiera esta funcionalidad.

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>Solución de problemas de instalación de .NET Framework 3.5

Durante la instalación es posible que encuentre el error 0x800f0906, 0x800f0907, 0x800f081f, o 0x800F0922. En ese caso, consulte [Error de instalación de .NET Framework 3.5: 0x800F0906, 0x800F081F, 0x800F0907](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) para ver cómo solucionar estos problemas.

Si todavía no puede resolver el problema de instalación o no dispone de una conexión a Internet, puede intentar instalarlo mediante el soporte de instalación de Windows. Para obtener más información, consulte [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism) (Implementación de .NET Framework 3.5 mediante Administración y mantenimiento de imágenes de implementación). Si no tiene los medios para realizar la instalación, vea [Crear medios de instalación de Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).
