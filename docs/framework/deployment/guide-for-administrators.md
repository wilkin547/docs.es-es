---
title: Guía de implementación de .NET Framework para administradores
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
ms.openlocfilehash: be15ce0b0bed37da6fe400e98bfdd118c48f7ba0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716537"
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="7892c-102">Guía de implementación de .NET Framework para administradores</span><span class="sxs-lookup"><span data-stu-id="7892c-102">.NET Framework Deployment Guide for Administrators</span></span>

<span data-ttu-id="7892c-103">En este artículo paso a paso se describe cómo puede implementar un administrador del sistema .NET Framework 4.5 y sus dependencias del sistema en una red mediante Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7892c-103">This step-by-step article describes how a system administrator can deploy the .NET Framework 4.5 and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="7892c-104">En este artículo se supone que todos los equipos cliente de destino cumplen los requisitos mínimos para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7892c-104">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="7892c-105">Para obtener una lista de los requisitos de software y hardware para instalar .NET Framework 4.5, consulte [Requisitos de sistema](../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7892c-105">For a list of the software and hardware requirements for installing the .NET Framework 4.5, see [System Requirements](../get-started/system-requirements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7892c-106">El software al que se hace referencia en este documento, a título enunciativo y en ningún caso limitativo, .NET Framework 4.5, Configuration Manager y Active Directory, está sujeto a los términos y condiciones de licencia.</span><span class="sxs-lookup"><span data-stu-id="7892c-106">The software referenced in this document, including, without limitation, the .NET Framework 4.5, Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="7892c-107">En estas instrucciones se asume que los usuarios con la licencia apropiada del software han leído y aceptado dichos términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="7892c-107">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="7892c-108">Estas instrucciones no anulan ninguno de los términos y condiciones de dichos contratos de licencia.</span><span class="sxs-lookup"><span data-stu-id="7892c-108">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>
>
> <span data-ttu-id="7892c-109">Para obtener información sobre el soporte técnico de .NET Framework, consulte [Directiva de ciclo soporte técnico oficial de .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) en el sitio web de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7892c-109">For information about support for the .NET Framework, see [.NET Framework official support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) on the Microsoft Support website.</span></span>

<span data-ttu-id="7892c-110">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="7892c-110">This topic contains the following sections:</span></span>

- [<span data-ttu-id="7892c-111">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="7892c-111">The deployment process</span></span>](#the_deployment_process)
- [<span data-ttu-id="7892c-112">Implementación de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7892c-112">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)
- [<span data-ttu-id="7892c-113">Crear una colección</span><span class="sxs-lookup"><span data-stu-id="7892c-113">Create a collection</span></span>](#creating_a_collection)
- [<span data-ttu-id="7892c-114">Crear un paquete y un programa</span><span class="sxs-lookup"><span data-stu-id="7892c-114">Create a package and program</span></span>](#creating_a_package)
- [<span data-ttu-id="7892c-115">Seleccionar un punto de distribución</span><span class="sxs-lookup"><span data-stu-id="7892c-115">Select a distribution point</span></span>](#select_dist_point)
- [<span data-ttu-id="7892c-116">Implementar el paquete</span><span class="sxs-lookup"><span data-stu-id="7892c-116">Deploy the package</span></span>](#deploying_package)
- [<span data-ttu-id="7892c-117">Recursos</span><span class="sxs-lookup"><span data-stu-id="7892c-117">Resources</span></span>](#resources)
- [<span data-ttu-id="7892c-118">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="7892c-118">Troubleshooting</span></span>](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a><span data-ttu-id="7892c-119">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="7892c-119">The deployment process</span></span>

<span data-ttu-id="7892c-120">Una vez implementada la infraestructura de apoyo, se utiliza Configuration Manager para implementar el paquete redistribuible de .NET Framework en equipos de la red.</span><span class="sxs-lookup"><span data-stu-id="7892c-120">When you have the supporting infrastructure in place, you use Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="7892c-121">La creación de la infraestructura implica crear y definir cinco áreas primarias: colecciones, un paquete y un programa para el software, puntos de distribución e implementaciones.</span><span class="sxs-lookup"><span data-stu-id="7892c-121">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>

- <span data-ttu-id="7892c-122">Las **colecciones** son grupos de recursos de Configuration Manager, tales como usuarios, grupos de usuarios o equipos, en los que se implementa .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7892c-122">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="7892c-123">Para más información, consulte [Introducción a las recopilaciones en Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7892c-123">For more information, see [Introduction to collections in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="7892c-124">Los **paquetes y programas** suelen representar aplicaciones de software que se van a instalar en un equipo cliente, aunque también pueden contener archivos individuales, actualizaciones o incluso comandos individuales.</span><span class="sxs-lookup"><span data-stu-id="7892c-124">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="7892c-125">Para obtener más información, consulte el tema sobre [paquetes y programas en Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7892c-125">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="7892c-126">Los **puntos de distribución** son roles del sistema de sitio de Configuration Manager que almacenan los archivos necesarios para que el software se ejecute en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="7892c-126">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="7892c-127">Cuando un cliente de Configuration Manager recibe y procesa una implementación de software, se pone en contacto con un punto de distribución para descargar el contenido asociado al software e iniciar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="7892c-127">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="7892c-128">Para más información, vea [Aspectos básicos de la administración de contenido en Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7892c-128">For more information, see [Fundamental concepts for content management in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="7892c-129">Las **implementaciones** indican a los miembros correspondientes de la colección de destino especificada que instalen el paquete de software.</span><span class="sxs-lookup"><span data-stu-id="7892c-129">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7892c-130">Los procedimientos de este tema contienen valores típicos para crear e implementar un paquete y un programa y puede que no cubran todos los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="7892c-130">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="7892c-131">Para ver otras opciones de implementación de Configuration Manager, consulte la [biblioteca de documentación de Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).</span><span class="sxs-lookup"><span data-stu-id="7892c-131">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).</span></span>

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-the-net-framework"></a><span data-ttu-id="7892c-132">Implementación de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7892c-132">Deploying the .NET Framework</span></span>

<span data-ttu-id="7892c-133">Se puede usar Configuration Manager para implementar una instalación silenciosa de .NET Framework 4.5, donde los usuarios no interactúan con el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="7892c-133">You can use Configuration Manager to deploy a silent installation of the .NET Framework 4.5, where the users do not interact with the installation process.</span></span> <span data-ttu-id="7892c-134">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7892c-134">Follow these steps:</span></span>

1. <span data-ttu-id="7892c-135">[Cree una colección](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="7892c-135">[Create a collection](#creating_a_collection).</span></span>

2. <span data-ttu-id="7892c-136">[Cree un paquete y un programa para el paquete redistribuible de .NET Framework](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="7892c-136">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>

3. <span data-ttu-id="7892c-137">[Seleccione un punto de distribución](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="7892c-137">[Select a distribution point](#select_dist_point).</span></span>

4. <span data-ttu-id="7892c-138">[Implemente el paquete](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="7892c-138">[Deploy the package](#deploying_package).</span></span>

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a><span data-ttu-id="7892c-139">Crear una colección</span><span class="sxs-lookup"><span data-stu-id="7892c-139">Create a collection</span></span>

<span data-ttu-id="7892c-140">En este paso, se seleccionan los equipos donde se implementará el paquete y el programa y se agruparán en una colección de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7892c-140">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="7892c-141">Para crear una colección en Configuration Manager, puede usar reglas de pertenencia directa (donde se especifican manualmente los miembros de la colección) o reglas de consulta (donde Configuration Manager determina los miembros de la colección en función de los criterios que especifique el usuario).</span><span class="sxs-lookup"><span data-stu-id="7892c-141">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="7892c-142">Para obtener más información sobre las reglas de pertenencia, incluidas las reglas de consulta y las reglas directas, consulte [Introducción a las recopilaciones en Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7892c-142">For more information about membership rules, including queries and direct rules, see [Introduction to collections in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager Documentation Library.</span></span>

<span data-ttu-id="7892c-143">Para crear una colección:</span><span class="sxs-lookup"><span data-stu-id="7892c-143">To create a collection:</span></span>

1. <span data-ttu-id="7892c-144">En la consola de Configuration Manager, elija **Activos y compatibilidad**.</span><span class="sxs-lookup"><span data-stu-id="7892c-144">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>

2. <span data-ttu-id="7892c-145">En el área de trabajo **Activos y compatibilidad**, elija **Recopilaciones de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="7892c-145">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>

3. <span data-ttu-id="7892c-146">En la pestaña **Inicio** del grupo **Crear**, elija **Crear recopilación de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="7892c-146">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>

4. <span data-ttu-id="7892c-147">En la página **General** del **Asistente para crear recopilación de dispositivos**, escriba un nombre para la colección.</span><span class="sxs-lookup"><span data-stu-id="7892c-147">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>

5. <span data-ttu-id="7892c-148">Elija **Examinar** para especificar una recopilación de restricción.</span><span class="sxs-lookup"><span data-stu-id="7892c-148">Choose **Browse** to specify a limiting collection.</span></span>

6. <span data-ttu-id="7892c-149">En la página **Reglas de pertenencia**, elija **Agregar regla** y, a continuación, **Regla directa** para abrir el **Asistente para crear reglas de pertenencia directa**.</span><span class="sxs-lookup"><span data-stu-id="7892c-149">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="7892c-150">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-150">Choose **Next**.</span></span>

7. <span data-ttu-id="7892c-151">En la página **Buscar recursos**, en la lista **Clase de recurso**, elija **Recurso del sistema**.</span><span class="sxs-lookup"><span data-stu-id="7892c-151">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="7892c-152">En la lista **Nombre del atributo**, elija **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="7892c-152">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="7892c-153">En el campo **Valor**, escriba `%` y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-153">In the **Value** field, enter `%`, and then choose **Next**.</span></span>

8. <span data-ttu-id="7892c-154">En la página **Seleccionar recursos**, active la casilla de cada equipo en el que desea implementar .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7892c-154">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="7892c-155">Elija **Siguiente** y finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="7892c-155">Choose **Next**, and then complete the wizard.</span></span>

9. <span data-ttu-id="7892c-156">En la página **Reglas de pertenencia** del **Asistente para crear recopilación de dispositivos**, elija **Siguiente** y finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="7892c-156">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="7892c-157">Cree un paquete y un programa para el paquete redistribuible de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7892c-157">Create a package and program for the .NET Framework redistributable package</span></span>

<span data-ttu-id="7892c-158">Mediante los siguientes pasos se crea manualmente un paquete para .NET Framework redistribuible.</span><span class="sxs-lookup"><span data-stu-id="7892c-158">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="7892c-159">El paquete contiene los parámetros especificados para instalar .NET Framework y la ubicación desde la que se distribuirá el paquete a los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="7892c-159">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>

<span data-ttu-id="7892c-160">Para crear un paquete:</span><span class="sxs-lookup"><span data-stu-id="7892c-160">To create a package:</span></span>

1. <span data-ttu-id="7892c-161">En la consola de Configuration Manager, elija **Biblioteca de software**.</span><span class="sxs-lookup"><span data-stu-id="7892c-161">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="7892c-162">En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.</span><span class="sxs-lookup"><span data-stu-id="7892c-162">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="7892c-163">En la pestaña **Inicio**, en el grupo **Crear**, elija **Crear paquete**.</span><span class="sxs-lookup"><span data-stu-id="7892c-163">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>

4. <span data-ttu-id="7892c-164">En la página **Paquete** del **Asistente para crear paquetes y programas**, escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7892c-164">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    - <span data-ttu-id="7892c-165">Nombre: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="7892c-165">Name: `.NET Framework 4.5`</span></span>

    - <span data-ttu-id="7892c-166">Fabricante: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="7892c-166">Manufacturer: `Microsoft`</span></span>

    - <span data-ttu-id="7892c-167">Idioma.</span><span class="sxs-lookup"><span data-stu-id="7892c-167">Language.</span></span> `English (US)`

5. <span data-ttu-id="7892c-168">Elija **Este paquete contiene archivos de origen** y, después, **Examinar** para seleccionar la carpeta local o de red que contiene los archivos de instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7892c-168">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="7892c-169">Una vez seleccionada la carpeta, elija **Aceptar** y **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-169">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>

6. <span data-ttu-id="7892c-170">En la página **Tipo de programa** del asistente, elija **Programa estándar** y, después, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-170">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>

7. <span data-ttu-id="7892c-171">En la página **Programa** del **Asistente para crear paquetes y programas**, escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7892c-171">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    1. <span data-ttu-id="7892c-172">**Nombre:** `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="7892c-172">**Name:** `.NET Framework 4.5`</span></span>

    2. <span data-ttu-id="7892c-173">**Línea de comandos:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (las opciones de la línea de comandos se describen en la tabla que aparece después de estos pasos)</span><span class="sxs-lookup"><span data-stu-id="7892c-173">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>

    3. <span data-ttu-id="7892c-174">**Ejecutar:** elija **Oculto**.</span><span class="sxs-lookup"><span data-stu-id="7892c-174">**Run:** Choose **Hidden**.</span></span>

    4. <span data-ttu-id="7892c-175">**El programa se puede ejecutar:** elija la opción que especifica que el programa se puede ejecutar independientemente de si un usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="7892c-175">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>

8. <span data-ttu-id="7892c-176">En la página **Requisitos**, elija **Siguiente** para aceptar los valores predeterminados y, después, finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="7892c-176">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>

<span data-ttu-id="7892c-177">En la tabla siguiente se describen las opciones de la línea de comandos especificadas en el paso 7.</span><span class="sxs-lookup"><span data-stu-id="7892c-177">The following table describes the command-line options specified in step 7.</span></span>

|<span data-ttu-id="7892c-178">Opción</span><span class="sxs-lookup"><span data-stu-id="7892c-178">Option</span></span>|<span data-ttu-id="7892c-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="7892c-179">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="7892c-180">**/q**</span><span class="sxs-lookup"><span data-stu-id="7892c-180">**/q**</span></span>|<span data-ttu-id="7892c-181">Establece el modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="7892c-181">Sets quiet mode.</span></span> <span data-ttu-id="7892c-182">No se requiere proporcionar ningún dato y no se muestra ningún resultado.</span><span class="sxs-lookup"><span data-stu-id="7892c-182">No user input is required, and no output is shown.</span></span>|
|<span data-ttu-id="7892c-183">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="7892c-183">**/norestart**</span></span>|<span data-ttu-id="7892c-184">Evita que el programa de instalación se reinicie automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7892c-184">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="7892c-185">Si usa esta opción, Configuration Manager debe controlar el reinicio del equipo.</span><span class="sxs-lookup"><span data-stu-id="7892c-185">If you use this option, Configuration Manager must handle the computer restart.</span></span>|
|<span data-ttu-id="7892c-186">**/chainingpackage** *NombreDePaquete*</span><span class="sxs-lookup"><span data-stu-id="7892c-186">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="7892c-187">Especifica el nombre del paquete que realiza el encadenamiento.</span><span class="sxs-lookup"><span data-stu-id="7892c-187">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="7892c-188">Esta información se notifica con otra información de sesión de instalación para los usuarios que se hayan registrado en el Programa para la mejora de la experiencia del usuario (CEIP) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7892c-188">This information is reported with other installation session information for those who have signed up for the Microsoft Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="7892c-189">Si el nombre del paquete incluye espacios, use comillas dobles como delimitadores; por ejemplo: **/chainingpackage "Chaining Product"** .</span><span class="sxs-lookup"><span data-stu-id="7892c-189">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|

<span data-ttu-id="7892c-190">Mediante estos pasos se crea un paquete denominado .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7892c-190">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="7892c-191">El programa implementa una instalación silenciosa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7892c-191">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="7892c-192">En una instalación silenciosa, los usuarios no interactúan con el proceso de instalación y la aplicación de encadenamiento tiene que capturar el código devuelto y controlar el reinicio; vea [Getting Progress Information from an Installation Package (Obtener información de progreso de un paquete de instalación)](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7892c-192">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).</span></span>

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a><span data-ttu-id="7892c-193">Seleccionar un punto de distribución</span><span class="sxs-lookup"><span data-stu-id="7892c-193">Select a distribution point</span></span>

<span data-ttu-id="7892c-194">Para distribuir el paquete y el programa a los equipos cliente de un servidor, deberá designar primero un sistema de sitio como punto de distribución y después distribuir el paquete al punto de distribución.</span><span class="sxs-lookup"><span data-stu-id="7892c-194">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>

<span data-ttu-id="7892c-195">Realice los pasos siguientes para seleccionar un punto de distribución para el paquete de .NET Framework 4.5 que ha creado en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="7892c-195">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>

1. <span data-ttu-id="7892c-196">En la consola de Configuration Manager, elija **Biblioteca de software**.</span><span class="sxs-lookup"><span data-stu-id="7892c-196">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="7892c-197">En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.</span><span class="sxs-lookup"><span data-stu-id="7892c-197">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="7892c-198">En la lista de paquetes, seleccione el paquete **.NET Framework 4.5** que creó en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="7892c-198">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>

4. <span data-ttu-id="7892c-199">En la pestaña **Inicio**, en el grupo **Implementación**, elija **Distribuir contenido**.</span><span class="sxs-lookup"><span data-stu-id="7892c-199">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>

5. <span data-ttu-id="7892c-200">En la pestaña **General** del **Asistente para distribuir contenido**, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-200">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>

6. <span data-ttu-id="7892c-201">En la página **Destino del contenido** del asistente, elija **Agregar** y, después, **Punto de distribución**.</span><span class="sxs-lookup"><span data-stu-id="7892c-201">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>

7. <span data-ttu-id="7892c-202">En el cuadro de diálogo **Agregar puntos de distribución**, seleccione los puntos de distribución que hospedarán el paquete y el programa y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7892c-202">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>

8. <span data-ttu-id="7892c-203">Complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="7892c-203">Complete the wizard.</span></span>

<span data-ttu-id="7892c-204">Ahora el paquete contiene toda la información necesaria para realizar una implementación silenciosa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7892c-204">The package now contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="7892c-205">Antes de implementar el paquete y el programa, compruebe que se haya instalado en el punto de distribución; vea la sección de supervisión de contenido de [Supervisión del contenido que se ha distribuido con Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) en la biblioteca de documentación de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7892c-205">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Content status monitoring" section of [Monitor content you distribute with Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) in the Configuration Manager Documentation Library.</span></span>

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a><span data-ttu-id="7892c-206">Implementar el paquete</span><span class="sxs-lookup"><span data-stu-id="7892c-206">Deploy the package</span></span>

<span data-ttu-id="7892c-207">Para implementar el paquete y el programa de .NET Framework 4.5:</span><span class="sxs-lookup"><span data-stu-id="7892c-207">To deploy the .NET Framework 4.5 package and program:</span></span>

1. <span data-ttu-id="7892c-208">En la consola de Configuration Manager, elija **Biblioteca de software**.</span><span class="sxs-lookup"><span data-stu-id="7892c-208">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="7892c-209">En el área de trabajo **Biblioteca de software**, expanda **Administración de aplicaciones** y, luego, elija **Paquetes**.</span><span class="sxs-lookup"><span data-stu-id="7892c-209">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="7892c-210">En la lista de paquetes, seleccione el paquete que creó denominado **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="7892c-210">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>

4. <span data-ttu-id="7892c-211">En la pestaña **Inicio**, en el grupo **Implementación**, elija **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="7892c-211">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>

5. <span data-ttu-id="7892c-212">En la página **General** del **Asistente para implementar software**, elija **Examinar** y, a continuación, seleccione la colección que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7892c-212">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="7892c-213">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-213">Choose **Next**.</span></span>

6. <span data-ttu-id="7892c-214">En la página **Contenido** del asistente, compruebe que se muestra el punto desde el que desea distribuir el software y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-214">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>

7. <span data-ttu-id="7892c-215">En la página **Configuración de implementación** del asistente, confirme que la **Acción** está establecida en **Instalar** y el **Propósito** en **Requerido**.</span><span class="sxs-lookup"><span data-stu-id="7892c-215">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="7892c-216">Esto garantiza que el paquete de software sea una instalación obligatoria en los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="7892c-216">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="7892c-217">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-217">Choose **Next**.</span></span>

8. <span data-ttu-id="7892c-218">En la página **Programación** del asistente, especifique cuándo desea que se instale .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7892c-218">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="7892c-219">Puede elegir **Nuevo** para asignar un tiempo de instalación o bien indicar al software que realice la instalación cuando el usuario inicie o cierre sesión o lo antes posible.</span><span class="sxs-lookup"><span data-stu-id="7892c-219">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="7892c-220">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-220">Choose **Next**.</span></span>

9. <span data-ttu-id="7892c-221">En la página **Experiencia del usuario** del asistente, use los valores predeterminados y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-221">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7892c-222">El entorno de producción puede tener directivas que requieran selecciones distintas para la programación de distribución.</span><span class="sxs-lookup"><span data-stu-id="7892c-222">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="7892c-223">Para obtener información sobre estas opciones, vea [Advertisement Name Properties: Schedule Tab](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29) (Propiedades de nombre de anuncio: pestaña Programación).</span><span class="sxs-lookup"><span data-stu-id="7892c-223">For information about these options, see [Advertisement Name Properties: Schedule Tab](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29).</span></span>

10. <span data-ttu-id="7892c-224">En la página **Puntos de distribución** del asistente, use los valores predeterminados y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7892c-224">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>

11. <span data-ttu-id="7892c-225">Complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="7892c-225">Complete the wizard.</span></span> <span data-ttu-id="7892c-226">Puede supervisar el progreso de la implementación en el nodo **Implementaciones** del área de trabajo **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="7892c-226">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>

<span data-ttu-id="7892c-227">El paquete se implementará ahora en la colección de destino y se iniciará la instalación silenciosa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7892c-227">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="7892c-228">Para obtener información sobre los códigos de error de instalación de .NET Framework 4.5, vea la sección [Códigos devueltos](#return_codes) en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="7892c-228">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>

<a name="resources"></a>

## <a name="resources"></a><span data-ttu-id="7892c-229">Recursos</span><span class="sxs-lookup"><span data-stu-id="7892c-229">Resources</span></span>

<span data-ttu-id="7892c-230">Para obtener más información sobre la infraestructura para probar la implementación del paquete redistribuible de .NET Framework 4.5, consulte los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="7892c-230">For more information about the infrastructure for testing the deployment of the .NET Framework 4.5 redistributable package, see the following resources.</span></span>

<span data-ttu-id="7892c-231">**Active Directory, DNS, DHCP:**</span><span class="sxs-lookup"><span data-stu-id="7892c-231">**Active Directory, DNS, DHCP:**</span></span>

- [<span data-ttu-id="7892c-232">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="7892c-232">Active Directory Domain Services</span></span>](/windows/desktop/ad/active-directory-domain-services)

- [<span data-ttu-id="7892c-233">Sistema de nombres de dominio (DNS)</span><span class="sxs-lookup"><span data-stu-id="7892c-233">Domain Name System (DNS)</span></span>](/windows-server/networking/dns/dns-top)

- [<span data-ttu-id="7892c-234">Protocolo de configuración dinámica de host (DHCP)</span><span class="sxs-lookup"><span data-stu-id="7892c-234">Dynamic Host Configuration Protocol (DHCP)</span></span>](/windows-server/networking/technologies/dhcp/dhcp-top)

<span data-ttu-id="7892c-235">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="7892c-235">**SQL Server 2008:**</span></span>

- <span data-ttu-id="7892c-236">[Instalar SQL Server 2008 (vídeo de SQL Server)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="7892c-236">[Installing SQL Server 2008 (SQL Server Video)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span></span>

- [<span data-ttu-id="7892c-237">Información general sobre la seguridad de SQL Server 2008 para administradores de bases de datos</span><span class="sxs-lookup"><span data-stu-id="7892c-237">SQL Server 2008 Security Overview for Database Administrators</span></span>](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

<span data-ttu-id="7892c-238">**System Center 2012 Configuration Manager (punto de administración, punto de distribución):**</span><span class="sxs-lookup"><span data-stu-id="7892c-238">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>

- [<span data-ttu-id="7892c-239">Administración del sitio de System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7892c-239">Site Administration for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg681983%28v=technet.10%29)

- [<span data-ttu-id="7892c-240">Planeación e implementación de sitio único de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7892c-240">Configuration Manager Single Site Planning and Deployment</span></span>](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb680961%28v=technet.10%29)

<span data-ttu-id="7892c-241">**Cliente de System Center 2012 Configuration Manager para equipos Windows:**</span><span class="sxs-lookup"><span data-stu-id="7892c-241">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>

- [<span data-ttu-id="7892c-242">Implementación de clientes para System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7892c-242">Deploying Clients for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699391%28v=technet.10%29)

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="7892c-243">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="7892c-243">Troubleshooting</span></span>

### <a name="log-file-locations"></a><span data-ttu-id="7892c-244">Ubicaciones de archivos de registro</span><span class="sxs-lookup"><span data-stu-id="7892c-244">Log file locations</span></span>

<span data-ttu-id="7892c-245">Los siguientes archivos de registro se generan durante la configuración de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7892c-245">The following log files are generated during .NET Framework setup:</span></span>

- <span data-ttu-id="7892c-246">%temp%\Microsoft .NET Framework *versión*\*.txt</span><span class="sxs-lookup"><span data-stu-id="7892c-246">%temp%\Microsoft .NET Framework *version*\*.txt</span></span>
- <span data-ttu-id="7892c-247">%temp%\Microsoft .NET Framework *versión*\*.html</span><span class="sxs-lookup"><span data-stu-id="7892c-247">%temp%\Microsoft .NET Framework *version*\*.html</span></span>

<span data-ttu-id="7892c-248">donde *versión* es la versión de .NET Framework que va a instalar, como 4.5 o 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="7892c-248">where *version* is the version of the .NET Framework that you're installing, such as 4.5 or 4.7.2.</span></span>

<span data-ttu-id="7892c-249">También puede especificar el directorio en el que se escriben los archivos de registro mediante la opción de la línea de comandos `/log` en el comando de instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7892c-249">You can also specify the directory to which log files are written by using the `/log` command-line option in the .NET Framework installation command.</span></span> <span data-ttu-id="7892c-250">Para obtener más información, consulte la [Guía de implementación de .NET Framework para desarrolladores](deployment-guide-for-developers.md#command-line-options).</span><span class="sxs-lookup"><span data-stu-id="7892c-250">For more information, see [.NET Framework deployment guide for developers](deployment-guide-for-developers.md#command-line-options).</span></span>

<span data-ttu-id="7892c-251">Puede usar la [herramienta de recopilación de registros](https://www.microsoft.com/download/details.aspx?id=12493) para recopilar los archivos de registro de .NET Framework y crear un archivo .cab comprimido que reduzca el tamaño de los archivos.</span><span class="sxs-lookup"><span data-stu-id="7892c-251">You can use the [log collection tool](https://www.microsoft.com/download/details.aspx?id=12493) to collect the .NET Framework log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>

<a name="return_codes"></a>

### <a name="return-codes"></a><span data-ttu-id="7892c-252">Códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="7892c-252">Return codes</span></span>

<span data-ttu-id="7892c-253">En la siguiente tabla se muestra una lista de los códigos devueltos más habituales del programa de instalación redistribuible de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7892c-253">The following table lists the most common return codes from the .NET Framework 4.5 redistributable installation program.</span></span> <span data-ttu-id="7892c-254">Los códigos devueltos son los mismos para todas las versiones del instalador.</span><span class="sxs-lookup"><span data-stu-id="7892c-254">The return codes are the same for all versions of the installer.</span></span>

<span data-ttu-id="7892c-255">Para obtener vínculos a información detallada, vea la sección siguiente, [Descargar códigos de error](#additional_error_codes).</span><span class="sxs-lookup"><span data-stu-id="7892c-255">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>

|<span data-ttu-id="7892c-256">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="7892c-256">Return code</span></span>|<span data-ttu-id="7892c-257">Descripción</span><span class="sxs-lookup"><span data-stu-id="7892c-257">Description</span></span>|
|-----------------|-----------------|
|<span data-ttu-id="7892c-258">0</span><span class="sxs-lookup"><span data-stu-id="7892c-258">0</span></span>|<span data-ttu-id="7892c-259">La instalación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7892c-259">Installation completed successfully.</span></span>|
|<span data-ttu-id="7892c-260">1602</span><span class="sxs-lookup"><span data-stu-id="7892c-260">1602</span></span>|<span data-ttu-id="7892c-261">El usuario canceló la instalación.</span><span class="sxs-lookup"><span data-stu-id="7892c-261">The user canceled installation.</span></span>|
|<span data-ttu-id="7892c-262">1603</span><span class="sxs-lookup"><span data-stu-id="7892c-262">1603</span></span>|<span data-ttu-id="7892c-263">Error irrecuperable durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="7892c-263">A fatal error occurred during installation.</span></span>|
|<span data-ttu-id="7892c-264">1641</span><span class="sxs-lookup"><span data-stu-id="7892c-264">1641</span></span>|<span data-ttu-id="7892c-265">Para completar la instalación es necesario reiniciar.</span><span class="sxs-lookup"><span data-stu-id="7892c-265">A restart is required to complete the installation.</span></span> <span data-ttu-id="7892c-266">Este mensaje indica que la instalación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7892c-266">This message indicates success.</span></span>|
|<span data-ttu-id="7892c-267">3010</span><span class="sxs-lookup"><span data-stu-id="7892c-267">3010</span></span>|<span data-ttu-id="7892c-268">Para completar la instalación es necesario reiniciar.</span><span class="sxs-lookup"><span data-stu-id="7892c-268">A restart is required to complete the installation.</span></span> <span data-ttu-id="7892c-269">Este mensaje indica que la instalación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7892c-269">This message indicates success.</span></span>|
|<span data-ttu-id="7892c-270">5100</span><span class="sxs-lookup"><span data-stu-id="7892c-270">5100</span></span>|<span data-ttu-id="7892c-271">El equipo del usuario no cumple los requisitos del sistema.</span><span class="sxs-lookup"><span data-stu-id="7892c-271">The user's computer does not meet system requirements.</span></span>|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a><span data-ttu-id="7892c-272">Descargar códigos de error</span><span class="sxs-lookup"><span data-stu-id="7892c-272">Download error codes</span></span>

- [<span data-ttu-id="7892c-273">Códigos de error del Servicio de transferencia inteligente en segundo plano (BITS)</span><span class="sxs-lookup"><span data-stu-id="7892c-273">Background Intelligent Transfer Service (BITS) error codes</span></span>](/windows/desktop/Bits/bits-return-values)

- [<span data-ttu-id="7892c-274">Códigos de error del moniker de dirección URL</span><span class="sxs-lookup"><span data-stu-id="7892c-274">URL moniker error codes</span></span>](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145%28v=vs.85%29)

- [<span data-ttu-id="7892c-275">Códigos de error de WinHttp</span><span class="sxs-lookup"><span data-stu-id="7892c-275">WinHttp error codes</span></span>](/windows/desktop/WinHttp/error-messages)

<span data-ttu-id="7892c-276">Otros códigos de error:</span><span class="sxs-lookup"><span data-stu-id="7892c-276">Other error codes:</span></span>

- [<span data-ttu-id="7892c-277">Códigos de error de Windows Installer</span><span class="sxs-lookup"><span data-stu-id="7892c-277">Windows Installer error codes</span></span>](/windows/desktop/msi/error-codes)

- <span data-ttu-id="7892c-278">[Códigos de resultado del Agente de Windows Update](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="7892c-278">[Windows Update Agent result codes](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="7892c-279">Vea también</span><span class="sxs-lookup"><span data-stu-id="7892c-279">See also</span></span>

- [<span data-ttu-id="7892c-280">Guía de implementación para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="7892c-280">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)
- [<span data-ttu-id="7892c-281">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="7892c-281">System Requirements</span></span>](../get-started/system-requirements.md)
