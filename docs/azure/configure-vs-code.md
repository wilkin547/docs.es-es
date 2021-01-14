---
title: Configuración de Visual Studio Code para el desarrollo en Azure con .NET
description: Este artículo le ayuda a configurar Visual Studio Code para el desarrollo de Azure, incluida la instalación de los complementos correctos y la configuración en Visual Studio Code.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 65ced99befe12d137062b4ea6a59a1ccd3099e0b
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701031"
---
# <a name="configure-visual-studio-code-for-azure-development"></a>Configuración de Visual Studio Code para el desarrollo en Azure

Si usa Visual Studio Code, ya sea para el desarrollo de .NET, para compilar aplicaciones de una sola página con plataformas como Angular, React o Vue, o para escribir aplicaciones en otro lenguaje como Python, necesitará configurar Visual Studio Code para el desarrollo de Azure.

### <a name="download-visual-studio-code"></a>Descargar Visual Studio Code

Si ya tiene instalado Visual Studio Code, puede omitir este paso.

> [!div class="nextstepaction"]
> [Descargar Visual Studio Code](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a>Instalación del paquete de extensiones de Azure Tools

El [paquete de extensiones Azure Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) contiene extensiones para trabajar con Azure App Service, Azure Functions, Azure Storage, Cosmos DB y Azure Virtual Machines, todo en un único y práctico paquete.

Para instalar la extensión desde Visual Studio Code, siga los pasos siguientes:

1. Presione <kbd>Ctrl + Mayús + X</kbd> para abrir la ventana **Extensiones**.
1. Busque la extensión *Azure Tools*.
1. Seleccione el botón **Instalar**.

![Captura de pantalla de Visual Studio Code que muestra el panel de extensiones en el que se busca el paquete de extensiones Azure Tools](./media/visual-studio-code-azure-tools.png)

Para obtener más información sobre la instalación de extensiones en Visual Studio Code, consulte el documento [Marketplace de extensiones](https://code.visualstudio.com/docs/editor/extension-gallery) en el sitio web de Visual Studio Code.

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a>Inicio de sesión en la cuenta de Azure con Azure Tools

En el panel izquierdo, verá un icono de Azure. Seleccione este icono y aparecerá un panel de control de los servicios de Azure. Elija **Iniciar sesión en Azure...** en cualquier servicio para completar el proceso de autenticación de Azure Tools en Visual Studio Code.

![Captura de pantalla de Visual Studio Code en la que se muestra cómo iniciar sesión en Azure Tools](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a>Pasos siguientes

Ahora, tendrá que instalar la CLI de Azure en la estación de trabajo.

> [!div class="nextstepaction"]
> [Instalación de la CLI de Azure](./install-azure-cli.md)
