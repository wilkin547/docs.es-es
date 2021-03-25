---
title: Solución del error "No se pudo iniciar esta aplicación"
description: Obtenga información sobre qué hacer si ve el cuadro de diálogo "No se pudo iniciar esta aplicación".
ms.date: 09/05/2019
ms.openlocfilehash: 92055bf40500eba4f7c892d11af12d8e675ddd5d
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605248"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a>Solución de un mensaje de error "No se pudo iniciar esta aplicación"

Para las aplicaciones que se desarrollan para .NET Framework suele ser necesario instalar una versión específica de .NET Framework en el sistema. En algunos casos, puede intentar ejecutar una aplicación sin una versión instalada ni la versión esperada de .NET Framework presente. Esto suele generar un cuadro de diálogo de error similar al siguiente:

![No se pudo iniciar esta aplicación.](media/application-not-started/app-could-not-be-started.png)

Por lo general, este error indica una de las condiciones siguientes:

- Se dañó una instalación de .NET Framework del sistema.

- No se puede detectar la versión de .NET Framework que se necesita para la aplicación.

Para solucionar este problema de manera que pueda ejecutar la aplicación, haga lo siguiente:

1. Descargue la [herramienta de reparación de .NET Framework (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135). La herramienta se ejecuta automáticamente cuando se completa la descarga.

1. Si la herramienta de reparación de .NET Framework recomienda realizar cualquier acción adicional, como las que se muestran en la figura siguiente, seleccione **Siguiente**.

   ![Cambios recomendados de la herramienta de reparación](media/application-not-started/repair-tool-recommended-changes.png)

1. La herramienta de reparación de .NET Framework muestra un cuadro de diálogo que se ve en la ilustración siguiente para indicar que se completaron los cambios. Deje abierto el cuadro de diálogo mientras vuelve a ejecutar la aplicación. Esto debe realizarse correctamente si la herramienta de reparación de .NET Framework ha identificado y corregido una instalación dañada de .NET Framework.

   ![Cambios en la herramienta de reparación completados](media/application-not-started/repair-tool-changes-complete.png)

1. Si la aplicación se ejecuta correctamente, seleccione el botón **Finalizar**. En caso contrario, seleccione el botón **Siguiente**.

1. Si seleccionó el botón **Siguiente**, la herramienta de reparación de .NET Framework muestra un cuadro de diálogo como el siguiente. Seleccione el botón **Finalizar** para enviar información de diagnóstico a Microsoft.

   ![No se puede resolver el problema](media/application-not-started/repair-tool-no-resolution.png)

1. Si sigue sin poder ejecutar la aplicación, instale la versión más reciente de .NET Framework compatible con la versión de Windows, como se muestra en la tabla siguiente.

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

1. En algunos casos, es posible que vea un cuadro de diálogo como el siguiente, en el que se le pida que instale .NET Framework 3.5. Seleccione **Descargar e instalar esta característica** para instalar .NET Framework 3.5 y, después, vuelva a iniciar la aplicación.

   ![Cuadro de diálogo Características de Windows en el que se sugiere la instalación de .NET Framework 3.5](media/application-not-started/install-3-5.png)

## <a name="see-also"></a>Vea también

- [Requisitos del sistema de .NET Framework](../get-started/system-requirements.md)
- [Guía de instalación de .NET Framework](index.md)
- [Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
