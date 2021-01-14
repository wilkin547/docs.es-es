---
title: Información general de Azure SDK para .NET
description: En este artículo se proporciona información general sobre qué es Azure SDK para .NET y sobre los pasos básicos para usar el SDK en una aplicación de .NET.
ms.date: 11/30/2020
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 3ec1ee9e8da3a6e03581ce2a29a655ec0d68fe54
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701014"
---
# <a name="azure-sdk-for-net-overview"></a><span data-ttu-id="e66fe-103">Información general de Azure SDK para .NET</span><span class="sxs-lookup"><span data-stu-id="e66fe-103">Azure SDK for .NET overview</span></span>

## <a name="what-is-the-azure-sdk-for-net"></a><span data-ttu-id="e66fe-104">¿Qué es Azure SDK para .NET?</span><span class="sxs-lookup"><span data-stu-id="e66fe-104">What is the Azure SDK for .NET</span></span>

<span data-ttu-id="e66fe-105">**Azure SDK para .NET** está diseñado para facilitar el uso de los servicios de Azure desde las aplicaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="e66fe-105">The **Azure SDK for .NET** is designed to make it easy to use Azure services from your .NET applications.</span></span>  <span data-ttu-id="e66fe-106">Azure SDK para .NET proporciona una interfaz coherente y familiar para acceder a los servicios de Azure, ya sea para cargar o descargar archivos en Blob Storage, recuperar los secretos de la aplicación en Azure Key Vault o procesar notificaciones de Azure Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="e66fe-106">Whether it is uploading and downloading files to Blob Storage, retrieving application secrets from Azure Key Vault, or processing notifications from Azure Event Hubs, the Azure SDK for .NET provides a consistent and familiar interface to access Azure services.</span></span>  

<span data-ttu-id="e66fe-107">Azure SDK para .NET está disponible como una serie de paquetes NuGet que se pueden usar en aplicaciones de .NET Core (2.1 y versiones posteriores) y .NET Framework (4.6.1 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="e66fe-107">The Azure SDK for .NET is available as series of NuGet packages that can be used in both .NET Core (2.1 and higher) and .NET Framework (4.6.1 and higher) applications.</span></span>

![Diagrama en el que se muestra cómo usan las aplicaciones .NET el SDK de Azure para acceder a los servicios de Azure](./media/azure-sdk-for-dotnet-overview.png)

## <a name="use-the-azure-sdk-for-net-in-your-applications"></a><span data-ttu-id="e66fe-109">Uso de Azure SDK para .NET en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e66fe-109">Use the Azure SDK for .NET in your applications</span></span>

<span data-ttu-id="e66fe-110">Para usar un paquete del SDK de Azure en una de sus aplicaciones de .NET, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e66fe-110">To use an Azure SDK package in one of your .NET applications, you want to follow these steps.</span></span>

1. <span data-ttu-id="e66fe-111">**Localización del paquete del SDK adecuado**: use la [lista de paquetes](../packages.md) para encontrar el paquete adecuado para el servicio de Azure con el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="e66fe-111">**Locate the appropriate SDK package -** Use the [package list](../packages.md) to find the appropriate package for the Azure service you are working with.</span></span>  <span data-ttu-id="e66fe-112">Tenga en cuenta que la mayoría de los servicios tienen un paquete de cliente para trabajar con el servicio y un paquete de administración para crear y administrar instancias de dicho servicio.</span><span class="sxs-lookup"><span data-stu-id="e66fe-112">Be advised that most services have a client package for working with the service and a management package for creating and managing instances of the service.</span></span>  <span data-ttu-id="e66fe-113">En la mayoría de los casos, le interesará el paquete de cliente.</span><span class="sxs-lookup"><span data-stu-id="e66fe-113">In most cases, you will want the client package.</span></span>  <span data-ttu-id="e66fe-114">Instale este paquete en la aplicación mediante NuGet.</span><span class="sxs-lookup"><span data-stu-id="e66fe-114">Install this package in your application using NuGet.</span></span>

2. <span data-ttu-id="e66fe-115">**Configuración de la autenticación para la aplicación**: para poder acceder a los recursos de Azure, la aplicación necesitará tener las credenciales y los derechos de acceso adecuados asignados en Azure.</span><span class="sxs-lookup"><span data-stu-id="e66fe-115">**Set up authentication for your application -** To access Azure resources, your application will need to have the appropriate credentials and access rights assigned in Azure.</span></span>  <span data-ttu-id="e66fe-116">Para aprender a configurar la autenticación, consulte el artículo [Autenticación con SDK de Azure para .NET](../authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e66fe-116">Learn how to configure authentication in [Authenticating .NET applications to Azure](../authentication.md).</span></span>

3. <span data-ttu-id="e66fe-117">**Escritura de código mediante el SDK en la aplicación**: al trabajar con un servicio de Azure, su código creará primero un objeto de cliente para trabajar con el servicio y, después, llamará a métodos en ese objeto de cliente para interactuar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="e66fe-117">**Write code using the SDK in your application -** When working with Azure services, your code will first create a client object to work with the service and then call methods on that client object to interact with the service.</span></span>  <span data-ttu-id="e66fe-118">Se proporcionan métodos sincrónicos y asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="e66fe-118">Both synchronous and asynchronous methods are provided.</span></span>  <span data-ttu-id="e66fe-119">En la documentación de Azure se proporcionan ejemplos de uso de cada uno de los paquetes del SDK.</span><span class="sxs-lookup"><span data-stu-id="e66fe-119">Examples of using each individual SDK package are provided throughout the Azure documentation.</span></span>

4. <span data-ttu-id="e66fe-120">**Configuración del registro para el SDK (opcional)** : si necesita diagnosticar problemas entre la aplicación y Azure, puede [habilitar el registro con Azure SDK para .NET](./logging.md).</span><span class="sxs-lookup"><span data-stu-id="e66fe-120">**Configure logging for the SDK (optional) -** If you need to diagnose issues between your application and Azure, you can [enable logging in the Azure SDK for .NET](./logging.md).</span></span>
