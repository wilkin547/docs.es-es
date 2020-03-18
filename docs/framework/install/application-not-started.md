---
title: Solución del error "No se pudo iniciar esta aplicación"
description: Obtenga información sobre qué hacer si ve el cuadro de diálogo "No se pudo iniciar esta aplicación".
ms.date: 09/05/2019
ms.openlocfilehash: 864c6ea23e9a048f060eee39d904bd4377be5084
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "76965911"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a>Solución de un mensaje de error "No se pudo iniciar esta aplicación"

Las aplicaciones que se desarrollan para .NET Framework suelen requerir que se instale una versión específica de .NET Framework en el sistema. En algunos casos, puede intentar ejecutar una aplicación sin una versión instalada ni la versión esperada de .NET Framework presente. Esto suele generar un cuadro de diálogo de error similar al siguiente:

![No se pudo iniciar esta aplicación.](media/application-not-started/app-could-not-be-started.png)

Por lo general, esto indica una de las condiciones siguientes:

- Se dañó una instalación de .NET Framework del sistema.

- No se puede detectar la versión de .NET Framework que se necesita para la aplicación.

Para solucionar este problema de manera que pueda ejecutar la aplicación, haga lo siguiente:

1. Descargue la [herramienta de reparación de .NET Framework (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135). La herramienta se ejecuta automáticamente cuando se completa la descarga.

1. Si la herramienta de reparación de .NET Framework recomienda realizar cualquier acción adicional, como las que se muestran en la figura siguiente, seleccione **Siguiente**.

   ![Cambios recomendados](media/application-not-started/repair-tool-recommended-changes.png)

1. La herramienta de reparación de .NET Framework muestra un cuadro de diálogo que se ve en la ilustración siguiente para indicar que se completaron los cambios. Deje abierto el cuadro de diálogo mientras vuelve a ejecutar la aplicación. Esto debe realizarse correctamente si la herramienta de reparación de .NET Framework ha identificado y corregido una instalación dañada de .NET Framework.

   ![Cambios recomendados](media/application-not-started/repair-tool-changes-complete.png)

1. Si la aplicación se ejecuta correctamente, seleccione el botón **Finalizar**. En caso contrario, seleccione el botón **Siguiente**.

1. Si seleccionó el botón **Siguiente**, la herramienta de reparación de .NET Framework muestra un cuadro de diálogo como el siguiente. Seleccione el botón **Finalizar** para enviar información de diagnóstico a Microsoft.

   ![No se puede resolver el problema](media/application-not-started/repair-tool-no-resolution.png)

1. Si sigue sin poder ejecutar la aplicación, instale la versión más reciente de .NET Framework compatible con su versión de Windows, tal como se muestra en la tabla siguiente.

   |Versión de Windows|Instalación de .NET Framework|
   |---|---|
   |Actualización de aniversario de Windows 10 (versión 1607) o versiones posteriores|[Tiempo de ejecución de .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 10, actualización de noviembre de Windows 10|[.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |Windows 8.1|[Tiempo de ejecución de .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 8|[.NET Framework 4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |Windows 7 SP1|[Tiempo de ejecución de .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows Vista SP2|[.NET Framework 4.6](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > .NET Framework 4.8 instalado previamente en la Actualización de mayo de 2019 de Windows 10.

1. Intente iniciar la aplicación.

1. En algunos casos, puede ver un cuadro de diálogo como el siguiente, en el que se le pida que instale .NET Framework 3.5. Seleccione **Download and install this feature** (Descargar e instalar esta característica) para instalar .NET Framework 3.5 y vuelva a iniciar la aplicación.

   ![No se puede resolver el problema](media/application-not-started/install-3-5.png)

## <a name="see-also"></a>Vea también

- [Requisitos del sistema de .NET Framework](../get-started/system-requirements.md)
- [Guía de instalación de .NET Framework](index.md)
- [Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
