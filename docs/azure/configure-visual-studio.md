---
title: Configuración de Visual Studio para el desarrollo en Azure con .NET
description: Este artículo le ayuda a configurar Visual Studio para el desarrollo de Azure, incluida la instalación de las cargas de trabajo correctas y la conexión de Visual Studio a su cuenta de Azure.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 986469bd07657d968045465803047dc21d76dd62
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701036"
---
# <a name="configure-visual-studio-for-azure-development-with-net"></a>Configuración de Visual Studio para el desarrollo en Azure con .NET

Visual Studio incluye herramientas que ayudan a desarrollar e implementar aplicaciones en Azure.  Esta guía le ayudará a asegurarse de que tiene Visual Studio configurado correctamente para el desarrollo de Azure.

### <a name="download-visual-studio-2019"></a>Descargar Visual Studio 2019

Si ya tiene instalado Visual Studio 2019, puede omitir este paso.

> [!div class="nextstepaction"]
> [Descargar Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="install-azure-workloads"></a>Instalación de cargas de trabajo de Azure

Inicie el **Instalador de Visual Studio** y compruebe que tiene instaladas las cargas de trabajo **de desarrollo de Azure** y **de desarrollo web y ASP.NET**.  Si alguna de estas cargas de trabajo no está instalada, selecciónelas para instalarlas.

![Captura de pantalla del instalador de Visual Studio en la que se muestran las cargas de trabajo de desarrollo de Azure y de desarrollo web y ASP.NET seleccionadas](./media/visual-studio-installer-azure-development.png)

### <a name="authenticate-visual-studio-with-azure"></a>Autenticación de Visual Studio con Azure

Al depurar aplicaciones a través de Visual Studio, Visual Studio puede usar su cuenta de Azure para autenticarse y acceder a los recursos de Azure.  Esta cuenta también se usa cuando se publican aplicaciones directamente desde Visual Studio en Azure.

Para autenticar su cuenta de Azure desde Visual Studio, seleccione el menú **Herramientas** > **Opciones** para iniciar el cuadro de diálogo **Opciones**. Vaya a las opciones de `Azure Service Authentication` e inicie sesión con su cuenta de Azure.

![Captura de pantalla del cuadro de diálogo Opciones de Visual Studio que muestra el inicio de sesión de Azure](./media/visual-studio-azure-login-dialog.png)

### <a name="next-steps"></a>Pasos siguientes

Si también usa [Visual Studio Code](https://code.visualstudio.com/) para el desarrollo en .NET o en cualquier otro lenguaje, también debe [configurar Visual Studio Code para el desarrollo de Azure](./configure-vs-code.md). De lo contrario, continúe con la [instalación de la CLI de Azure](./install-azure-cli.md).
