---
title: Migración de una aplicación web ASP.NET a una máquina virtual de Azure
description: Vea cómo migrar una aplicación web ASP.NET de un entorno local a una máquina virtual de Azure.
ms.topic: how-to
ms.date: 11/15/2017
ms.openlocfilehash: cc9477de92e6105762636ed3a2241949e69ac8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81433365"
---
# <a name="migrate-an-aspnet-web-application-to-an-azure-virtual-machine"></a><span data-ttu-id="92f53-103">Migración de una aplicación web ASP.NET a una máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="92f53-103">Migrate an ASP.NET Web application to an Azure Virtual Machine</span></span>

<span data-ttu-id="92f53-104">En este documento se describe cómo migrar una aplicación web ASP.NET de un entorno local a una máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="92f53-104">This document provides an overview of how to migrate an ASP.NET web application from on-premises to an Azure Virtual Machine.</span></span>

## <a name="quickstart"></a><span data-ttu-id="92f53-105">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="92f53-105">Quickstart</span></span>

<span data-ttu-id="92f53-106">Obtenga información acerca de cómo crear una máquina virtual y publicar la aplicación en ella: [Publicar en una máquina virtual de Azure](https://tutorials.visualstudio.com/aspnet-vm/intro)</span><span class="sxs-lookup"><span data-stu-id="92f53-106">Learn how to create a virtual machine and publish your app to it: [Publish to an Azure VM](https://tutorials.visualstudio.com/aspnet-vm/intro)</span></span>

## <a name="get-started"></a><span data-ttu-id="92f53-107">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="92f53-107">Get Started</span></span>

<span data-ttu-id="92f53-108">Estos tutoriales muestran los pasos para crear (o migrar) una máquina virtual, publicar la aplicación web en ella y otras tareas que pueden ser necesarias para admitir la aplicación en Azure.</span><span class="sxs-lookup"><span data-stu-id="92f53-108">These tutorials demonstrate the steps to create (or migrate) a virtual machine, publish your web application to it, and other tasks that may be required to support your application in Azure.</span></span>

- <span data-ttu-id="92f53-109">Cree una máquina virtual para la aplicación ASP.NET en Azure con una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="92f53-109">Create a virtual machine for your ASP.NET application in Azure using one of the following options:</span></span>
  - [<span data-ttu-id="92f53-110">Creación de una nueva máquina virtual para aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="92f53-110">Create a new virtual machine for ASP.NET Applications</span></span>](https://go.microsoft.com/fwlink/?linkid=863237)
  - [<span data-ttu-id="92f53-111">Migración de una máquina virtual VMWare local existente</span><span class="sxs-lookup"><span data-stu-id="92f53-111">Migrate an existing on-premises VMWare virtual machine</span></span>](https://docs.microsoft.com/azure/migrate/tutorial-migrate-vmware)
  - [<span data-ttu-id="92f53-112">Migración de una máquina virtual Hyper-V local existente</span><span class="sxs-lookup"><span data-stu-id="92f53-112">Migrate an existing on-premises Hyper-V virtual machine</span></span>](https://docs.microsoft.com/azure/migrate/tutorial-migrate-hyper-v)
- [<span data-ttu-id="92f53-113">Publicación de la aplicación mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92f53-113">Publish your app using Visual Studio</span></span>](https://go.microsoft.com/fwlink/?linkid=863240)
- [<span data-ttu-id="92f53-114">Creación de una red virtual segura para sus máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="92f53-114">Create a secure virtual network for your VMs</span></span>](https://docs.microsoft.com/azure/virtual-network/virtual-network-get-started-vnet-subnet)
- [<span data-ttu-id="92f53-115">Creación de una canalización de CI/CD para la aplicación</span><span class="sxs-lookup"><span data-stu-id="92f53-115">Create a CI/CD pipeline for your application</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-webdeploy-iis-deploygroups)
- [<span data-ttu-id="92f53-116">Traslado a un conjunto de escalado de máquinas virtuales para alta disponibilidad y escalabilidad</span><span class="sxs-lookup"><span data-stu-id="92f53-116">Move to a VM scale set for high availability and scalability</span></span>](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app)

## <a name="considerations"></a><span data-ttu-id="92f53-117">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="92f53-117">Considerations</span></span>

### <a name="benefits"></a><span data-ttu-id="92f53-118">Ventajas</span><span class="sxs-lookup"><span data-stu-id="92f53-118">Benefits</span></span>

<span data-ttu-id="92f53-119">Las máquinas virtuales ofrecen una ruta más sencilla para migrar una aplicación de un entorno local a la nube.</span><span class="sxs-lookup"><span data-stu-id="92f53-119">Virtual machines offer the easiest path to migrate an application from on-premises to the cloud.</span></span> <span data-ttu-id="92f53-120">Permiten replicar el mismo entorno que la aplicación usa de forma local, pero elimina la necesidad de mantener sus propios centros de datos.</span><span class="sxs-lookup"><span data-stu-id="92f53-120">They enable you to replicate the same environment your application uses on-premises, while removing the need to maintain your own data centers.</span></span> <span data-ttu-id="92f53-121">Los conjuntos de escalado de máquinas virtuales proporcionan alta disponibilidad y escalabilidad para las aplicaciones que se ejecutan en las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="92f53-121">Virtual Machine Scale Sets provide high availability and scalability for applications running in Virtual Machines.</span></span>

### <a name="virtual-machine-size"></a><span data-ttu-id="92f53-122">Tamaño de la máquina virtual</span><span class="sxs-lookup"><span data-stu-id="92f53-122">Virtual Machine Size</span></span>

<span data-ttu-id="92f53-123">Elija el tamaño y el tipo de máquina virtual más adecuados para la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92f53-123">Choose the virtual machine size and type that is best optimized for your workload.</span></span> <span data-ttu-id="92f53-124">Para más información, vea [Tamaños de las máquinas virtuales Windows en Azure](https://docs.microsoft.com/azure/virtual-machines/windows/sizes).</span><span class="sxs-lookup"><span data-stu-id="92f53-124">For more information, see [Sizes for Windows virtual machines in Azure](https://docs.microsoft.com/azure/virtual-machines/windows/sizes).</span></span>

### <a name="maintenance"></a><span data-ttu-id="92f53-125">Mantenimiento </span><span class="sxs-lookup"><span data-stu-id="92f53-125">Maintenance</span></span>

<span data-ttu-id="92f53-126">Al igual que una máquina local, es su responsabilidad de mantener y actualizar la máquina virtual<sup>&#42;</sup>.</span><span class="sxs-lookup"><span data-stu-id="92f53-126">Just like an on-premises machine, you are responsible for maintaining and updating the virtual machine<sup>&#42;</sup>.</span></span> <span data-ttu-id="92f53-127">Si la aplicación puede ejecutarse en un entorno de Plataforma como servicio (PaaS), por ejemplo, [Azure App Service](https://docs.microsoft.com/azure/app-service/) o en un [contenedor](https://docs.microsoft.com/azure/app-service/containers/), esto ya no será necesario.</span><span class="sxs-lookup"><span data-stu-id="92f53-127">If your application can run in a Platform as a Service (PaaS) environment such as [Azure App Service](https://docs.microsoft.com/azure/app-service/) or in a [container](https://docs.microsoft.com/azure/app-service/containers/), that will remove this need.</span></span>

<span data-ttu-id="92f53-128">*<sup>&#42;</sup>[Las actualizaciones automáticas del sistema operativo para los conjuntos de escalado de máquinas virtuales](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) están disponibles en versión preliminar.*</span><span class="sxs-lookup"><span data-stu-id="92f53-128">*<sup>&#42;</sup>[Automatic OS upgrades for virtual machine scale sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) is currently available as a Preview service.*</span></span>

### <a name="virtual-networks"></a><span data-ttu-id="92f53-129">Virtual Networks</span><span class="sxs-lookup"><span data-stu-id="92f53-129">Virtual Networks</span></span>

<span data-ttu-id="92f53-130">Azure Virtual Network permite:</span><span class="sxs-lookup"><span data-stu-id="92f53-130">Azure Virtual Networks enable you to:</span></span>

- <span data-ttu-id="92f53-131">Crear una infraestructura híbrida bajo su control</span><span class="sxs-lookup"><span data-stu-id="92f53-131">Build a hybrid infrastructure that you control</span></span>
- <span data-ttu-id="92f53-132">Traer sus propias direcciones IP y servidores DNS</span><span class="sxs-lookup"><span data-stu-id="92f53-132">Bring your own IP addresses and DNS servers</span></span>
- <span data-ttu-id="92f53-133">Crear un entorno aislado y de alta seguridad para sus aplicaciones</span><span class="sxs-lookup"><span data-stu-id="92f53-133">Create an isolated and highly secure environment for your applications</span></span>
- <span data-ttu-id="92f53-134">Conectar su máquina virtual a la red local mediante diversas [opciones de conectividad](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)</span><span class="sxs-lookup"><span data-stu-id="92f53-134">Connect your VM to your on-premises network using one of several [connectivity options](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)</span></span>
- <span data-ttu-id="92f53-135">Integrar la máquina virtual en la red local mediante [ExpressRoute](https://azure.microsoft.com/services/expressroute/)</span><span class="sxs-lookup"><span data-stu-id="92f53-135">Integrate your virtual machine into your on-premises network using [ExpressRoute](https://azure.microsoft.com/services/expressroute/)</span></span>

<span data-ttu-id="92f53-136">Para comenzar, consulte la [documentación de Virtual Network](https://docs.microsoft.com/azure/virtual-network/)</span><span class="sxs-lookup"><span data-stu-id="92f53-136">To get started, see the [Virtual Network documentation](https://docs.microsoft.com/azure/virtual-network/)</span></span>

### <a name="active-directory"></a><span data-ttu-id="92f53-137">Grafo de</span><span class="sxs-lookup"><span data-stu-id="92f53-137">Active Directory</span></span>
<span data-ttu-id="92f53-138">Muchas aplicaciones usan Active Directory para la autenticación y administración de identidades.</span><span class="sxs-lookup"><span data-stu-id="92f53-138">Many applications use Active Directory for authentication and identity management.</span></span>

- <span data-ttu-id="92f53-139">Azure AD Connect permite integrar sus directorios locales con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92f53-139">Azure AD Connect enables you to integrate your on-premises directories with Azure Active Directory.</span></span> <span data-ttu-id="92f53-140">Para comenzar, consulte [Integración de los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="92f53-140">To get started, see [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="92f53-141">[ExpressRoute](https://azure.microsoft.com/services/expressroute/) también permite que la aplicación tenga acceso a su directorio local de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="92f53-141">Alternatively, [ExpressRoute](https://azure.microsoft.com/services/expressroute/) enables your application to access your on-premises Active Directory.</span></span>

### <a name="sql-databases"></a><span data-ttu-id="92f53-142">Instancias de SQL Database</span><span class="sxs-lookup"><span data-stu-id="92f53-142">SQL Databases</span></span>

<span data-ttu-id="92f53-143">Si su aplicación usa una base de datos local, la aplicación no podrá comunicarse con ella de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="92f53-143">If your application is using an on-premises database, your app will not be able to talk to it by default.</span></span> <span data-ttu-id="92f53-144">Puede:</span><span class="sxs-lookup"><span data-stu-id="92f53-144">You can either:</span></span>

- <span data-ttu-id="92f53-145">Configurar una red híbrida que permita que la aplicación tenga acceso a la base de datos que se ejecuta de forma local.</span><span class="sxs-lookup"><span data-stu-id="92f53-145">Configure a hybrid network that enables your application to access your database running on-premises.</span></span>
- <span data-ttu-id="92f53-146">Migrar la base de datos a Azure.</span><span class="sxs-lookup"><span data-stu-id="92f53-146">Migrate your database to the Azure.</span></span> <span data-ttu-id="92f53-147">Para más información, vea [Migración de la base de datos de SQL Server a Azure](sql.md).</span><span class="sxs-lookup"><span data-stu-id="92f53-147">For more information, see [Migrate your SQL Server database to Azure](sql.md).</span></span>

### <a name="high-availability-and-scalability"></a><span data-ttu-id="92f53-148">Alta disponibilidad y escalabilidad</span><span class="sxs-lookup"><span data-stu-id="92f53-148">High Availability and Scalability</span></span>

#### <a name="virtual-machine-scale-sets"></a><span data-ttu-id="92f53-149">Virtual Machine Scale Sets</span><span class="sxs-lookup"><span data-stu-id="92f53-149">Virtual Machine Scale Sets</span></span>
<span data-ttu-id="92f53-150">Si desea asegurarse de que la aplicación tenga alta disponibilidad y pueda escalar, migre la imagen de su máquina virtual a un conjunto de escalado de máquinas virtuales de Azure para mejorar la disponibilidad y escalabilidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="92f53-150">You want to make sure that your application is highly available and can scale, migrate your VM image to an Azure Virtual Machine Scale Set to improve the availability and scalability of your application.</span></span> <span data-ttu-id="92f53-151">VM Scale Sets permite usar una máquina virtual existente ya configurada o configurar una canalización de compilación para crear una imagen con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="92f53-151">VM Scale Sets provide the ability to use an existing VM you've already configured or set up a build pipeline to build an image with your application.</span></span>

<span data-ttu-id="92f53-152">Para comenzar, consulte [Implementación de la aplicación en conjuntos de escalado de máquinas virtuales](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app).</span><span class="sxs-lookup"><span data-stu-id="92f53-152">To get started, see [Deploy your application on virtual machine scale sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app).</span></span>

#### <a name="centralized-logging"></a><span data-ttu-id="92f53-153">Registro centralizado</span><span class="sxs-lookup"><span data-stu-id="92f53-153">Centralized Logging</span></span>
<span data-ttu-id="92f53-154">Si la aplicación se ejecuta en varias instancias, considere la posibilidad de almacenar los registros en una ubicación centralizada, por ejemplo, [Azure Storage](https://docs.microsoft.com/azure/storage/).</span><span class="sxs-lookup"><span data-stu-id="92f53-154">When running your application across multiple instances, consider storing your logs in a centralized location such as [Azure Storage](https://docs.microsoft.com/azure/storage/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="92f53-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="92f53-155">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92f53-156">Migración de una base de datos de SQL Server a Azure</span><span class="sxs-lookup"><span data-stu-id="92f53-156">Migrate a SQL Server database to Azure</span></span>](sql.md)
