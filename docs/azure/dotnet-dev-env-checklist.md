---
title: Lista de comprobación de la configuración de desarrollo de .NET en Azure
description: Proporciona un resumen rápido de todas las herramientas que debe tener instaladas para el desarrollo de .NET con Azure.
ms.date: 1/1/2021
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 2f22f69ec99baf192d1cbdd28f884b7f47867389
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257985"
---
# <a name="net-on-azure-development-environment-checklist"></a><span data-ttu-id="1c2a4-103">Lista de comprobación del entorno de desarrollo de .NET en Azure</span><span class="sxs-lookup"><span data-stu-id="1c2a4-103">.NET on Azure development environment checklist</span></span>

<span data-ttu-id="1c2a4-104">Esta lista de comprobación se proporciona para ayudarle a asegurarse de que tenga el entorno de desarrollo configurado correctamente para el desarrollo de .NET con Azure.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-104">This checklist is provided to help you make sure you have your development environment correctly configured for .NET development with Azure</span></span>

## <a name="create-an-azure-account"></a><span data-ttu-id="1c2a4-105">Crear una cuenta de Azure</span><span class="sxs-lookup"><span data-stu-id="1c2a4-105">Create an Azure account</span></span>

<span data-ttu-id="1c2a4-106">Para acceder a servicios de Azure o ejecutar aplicaciones en Azure, necesita una cuenta de Azure.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-106">To access Azure services or run applications in Azure, you need an Azure account.</span></span>

* <span data-ttu-id="1c2a4-107">Si tiene una suscripción de Visual Studio, cuenta con [créditos de Azure gratuitos](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) disponibles cada mes.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-107">If you are a Visual Studio subscriber, you have monthly [free Azure credits](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) available to you every month</span></span>
* <span data-ttu-id="1c2a4-108">[Cree una cuenta de Azure gratuita](https://azure.microsoft.com/free/dotnet/) y recibirá 200 USD en créditos y servicios específicos de manera gratuita durante 12 meses.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-108">[Create a free Azure account](https://azure.microsoft.com/free/dotnet/) and receive $200 in credits and select services free for 12 months</span></span>
* <span data-ttu-id="1c2a4-109">Use una cuenta que le haya asignado el administrador de Azure de su empresa.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-109">Use an account assigned to you by your company's Azure administrator</span></span>

## <a name="configure-your-ide"></a><span data-ttu-id="1c2a4-110">Configuración del IDE</span><span class="sxs-lookup"><span data-stu-id="1c2a4-110">Configure your IDE</span></span>

<span data-ttu-id="1c2a4-111">Herramientas populares como Visual Studio y Visual Studio Code tienen extensiones disponibles que permiten trabajar con Azure directamente desde el IDE.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-111">Popular tools like Visual Studio and Visual Studio Code have extensions available to let you work with Azure right from your IDE.</span></span>

* <span data-ttu-id="1c2a4-112">[Configuración de Visual Studio](./configure-visual-studio.md) para el desarrollo de .NET con Azure</span><span class="sxs-lookup"><span data-stu-id="1c2a4-112">[Configure Visual Studio](./configure-visual-studio.md) for .NET development using Azure</span></span>
* <span data-ttu-id="1c2a4-113">[Configuración de Visual Studio Code](./configure-vs-code.md) para el desarrollo de .NET con Azure</span><span class="sxs-lookup"><span data-stu-id="1c2a4-113">[Configure Visual Studio Code](./configure-vs-code.md) for .NET Development using Azure</span></span>

## <a name="install-the-azure-cli"></a><span data-ttu-id="1c2a4-114">Instalación de la CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="1c2a4-114">Install the Azure CLI</span></span>

<span data-ttu-id="1c2a4-115">Además de usar Azure Portal, le interesa instalar la CLI de Azure para crear y administrar recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-115">In addition to using the Azure portal, you will want to install the Azure CLI to create and manage Azure resources.</span></span>

* [<span data-ttu-id="1c2a4-116">Instalación de la CLI de Azure para Windows</span><span class="sxs-lookup"><span data-stu-id="1c2a4-116">Install the Azure CLI for Windows</span></span>](/cli/azure/install-azure-cli-windows?tabs=azure-cli)
* [<span data-ttu-id="1c2a4-117">Instalación de la CLI de Azure para macOS</span><span class="sxs-lookup"><span data-stu-id="1c2a4-117">Install the Azure CLI for macOS</span></span>](/cli/azure/install-azure-cli-macos)
* [<span data-ttu-id="1c2a4-118">Instalación de la CLI de Azure para Linux</span><span class="sxs-lookup"><span data-stu-id="1c2a4-118">Install the Azure CLI for Linux</span></span>](/cli/azure/install-azure-cli-linux)

## <a name="install-additional-tools-and-utilities"></a><span data-ttu-id="1c2a4-119">Instalación de herramientas y utilidades adicionales</span><span class="sxs-lookup"><span data-stu-id="1c2a4-119">Install additional tools and utilities</span></span>

<span data-ttu-id="1c2a4-120">Estas herramientas adicionales están diseñadas para ayudarle a mejorar la productividad al trabajar con Azure.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-120">These additional tools are designed to make you more productive when working with Azure.</span></span>

* <span data-ttu-id="1c2a4-121">[Instale Azure PowerShell](/powershell/azure/install-az-ps) si tiene previsto usar scripts de PowerShell para crear y administrar recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-121">[Install Azure PowerShell](/powershell/azure/install-az-ps) if you plan on using PowerShell scripts to create and manage Azure resources</span></span>
* <span data-ttu-id="1c2a4-122">[Instale Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/) para cargar, descargar y administrar datos de recursos de Azure Storage, incluidos blobs, colas, tablas y CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-122">[Install Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/) to upload, download, and manage data in Azure storage resources including blobs, queues, tables, and CosmosDB.</span></span>
* <span data-ttu-id="1c2a4-123">[Instale Azure Data Studio](/sql/azure-data-studio/download-azure-data-studio) si está trabajando con Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-123">[Install Azure Data Studio](/sql/azure-data-studio/download-azure-data-studio) if you are working with Azure SQL</span></span>

## <a name="bookmark-the-following-sites"></a><span data-ttu-id="1c2a4-124">Inclusión de los sitios siguientes en los marcadores</span><span class="sxs-lookup"><span data-stu-id="1c2a4-124">Bookmark the following sites</span></span>

<span data-ttu-id="1c2a4-125">Usará estos sitios con frecuencia cuando lleve a cabo el desarrollo con Azure.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-125">You will use these sites frequently when doing Azure development.</span></span>  <span data-ttu-id="1c2a4-126">Inclúyalos en los marcadores para poder consultarlos rápidamente.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-126">Bookmark them for quick reference.</span></span>

* <span data-ttu-id="1c2a4-127">Azure Portal: [https://portal.azure.com/](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="1c2a4-127">Azure Portal - [https://portal.azure.com/](https://portal.azure.com/)</span></span>
* <span data-ttu-id="1c2a4-128">Azure Cloud Shell: [https://shell.azure.com/](https://shell.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="1c2a4-128">Azure Cloud Shell - [https://shell.azure.com/](https://shell.azure.com/)</span></span>
