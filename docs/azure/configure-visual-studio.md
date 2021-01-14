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
# <a name="configure-visual-studio-for-azure-development-with-net"></a><span data-ttu-id="12cfa-103">Configuración de Visual Studio para el desarrollo en Azure con .NET</span><span class="sxs-lookup"><span data-stu-id="12cfa-103">Configure Visual Studio for Azure development with .NET</span></span>

<span data-ttu-id="12cfa-104">Visual Studio incluye herramientas que ayudan a desarrollar e implementar aplicaciones en Azure.</span><span class="sxs-lookup"><span data-stu-id="12cfa-104">Visual Studio includes tooling to help with the development and deployment of applications on Azure.</span></span>  <span data-ttu-id="12cfa-105">Esta guía le ayudará a asegurarse de que tiene Visual Studio configurado correctamente para el desarrollo de Azure.</span><span class="sxs-lookup"><span data-stu-id="12cfa-105">This guide will help you make sure that you have Visual Studio properly configured for Azure development.</span></span>

### <a name="download-visual-studio-2019"></a><span data-ttu-id="12cfa-106">Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="12cfa-106">Download Visual Studio 2019</span></span>

<span data-ttu-id="12cfa-107">Si ya tiene instalado Visual Studio 2019, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="12cfa-107">If you already have Visual Studio 2019 installed, you can skip this step.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="12cfa-108">Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="12cfa-108">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="install-azure-workloads"></a><span data-ttu-id="12cfa-109">Instalación de cargas de trabajo de Azure</span><span class="sxs-lookup"><span data-stu-id="12cfa-109">Install Azure workloads</span></span>

<span data-ttu-id="12cfa-110">Inicie el **Instalador de Visual Studio** y compruebe que tiene instaladas las cargas de trabajo **de desarrollo de Azure** y **de desarrollo web y ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="12cfa-110">Launch the **Visual Studio Installer** and validate that you have the workloads **Azure development** and **ASP.NET and web development** are installed.</span></span>  <span data-ttu-id="12cfa-111">Si alguna de estas cargas de trabajo no está instalada, selecciónelas para instalarlas.</span><span class="sxs-lookup"><span data-stu-id="12cfa-111">If either of these workloads is not installed, select these workloads to install them.</span></span>

![Captura de pantalla del instalador de Visual Studio en la que se muestran las cargas de trabajo de desarrollo de Azure y de desarrollo web y ASP.NET seleccionadas](./media/visual-studio-installer-azure-development.png)

### <a name="authenticate-visual-studio-with-azure"></a><span data-ttu-id="12cfa-113">Autenticación de Visual Studio con Azure</span><span class="sxs-lookup"><span data-stu-id="12cfa-113">Authenticate Visual Studio with Azure</span></span>

<span data-ttu-id="12cfa-114">Al depurar aplicaciones a través de Visual Studio, Visual Studio puede usar su cuenta de Azure para autenticarse y acceder a los recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="12cfa-114">When debugging apps through Visual Studio, Visual Studio can use your Azure account to authenticate and access Azure Resources with.</span></span>  <span data-ttu-id="12cfa-115">Esta cuenta también se usa cuando se publican aplicaciones directamente desde Visual Studio en Azure.</span><span class="sxs-lookup"><span data-stu-id="12cfa-115">This account is also used when you publish apps directly from Visual Studio to Azure.</span></span>

<span data-ttu-id="12cfa-116">Para autenticar su cuenta de Azure desde Visual Studio, seleccione el menú **Herramientas** > **Opciones** para iniciar el cuadro de diálogo **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="12cfa-116">To authenticate your Azure account from Visual Studio, select the **Tools** > **Options** menu to launch the **Options** dialog.</span></span> <span data-ttu-id="12cfa-117">Vaya a las opciones de `Azure Service Authentication` e inicie sesión con su cuenta de Azure.</span><span class="sxs-lookup"><span data-stu-id="12cfa-117">Navigate to the `Azure Service Authentication` options and sign in using your Azure account.</span></span>

![Captura de pantalla del cuadro de diálogo Opciones de Visual Studio que muestra el inicio de sesión de Azure](./media/visual-studio-azure-login-dialog.png)

### <a name="next-steps"></a><span data-ttu-id="12cfa-119">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="12cfa-119">Next steps</span></span>

<span data-ttu-id="12cfa-120">Si también usa [Visual Studio Code](https://code.visualstudio.com/) para el desarrollo en .NET o en cualquier otro lenguaje, también debe [configurar Visual Studio Code para el desarrollo de Azure](./configure-vs-code.md).</span><span class="sxs-lookup"><span data-stu-id="12cfa-120">If you also use [Visual Studio Code](https://code.visualstudio.com/) for development in .NET or any other language, you should also [configure Visual Studio Code for Azure development](./configure-vs-code.md).</span></span> <span data-ttu-id="12cfa-121">De lo contrario, continúe con la [instalación de la CLI de Azure](./install-azure-cli.md).</span><span class="sxs-lookup"><span data-stu-id="12cfa-121">Otherwise, proceed to [Installing the Azure CLI](./install-azure-cli.md).</span></span>
