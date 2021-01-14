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
# <a name="configure-visual-studio-code-for-azure-development"></a><span data-ttu-id="86c51-103">Configuración de Visual Studio Code para el desarrollo en Azure</span><span class="sxs-lookup"><span data-stu-id="86c51-103">Configure Visual Studio Code for Azure development</span></span>

<span data-ttu-id="86c51-104">Si usa Visual Studio Code, ya sea para el desarrollo de .NET, para compilar aplicaciones de una sola página con plataformas como Angular, React o Vue, o para escribir aplicaciones en otro lenguaje como Python, necesitará configurar Visual Studio Code para el desarrollo de Azure.</span><span class="sxs-lookup"><span data-stu-id="86c51-104">If you are using Visual Studio Code, whether for .NET development, for building single page applications using frameworks like Angular, React or Vue, or for writing applications in another language like Python, you will want to configure Visual Studio Code for Azure development.</span></span>

### <a name="download-visual-studio-code"></a><span data-ttu-id="86c51-105">Descargar Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="86c51-105">Download Visual Studio Code</span></span>

<span data-ttu-id="86c51-106">Si ya tiene instalado Visual Studio Code, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="86c51-106">If you already have Visual Studio Code installed, you can skip this step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="86c51-107">Descargar Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="86c51-107">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a><span data-ttu-id="86c51-108">Instalación del paquete de extensiones de Azure Tools</span><span class="sxs-lookup"><span data-stu-id="86c51-108">Install the Azure Tools Extension Pack</span></span>

<span data-ttu-id="86c51-109">El [paquete de extensiones Azure Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) contiene extensiones para trabajar con Azure App Service, Azure Functions, Azure Storage, Cosmos DB y Azure Virtual Machines, todo en un único y práctico paquete.</span><span class="sxs-lookup"><span data-stu-id="86c51-109">The [Azure Tools Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) contains extensions for working with Azure App Service, Azure Functions, Azure Storage, Cosmos DB, and Azure Virtual Machines all in one convenient package.</span></span>

<span data-ttu-id="86c51-110">Para instalar la extensión desde Visual Studio Code, siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="86c51-110">To install the extension from Visual Studio Code:</span></span>

1. <span data-ttu-id="86c51-111">Presione <kbd>Ctrl + Mayús + X</kbd> para abrir la ventana **Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="86c51-111">Press <kbd>Ctrl+Shift+X</kbd> to open the **Extensions** window.</span></span>
1. <span data-ttu-id="86c51-112">Busque la extensión *Azure Tools*.</span><span class="sxs-lookup"><span data-stu-id="86c51-112">Search for the *Azure Tools* extension.</span></span>
1. <span data-ttu-id="86c51-113">Seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="86c51-113">Select the **Install** button.</span></span>

![Captura de pantalla de Visual Studio Code que muestra el panel de extensiones en el que se busca el paquete de extensiones Azure Tools](./media/visual-studio-code-azure-tools.png)

<span data-ttu-id="86c51-115">Para obtener más información sobre la instalación de extensiones en Visual Studio Code, consulte el documento [Marketplace de extensiones](https://code.visualstudio.com/docs/editor/extension-gallery) en el sitio web de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="86c51-115">To learn more about installing extensions in Visual Studio Code, refer to the [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) document on the Visual Studio Code website.</span></span>

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a><span data-ttu-id="86c51-116">Inicio de sesión en la cuenta de Azure con Azure Tools</span><span class="sxs-lookup"><span data-stu-id="86c51-116">Sign in to your Azure account with Azure Tools</span></span>

<span data-ttu-id="86c51-117">En el panel izquierdo, verá un icono de Azure.</span><span class="sxs-lookup"><span data-stu-id="86c51-117">On the left hand panel, you'll see an Azure icon.</span></span> <span data-ttu-id="86c51-118">Seleccione este icono y aparecerá un panel de control de los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="86c51-118">Select this icon, and a control panel for Azure services will appear.</span></span> <span data-ttu-id="86c51-119">Elija **Iniciar sesión en Azure...** en cualquier servicio para completar el proceso de autenticación de Azure Tools en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="86c51-119">Choose **Sign in to Azure...** under any service to complete the authentication process for the Azure tools in Visual Studio Code.</span></span>

![Captura de pantalla de Visual Studio Code en la que se muestra cómo iniciar sesión en Azure Tools](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a><span data-ttu-id="86c51-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="86c51-121">Next steps</span></span>

<span data-ttu-id="86c51-122">Ahora, tendrá que instalar la CLI de Azure en la estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="86c51-122">Next, you will want to install the Azure CLI on your workstation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="86c51-123">Instalación de la CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="86c51-123">Install the Azure CLI</span></span>](./install-azure-cli.md)
