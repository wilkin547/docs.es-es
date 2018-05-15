---
title: Guía de implementación de .NET Framework para administradores
ms.custom: ''
ms.date: 04/10/2018
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
caps.latest.revision: 40
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 67efb04fc0d86a20fdf10c0e84bb00ae57383bb1
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="e6e03-102">Guía de implementación de .NET Framework para administradores</span><span class="sxs-lookup"><span data-stu-id="e6e03-102">.NET Framework Deployment Guide for Administrators</span></span>
<span data-ttu-id="e6e03-103">Este artículo paso a paso describe cómo un administrador del sistema puede implementar [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y sus dependencias del sistema en una red mediante Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-103">This step-by-step article describes how a system administrator can deploy the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and its system dependencies across a network by using Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="e6e03-104">En este artículo se supone que todos los equipos cliente de destino cumplen los requisitos mínimos para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e03-104">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="e6e03-105">Para obtener una lista de los requisitos de software y hardware para instalar [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], consulte [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6e03-105">For a list of the software and hardware requirements for installing the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], see [System Requirements](../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6e03-106">El software al que se hace referencia en este documento, a título enunciativo y en ningún caso limitativo, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], System Center Configuration Manager y Active Directory, está sujeto a los términos y condiciones de la licencia.</span><span class="sxs-lookup"><span data-stu-id="e6e03-106">The software referenced in this document, including, without limitation, the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], System Center Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="e6e03-107">En estas instrucciones se asume que los usuarios con la licencia apropiada del software han leído y aceptado dichos términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="e6e03-107">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="e6e03-108">Estas instrucciones no anulan ninguno de los términos y condiciones de dichos contratos de licencia.</span><span class="sxs-lookup"><span data-stu-id="e6e03-108">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>  
>   
>  <span data-ttu-id="e6e03-109">Para obtener información sobre el soporte técnico de .NET Framework, consulte [Directiva de ciclo de vida de soporte técnico de Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=196607) en el sitio web de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6e03-109">For information about support for the .NET Framework, see [Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/?LinkId=196607) on the Microsoft Support website.</span></span>  
  
 <span data-ttu-id="e6e03-110">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="e6e03-110">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="e6e03-111">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="e6e03-111">The deployment process</span></span>](#the_deployment_process)  
 [<span data-ttu-id="e6e03-112">Implementación de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6e03-112">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)  
 [<span data-ttu-id="e6e03-113">Crear una colección</span><span class="sxs-lookup"><span data-stu-id="e6e03-113">Create a collection</span></span>](#creating_a_collection)  
 [<span data-ttu-id="e6e03-114">Crear un paquete y un programa</span><span class="sxs-lookup"><span data-stu-id="e6e03-114">Create a package and program</span></span>](#creating_a_package)  
 [<span data-ttu-id="e6e03-115">Seleccionar un punto de distribución</span><span class="sxs-lookup"><span data-stu-id="e6e03-115">Select a distribution point</span></span>](#select_dist_point)  
 [<span data-ttu-id="e6e03-116">Implementar el paquete</span><span class="sxs-lookup"><span data-stu-id="e6e03-116">Deploy the package</span></span>](#deploying_package)  
[<span data-ttu-id="e6e03-117">Recursos</span><span class="sxs-lookup"><span data-stu-id="e6e03-117">Resources</span></span>](#resources)  
[<span data-ttu-id="e6e03-118">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e6e03-118">Troubleshooting</span></span>](#troubleshooting)  
  
<a name="the_deployment_process"></a>   
## <a name="the-deployment-process"></a><span data-ttu-id="e6e03-119">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="e6e03-119">The deployment process</span></span>  
 <span data-ttu-id="e6e03-120">Una vez implementada la infraestructura de apoyo, se utiliza System Center 2012 Configuration Manager para implementar el paquete redistribuible de .NET Framework en equipos de la red.</span><span class="sxs-lookup"><span data-stu-id="e6e03-120">When you have the supporting infrastructure in place, you use System Center 2012 Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="e6e03-121">La creación de la infraestructura implica crear y definir cinco áreas primarias: colecciones, un paquete y un programa para el software, puntos de distribución e implementaciones.</span><span class="sxs-lookup"><span data-stu-id="e6e03-121">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>  
  
-   <span data-ttu-id="e6e03-122">Las **colecciones** son grupos de recursos de Configuration Manager, tales como usuarios, grupos de usuarios o equipos, en los que se implementa .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e03-122">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="e6e03-123">Para obtener más información, vea el tema sobre [colecciones en Configuration Manager](http://technet.microsoft.com/library/gg682169.aspx) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-123">For more information, see [Collections in Configuration Manager](http://technet.microsoft.com/library/gg682169.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="e6e03-124">Los **paquetes y programas** suelen representar aplicaciones de software que se van a instalar en un equipo cliente, aunque también pueden contener archivos individuales, actualizaciones o incluso comandos individuales.</span><span class="sxs-lookup"><span data-stu-id="e6e03-124">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="e6e03-125">Para obtener más información, vea el tema sobre [paquetes y programas en Configuration Manager](http://technet.microsoft.com/library/gg699369.aspx) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-125">For more information, see [Packages and Programs in Configuration Manager](http://technet.microsoft.com/library/gg699369.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="e6e03-126">Los **puntos de distribución** son roles del sistema de sitio de Configuration Manager que almacenan los archivos necesarios para que el software se ejecute en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-126">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="e6e03-127">Cuando un cliente de Configuration Manager recibe y procesa una implementación de software, se pone en contacto con un punto de distribución para descargar el contenido asociado al software e iniciar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e03-127">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="e6e03-128">Para obtener más información, vea la [introducción a la administración de contenido en Configuration Manager](http://technet.microsoft.com/library/gg682083.aspx) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-128">For more information, see [Introduction to content Management in Configuration Manager](http://technet.microsoft.com/library/gg682083.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="e6e03-129">Las **implementaciones** indican a los miembros correspondientes de la colección de destino especificada que instalen el paquete de software.</span><span class="sxs-lookup"><span data-stu-id="e6e03-129">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span> <span data-ttu-id="e6e03-130">Para obtener más información, vea [cómo implementar aplicaciones en Configuration Manager](http://technet.microsoft.com/library/gg682082.aspx) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-130">For more information, see [How to Deploy Applications in Configuration Manager](http://technet.microsoft.com/library/gg682082.aspx) in the Configuration Manager documentation library.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6e03-131">Los procedimientos de este tema contienen valores típicos para crear e implementar un paquete y un programa y puede que no cubran todos los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="e6e03-131">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="e6e03-132">Para ver otras opciones de implementación de Configuration Manager, consulte la [biblioteca de documentación de Configuration Manager](http://technet.microsoft.com/library/gg682041.aspx).</span><span class="sxs-lookup"><span data-stu-id="e6e03-132">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](http://technet.microsoft.com/library/gg682041.aspx).</span></span>  
  
<a name="deploying_in_a_test_environment"></a>   
## <a name="deploying-the-net-framework"></a><span data-ttu-id="e6e03-133">Implementación de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6e03-133">Deploying the .NET Framework</span></span>  
 <span data-ttu-id="e6e03-134">Puede usar System Center 2012 Configuration Manager para implementar una instalación silenciosa de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], donde los usuarios no interactúan con el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e03-134">You can use System Center 2012 Configuration Manager to deploy a silent installation of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], where the users do not interact with the installation process.</span></span> <span data-ttu-id="e6e03-135">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e6e03-135">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="e6e03-136">[Cree una colección](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="e6e03-136">[Create a collection](#creating_a_collection).</span></span>  
  
2.  <span data-ttu-id="e6e03-137">[Cree un paquete y un programa para el paquete redistribuible de .NET Framework](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="e6e03-137">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>  
  
3.  <span data-ttu-id="e6e03-138">[Seleccione un punto de distribución](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="e6e03-138">[Select a distribution point](#select_dist_point).</span></span>  
  
4.  <span data-ttu-id="e6e03-139">[Implemente el paquete](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="e6e03-139">[Deploy the package](#deploying_package).</span></span>  
  
<a name="creating_a_collection"></a>   
### <a name="create-a-collection"></a><span data-ttu-id="e6e03-140">Crear una colección</span><span class="sxs-lookup"><span data-stu-id="e6e03-140">Create a collection</span></span>  
 <span data-ttu-id="e6e03-141">En este paso, se seleccionan los equipos donde se implementará el paquete y el programa y se agruparán en una colección de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e6e03-141">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="e6e03-142">Para crear una colección en Configuration Manager, puede usar reglas de pertenencia directa (donde se especifican manualmente los miembros de la colección) o reglas de consulta (donde Configuration Manager determina los miembros de la colección en función de los criterios que especifique el usuario).</span><span class="sxs-lookup"><span data-stu-id="e6e03-142">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="e6e03-143">Para obtener más información sobre las reglas de pertenencia, incluidas las reglas de consulta y las reglas directas, vea la [introducción a las colecciones en Configuration Manager](http://technet.microsoft.com/library/gg682177.aspx) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-143">For more information about membership rules, including queries and direct rules, see [Introduction to Collections in Configuration Manager](http://technet.microsoft.com/library/gg682177.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
 <span data-ttu-id="e6e03-144">Para crear una colección:</span><span class="sxs-lookup"><span data-stu-id="e6e03-144">To create a collection:</span></span>  
  
1.  <span data-ttu-id="e6e03-145">En la consola de Configuration Manager, elija **Activos y compatibilidad**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-145">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>  
  
2.  <span data-ttu-id="e6e03-146">En el área de trabajo **Activos y compatibilidad**, elija **Recopilaciones de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-146">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>  
  
3.  <span data-ttu-id="e6e03-147">En la pestaña **Inicio** del grupo **Crear**, elija **Crear recopilación de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-147">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>  
  
4.  <span data-ttu-id="e6e03-148">En la página **General** del **Asistente para crear recopilación de dispositivos**, escriba un nombre para la colección.</span><span class="sxs-lookup"><span data-stu-id="e6e03-148">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>  
  
5.  <span data-ttu-id="e6e03-149">Elija **Examinar** para especificar una recopilación de restricción.</span><span class="sxs-lookup"><span data-stu-id="e6e03-149">Choose **Browse** to specify a limiting collection.</span></span>  
  
6.  <span data-ttu-id="e6e03-150">En la página **Reglas de pertenencia**, elija **Agregar regla** y, a continuación, **Regla directa** para abrir el **Asistente para crear reglas de pertenencia directa**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-150">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="e6e03-151">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-151">Choose **Next**.</span></span>  
  
7.  <span data-ttu-id="e6e03-152">En la página **Buscar recursos**, en la lista **Clase de recurso**, elija **Recurso del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-152">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="e6e03-153">En la lista **Nombre del atributo**, elija **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-153">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="e6e03-154">En el campo **Valor**, escriba `%` y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-154">In the **Value** field, enter `%`, and then choose **Next**.</span></span>  
  
8.  <span data-ttu-id="e6e03-155">En la página **Seleccionar recursos**, active la casilla de cada equipo en el que desea implementar .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e03-155">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="e6e03-156">Elija **Siguiente** y finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-156">Choose **Next**, and then complete the wizard.</span></span>  
  
9. <span data-ttu-id="e6e03-157">En la página **Reglas de pertenencia** del **Asistente para crear recopilación de dispositivos**, elija **Siguiente** y finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-157">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="e6e03-158">Para obtener más información sobre las recopilaciones, vea el tema sobre [colecciones en Configuration Manager](http://technet.microsoft.com/library/bb693730.aspx) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-158">For more information about collections, see [Collections in Configuration Manager](http://technet.microsoft.com/library/bb693730.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="creating_a_package"></a>   
### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="e6e03-159">Cree un paquete y un programa para el paquete redistribuible de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6e03-159">Create a package and program for the .NET Framework redistributable package</span></span>  
 <span data-ttu-id="e6e03-160">Mediante los siguientes pasos se crea manualmente un paquete para .NET Framework redistribuible.</span><span class="sxs-lookup"><span data-stu-id="e6e03-160">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="e6e03-161">El paquete contiene los parámetros especificados para instalar .NET Framework y la ubicación desde la que se distribuirá el paquete a los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="e6e03-161">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>  
  
 <span data-ttu-id="e6e03-162">Para crear un paquete:</span><span class="sxs-lookup"><span data-stu-id="e6e03-162">To create a package:</span></span>  
  
1.  <span data-ttu-id="e6e03-163">En la consola de Configuration Manager, elija **Biblioteca de software**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-163">In the Configuration Manager console, choose **Software Library**..</span></span>  
  
2.  <span data-ttu-id="e6e03-164">En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-164">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="e6e03-165">En la pestaña **Inicio**, en el grupo **Crear**, elija **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-165">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>  
  
4.  <span data-ttu-id="e6e03-166">En la página **Paquete** del **Asistente para crear paquetes y programas**, escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e6e03-166">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    -   <span data-ttu-id="e6e03-167">Nombre: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="e6e03-167">Name: `.NET Framework 4.5`</span></span>  
  
    -   <span data-ttu-id="e6e03-168">Fabricante: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="e6e03-168">Manufacturer: `Microsoft`</span></span>  
  
    -   <span data-ttu-id="e6e03-169">Idioma.</span><span class="sxs-lookup"><span data-stu-id="e6e03-169">Language.</span></span> `English (US)`  
  
5.  <span data-ttu-id="e6e03-170">Elija **Este paquete contiene archivos de origen** y, después, **Examinar** para seleccionar la carpeta local o de red que contiene los archivos de instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e03-170">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="e6e03-171">Una vez seleccionada la carpeta, elija **Aceptar** y **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-171">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>  
  
6.  <span data-ttu-id="e6e03-172">En la página **Tipo de programa** del asistente, elija **Programa estándar** y, después, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-172">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="e6e03-173">En la página **Programa** del **Asistente para crear paquetes y programas**, escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e6e03-173">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="e6e03-174">**Nombre:** `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="e6e03-174">**Name:** `.NET Framework 4.5`</span></span>  
  
    2.  <span data-ttu-id="e6e03-175">**Línea de comandos:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (las opciones de la línea de comandos se describen en la tabla que aparece después de estos pasos)</span><span class="sxs-lookup"><span data-stu-id="e6e03-175">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>  
  
    3.  <span data-ttu-id="e6e03-176">**Ejecutar:** elija **Oculto**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-176">**Run:** Choose **Hidden**.</span></span>  
  
    4.  <span data-ttu-id="e6e03-177">**El programa se puede ejecutar:** elija la opción que especifica que el programa puede ejecutarse independientemente de si un usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="e6e03-177">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>  
  
8.  <span data-ttu-id="e6e03-178">En la página **Requisitos**, elija **Siguiente** para aceptar los valores predeterminados y, después, finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-178">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="e6e03-179">En la tabla siguiente se describen las opciones de la línea de comandos especificadas en el paso 7.</span><span class="sxs-lookup"><span data-stu-id="e6e03-179">The following table describes the command-line options specified in step 7.</span></span>  
  
|<span data-ttu-id="e6e03-180">Opción</span><span class="sxs-lookup"><span data-stu-id="e6e03-180">Option</span></span>|<span data-ttu-id="e6e03-181">Description</span><span class="sxs-lookup"><span data-stu-id="e6e03-181">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e6e03-182">**/q**</span><span class="sxs-lookup"><span data-stu-id="e6e03-182">**/q**</span></span>|<span data-ttu-id="e6e03-183">Establece el modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="e6e03-183">Sets quiet mode.</span></span> <span data-ttu-id="e6e03-184">No se requiere proporcionar ningún dato y no se muestra ningún resultado.</span><span class="sxs-lookup"><span data-stu-id="e6e03-184">No user input is required, and no output is shown.</span></span>|  
|<span data-ttu-id="e6e03-185">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="e6e03-185">**/norestart**</span></span>|<span data-ttu-id="e6e03-186">Evita que el programa de instalación se reinicie automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-186">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="e6e03-187">Si usa esta opción, Configuration Manager debe controlar el reinicio del equipo.</span><span class="sxs-lookup"><span data-stu-id="e6e03-187">If you use this option, Configuration Manager must handle the computer restart.</span></span>|  
|<span data-ttu-id="e6e03-188">**/chainingpackage** *NombrePaquete*</span><span class="sxs-lookup"><span data-stu-id="e6e03-188">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="e6e03-189">Especifica el nombre del paquete que realiza el encadenamiento.</span><span class="sxs-lookup"><span data-stu-id="e6e03-189">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="e6e03-190">Esta información se notifica con otra información de sesión de instalación para los usuarios que se hayan registrado en el [Programa para la mejora de la experiencia del usuario (CEIP) de Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=248244).</span><span class="sxs-lookup"><span data-stu-id="e6e03-190">This information is reported with other installation session information for those who have signed up for the [Microsoft Customer Experience Improvement Program (CEIP)](http://go.microsoft.com/fwlink/p/?LinkId=248244).</span></span> <span data-ttu-id="e6e03-191">Si el nombre del paquete incluye espacios, use comillas dobles como delimitadores; por ejemplo: **/chainingpackage "Chaining Product"**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-191">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|  
  
 <span data-ttu-id="e6e03-192">Mediante estos pasos se crea un paquete denominado .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e6e03-192">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="e6e03-193">El programa implementa una instalación silenciosa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e6e03-193">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="e6e03-194">En una instalación silenciosa, los usuarios no interactúan con el proceso de instalación y la aplicación de encadenamiento tiene que capturar el código devuelto y controlar el reinicio; vea [Getting Progress Information from an Installation Package (Obtener información de progreso de un paquete de instalación)](http://go.microsoft.com/fwlink/?LinkId=179606).</span><span class="sxs-lookup"><span data-stu-id="e6e03-194">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](http://go.microsoft.com/fwlink/?LinkId=179606).</span></span>  
 
<a name="select_dist_point"></a>   
### <a name="select-a-distribution-point"></a><span data-ttu-id="e6e03-195">Seleccionar un punto de distribución</span><span class="sxs-lookup"><span data-stu-id="e6e03-195">Select a distribution point</span></span>  
 <span data-ttu-id="e6e03-196">Para distribuir el paquete y el programa a los equipos cliente de un servidor, deberá designar primero un sistema de sitio como punto de distribución y después distribuir el paquete al punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="e6e03-196">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>  
  
 <span data-ttu-id="e6e03-197">Realice los pasos siguientes para seleccionar un punto de distribución para el paquete de .NET Framework 4.5 que ha creado en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="e6e03-197">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>  
  
1.  <span data-ttu-id="e6e03-198">En la consola de Configuration Manager, elija **Biblioteca de software**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-198">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="e6e03-199">En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-199">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="e6e03-200">En la lista de paquetes, seleccione el paquete **.NET Framework 4.5** que creó en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="e6e03-200">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>  
  
4.  <span data-ttu-id="e6e03-201">En la pestaña **Inicio**, en el grupo **Implementación**, elija **Distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-201">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>  
  
5.  <span data-ttu-id="e6e03-202">En la pestaña **General** del **Asistente para distribuir contenido**, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-202">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>  
  
6.  <span data-ttu-id="e6e03-203">En la página **Destino del contenido** del asistente, elija **Agregar** y, después, **Punto de distribución**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-203">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>  
  
7.  <span data-ttu-id="e6e03-204">En el cuadro de diálogo **Agregar puntos de distribución**, seleccione los puntos de distribución que hospedarán el paquete y el programa y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-204">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>  
  
8.  <span data-ttu-id="e6e03-205">Complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-205">Complete the wizard.</span></span>  
  
 <span data-ttu-id="e6e03-206">Ahora el paquete contiene toda la información necesaria para realizar una implementación silenciosa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e6e03-206">The package now contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="e6e03-207">Antes de implementar el paquete y el programa, compruebe que se haya instalado en el punto de distribución; vea la sección de supervisión de contenido del tema sobre [operaciones y mantenimiento de administración de contenido en Configuration Manager](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e6e03-207">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Monitor Content" section of [Operations and Maintenance for Content Management in Configuration Manager](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="deploying_package"></a>   
### <a name="deploy-the-package"></a><span data-ttu-id="e6e03-208">Implementar el paquete</span><span class="sxs-lookup"><span data-stu-id="e6e03-208">Deploy the package</span></span>  
 <span data-ttu-id="e6e03-209">Para implementar el paquete y el programa de .NET Framework 4.5:</span><span class="sxs-lookup"><span data-stu-id="e6e03-209">To deploy the .NET Framework 4.5 package and program:</span></span>  
  
1.  <span data-ttu-id="e6e03-210">En la consola de Configuration Manager, elija **Biblioteca de software**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-210">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="e6e03-211">En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-211">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="e6e03-212">En la lista de paquetes, seleccione el paquete que creó denominado **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-212">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>  
  
4.  <span data-ttu-id="e6e03-213">En la pestaña **Inicio**, en el grupo **Implementación**, elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-213">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>  
  
5.  <span data-ttu-id="e6e03-214">En la página **General** del **Asistente para implementar software**, elija **Examinar** y, a continuación, seleccione la colección que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-214">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="e6e03-215">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-215">Choose **Next**.</span></span>  
  
6.  <span data-ttu-id="e6e03-216">En la página **Contenido** del asistente, compruebe que se muestra el punto desde el que desea distribuir el software y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-216">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="e6e03-217">En la página **Configuración de implementación** del asistente, confirme que la **Acción** está establecida en **Instalar** y el **Propósito** en **Requerido**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-217">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="e6e03-218">Esto garantiza que el paquete de software sea una instalación obligatoria en los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="e6e03-218">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="e6e03-219">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-219">Choose **Next**.</span></span>  
  
8.  <span data-ttu-id="e6e03-220">En la página **Programación** del asistente, especifique cuándo desea que se instale .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e03-220">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="e6e03-221">Puede elegir **Nuevo** para asignar un tiempo de instalación o bien indicar al software que realice la instalación cuando el usuario inicie o cierre sesión o lo antes posible.</span><span class="sxs-lookup"><span data-stu-id="e6e03-221">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="e6e03-222">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-222">Choose **Next**.</span></span>  
  
9. <span data-ttu-id="e6e03-223">En la página **Experiencia del usuario** del asistente, use los valores predeterminados y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-223">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="e6e03-224">El entorno de producción puede tener directivas que requieran selecciones distintas para la programación de distribución.</span><span class="sxs-lookup"><span data-stu-id="e6e03-224">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="e6e03-225">Para obtener información sobre estas opciones, vea el tema sobre [la pestaña programación de las propiedades de nombre de anuncio](http://technet.microsoft.com/library/bb694016.aspx) en TechNet Library.</span><span class="sxs-lookup"><span data-stu-id="e6e03-225">For information about these options, see [Advertisement Name Properties: Schedule Tab](http://technet.microsoft.com/library/bb694016.aspx) in the TechNet Library.</span></span>  
  
10. <span data-ttu-id="e6e03-226">En la página **Puntos de distribución** del asistente, use los valores predeterminados y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-226">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>  
  
11. <span data-ttu-id="e6e03-227">Complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-227">Complete the wizard.</span></span> <span data-ttu-id="e6e03-228">Puede supervisar el progreso de la implementación en el nodo **Implementaciones** del área de trabajo **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="e6e03-228">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>  
  
 <span data-ttu-id="e6e03-229">El paquete se implementará ahora en la colección de destino y se iniciará la instalación silenciosa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e6e03-229">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="e6e03-230">Para obtener información sobre los códigos de error de instalación de .NET Framework 4.5, vea la sección [Códigos devueltos](#return_codes) en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="e6e03-230">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>  
  
<a name="resources"></a>   
## <a name="resources"></a><span data-ttu-id="e6e03-231">Recursos</span><span class="sxs-lookup"><span data-stu-id="e6e03-231">Resources</span></span>  
 <span data-ttu-id="e6e03-232">Para obtener más información sobre la infraestructura para probar la implementación del paquete redistribuible de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], consulte los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="e6e03-232">For more information about the infrastructure for testing the deployment of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable package, see the following resources.</span></span>  
  
 <span data-ttu-id="e6e03-233">**Active Directory, DNS, DHCP:**</span><span class="sxs-lookup"><span data-stu-id="e6e03-233">**Active Directory, DNS, DHCP:**</span></span>  
  
-   [<span data-ttu-id="e6e03-234">Servicios de dominio de Active Directory para Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="e6e03-234">Active Directory Domain Services for Windows Server 2008</span></span>](http://technet.microsoft.com/library/dd378891.aspx)  
  
-   [<span data-ttu-id="e6e03-235">Servidor DNS</span><span class="sxs-lookup"><span data-stu-id="e6e03-235">DNS Server</span></span>](http://technet.microsoft.com/library/cc732997.aspx)  
  
-   [<span data-ttu-id="e6e03-236">Servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="e6e03-236">DHCP Server</span></span>](http://technet.microsoft.com/library/cc896553.aspx)  
  
 <span data-ttu-id="e6e03-237">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="e6e03-237">**SQL Server 2008:**</span></span>  
  
-   [<span data-ttu-id="e6e03-238">Instalar SQL Server 2008 (vídeo de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e6e03-238">Installing SQL Server 2008 (SQL Server Video)</span></span>](http://technet.microsoft.com/library/dd299415.aspx)  
  
-   [<span data-ttu-id="e6e03-239">Información general sobre la seguridad de SQL Server 2008 para administradores de bases de datos</span><span class="sxs-lookup"><span data-stu-id="e6e03-239">SQL Server 2008 Security Overview for Database Administrators</span></span>](http://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)  
  
 <span data-ttu-id="e6e03-240">**System Center 2012 Configuration Manager (punto de administración, punto de distribución):**</span><span class="sxs-lookup"><span data-stu-id="e6e03-240">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>  
  
-   [<span data-ttu-id="e6e03-241">Administración del sitio de System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e6e03-241">Site Administration for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg681983.aspx)  
  
-   [<span data-ttu-id="e6e03-242">Planeación e implementación de sitio único de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e6e03-242">Configuration Manager Single Site Planning and Deployment</span></span>](http://technet.microsoft.com/library/bb680961.aspx)  
  
 <span data-ttu-id="e6e03-243">**Cliente de System Center 2012 Configuration Manager para equipos Windows:**</span><span class="sxs-lookup"><span data-stu-id="e6e03-243">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>  
  
-   [<span data-ttu-id="e6e03-244">Implementación de clientes para System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e6e03-244">Deploying Clients for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg699391.aspx)  
  
<a name="troubleshooting"></a>   
## <a name="troubleshooting"></a><span data-ttu-id="e6e03-245">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e6e03-245">Troubleshooting</span></span>  
  
### <a name="log-file-locations"></a><span data-ttu-id="e6e03-246">Ubicaciones de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="e6e03-246">Log file locations</span></span>  
 <span data-ttu-id="e6e03-247">Los siguientes archivos de registro se generan durante la configuración de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e6e03-247">The following log files are generated during .NET Framework setup:</span></span>  
  
 <span data-ttu-id="e6e03-248">%temp%\Microsoft .NET Framework *versión*\*.txt</span><span class="sxs-lookup"><span data-stu-id="e6e03-248">%temp%\Microsoft .NET Framework *version*\*.txt</span></span>  
 <span data-ttu-id="e6e03-249">%temp%\Microsoft .NET Framework *versión*\*.html</span><span class="sxs-lookup"><span data-stu-id="e6e03-249">%temp%\Microsoft .NET Framework *version*\*.html</span></span>  
  
 <span data-ttu-id="e6e03-250">donde *versión* es la versión de .NET Framework que va a instalar, como 4.5 o 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="e6e03-250">where *version* is the version of the .NET Framework that you're installing, such as 4.5 or 4.7.2.</span></span>  
 
 <span data-ttu-id="e6e03-251">También puede especificar el directorio en el que se escriben los archivos de registro mediante la opción de la línea de comandos `/log` en el comando de instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6e03-251">You can also specify the directory to which log files are written by using the `/log` command-line option in the .NET Framework installation command.</span></span> <span data-ttu-id="e6e03-252">Para obtener más información, consulte la [Guía de implementación de .NET Framework para desarrolladores](deployment-guide-for-developers.md#command-line-options).</span><span class="sxs-lookup"><span data-stu-id="e6e03-252">For more information, see [.NET Framework deployment guide for developers](deployment-guide-for-developers.md#command-line-options).</span></span> 
 
 <span data-ttu-id="e6e03-253">Puede usar la [herramienta de recopilación de registros](https://www.microsoft.com/download/details.aspx?id=12493) para recopilar los archivos de registro de .NET Framework y crear un archivo .cab comprimido que reduzca el tamaño de los archivos.</span><span class="sxs-lookup"><span data-stu-id="e6e03-253">You can use the [log collection tool](https://www.microsoft.com/download/details.aspx?id=12493) to collect the .NET Framework log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>  
  
<a name="return_codes"></a>   
### <a name="return-codes"></a><span data-ttu-id="e6e03-254">Códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="e6e03-254">Return codes</span></span>  
 <span data-ttu-id="e6e03-255">En la siguiente tabla se muestra una lista de los códigos devueltos más comunes del programa de instalación redistribuible de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e03-255">The following table lists the most common return codes from the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable installation program.</span></span> <span data-ttu-id="e6e03-256">Los códigos devueltos son los mismos para todas las versiones del instalador.</span><span class="sxs-lookup"><span data-stu-id="e6e03-256">The return codes are the same for all versions of the installer.</span></span>  
  
 <span data-ttu-id="e6e03-257">Para obtener vínculos a información detallada, vea la sección siguiente, [Descargar códigos de error](#additional_error_codes).</span><span class="sxs-lookup"><span data-stu-id="e6e03-257">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>  
  
|<span data-ttu-id="e6e03-258">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="e6e03-258">Return code</span></span>|<span data-ttu-id="e6e03-259">Description</span><span class="sxs-lookup"><span data-stu-id="e6e03-259">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e6e03-260">0</span><span class="sxs-lookup"><span data-stu-id="e6e03-260">0</span></span>|<span data-ttu-id="e6e03-261">La instalación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-261">Installation completed successfully.</span></span>|  
|<span data-ttu-id="e6e03-262">1602</span><span class="sxs-lookup"><span data-stu-id="e6e03-262">1602</span></span>|<span data-ttu-id="e6e03-263">El usuario canceló la instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e03-263">The user canceled installation.</span></span>|  
|<span data-ttu-id="e6e03-264">1603</span><span class="sxs-lookup"><span data-stu-id="e6e03-264">1603</span></span>|<span data-ttu-id="e6e03-265">Error irrecuperable durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="e6e03-265">A fatal error occurred during installation.</span></span>|  
|<span data-ttu-id="e6e03-266">1641</span><span class="sxs-lookup"><span data-stu-id="e6e03-266">1641</span></span>|<span data-ttu-id="e6e03-267">Para completar la instalación es necesario reiniciar.</span><span class="sxs-lookup"><span data-stu-id="e6e03-267">A restart is required to complete the installation.</span></span> <span data-ttu-id="e6e03-268">Este mensaje indica que la instalación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-268">This message indicates success.</span></span>|  
|<span data-ttu-id="e6e03-269">3010</span><span class="sxs-lookup"><span data-stu-id="e6e03-269">3010</span></span>|<span data-ttu-id="e6e03-270">Para completar la instalación es necesario reiniciar.</span><span class="sxs-lookup"><span data-stu-id="e6e03-270">A restart is required to complete the installation.</span></span> <span data-ttu-id="e6e03-271">Este mensaje indica que la instalación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6e03-271">This message indicates success.</span></span>|  
|<span data-ttu-id="e6e03-272">5100</span><span class="sxs-lookup"><span data-stu-id="e6e03-272">5100</span></span>|<span data-ttu-id="e6e03-273">El equipo del usuario no cumple los requisitos del sistema.</span><span class="sxs-lookup"><span data-stu-id="e6e03-273">The user's computer does not meet system requirements.</span></span>|  
  
<a name="additional_error_codes"></a>   
### <a name="download-error-codes"></a><span data-ttu-id="e6e03-274">Descargar códigos de error</span><span class="sxs-lookup"><span data-stu-id="e6e03-274">Download error codes</span></span>  
  
-   [<span data-ttu-id="e6e03-275">Códigos de error del Servicio de transferencia inteligente en segundo plano (BITS)</span><span class="sxs-lookup"><span data-stu-id="e6e03-275">Background Intelligent Transfer Service (BITS) error codes</span></span>](http://msdn.microsoft.com/library/aa362823.aspx)  
  
-   [<span data-ttu-id="e6e03-276">Códigos de error del moniker de dirección URL</span><span class="sxs-lookup"><span data-stu-id="e6e03-276">URL moniker error codes</span></span>](http://msdn.microsoft.com/library/ms775145.aspx)  
  
-   [<span data-ttu-id="e6e03-277">Códigos de error de WinHttp</span><span class="sxs-lookup"><span data-stu-id="e6e03-277">WinHttp error codes</span></span>](http://msdn.microsoft.com/library/aa383770.aspx)  
  
 <span data-ttu-id="e6e03-278">Otros códigos de error:</span><span class="sxs-lookup"><span data-stu-id="e6e03-278">Other error codes:</span></span>  
  
-   [<span data-ttu-id="e6e03-279">Códigos de error de Windows Installer</span><span class="sxs-lookup"><span data-stu-id="e6e03-279">Windows Installer error codes</span></span>](http://msdn.microsoft.com/library/aa368542.aspx)  
  
-   [<span data-ttu-id="e6e03-280">Códigos de resultado del Agente de Windows Update</span><span class="sxs-lookup"><span data-stu-id="e6e03-280">Windows Update Agent result codes</span></span>](http://technet.microsoft.com/library/cc720442.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="e6e03-281">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6e03-281">See Also</span></span>  
 [<span data-ttu-id="e6e03-282">Guía de implementación para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="e6e03-282">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [<span data-ttu-id="e6e03-283">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="e6e03-283">System Requirements</span></span>](../../../docs/framework/get-started/system-requirements.md)
