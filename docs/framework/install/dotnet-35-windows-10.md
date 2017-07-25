---
title: "Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8 | Microsoft Docs"
description: Aprenda a instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8
author: rlander
keywords: .NET Framework, Instalar
ms.date: 04/20/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 137436a073c050ed431b231204a3aca31c98c01a
ms.contentlocale: es-es
ms.lasthandoff: 06/02/2017

---

# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8

Para ejecutar una aplicación en Windows 10, Windows 8.1 y Windows 8, es posible que necesite .NET Framework 3.5. También puede usar estas instrucciones para versiones anteriores de Windows.

## <a name="install-the-net-framework-35-on-demand"></a>Instalar .NET Framework 3.5 a petición

Si intenta ejecutar una aplicación que requiere .NET Framework 3.5, es posible que vea el siguiente cuadro de diálogo de configuración. Elija **Instalar esta característica** para habilitar .NET Framework 3.5. Esta opción requiere una conexión a Internet.

![Cuadro de diálogo de instalación de .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a>Habilitar .NET Framework 3.5 en el Panel de control

Puede habilitar .NET Framework 3.5 mediante el Panel de control de Windows. Esta opción requiere una conexión a Internet.

1. Presione la tecla Windows ![logotipo de Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) del teclado, escriba "Características de Windows" y presione Entrar. Aparecerá el cuadro de diálogo **Activar o desactivar las características de Windows**.

2. Seleccione la casilla de verificación **.NET Framework 3.5 (incluye .NET 2.0 y 3.0)**, seleccione Aceptar y reinicie el equipo si se le solicita.

   ![Instalación de .NET con el Panel de control](./media/dotnet-control-panel.png)

   No necesita seleccionar los elementos secundarios para la **activación HTTP de Windows Communication Foundation (WCF)** y la **activación no HTTP de Windows Communication Foundation (WCF)**, a menos que sea un desarrollador o administrador de servidores que requiera esta funcionalidad.

