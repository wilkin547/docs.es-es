---
title: Procedimiento para usar la herramienta configuración de modelos de servicio COM+
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: 2d21ec8ccf84a7c9af235af8e0afd444044cf81b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729392"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a><span data-ttu-id="f925a-102">Procedimiento para usar la herramienta configuración de modelos de servicio COM+</span><span class="sxs-lookup"><span data-stu-id="f925a-102">How to: Use the COM+ Service Model Configuration Tool</span></span>

<span data-ttu-id="f925a-103">Cuando ha seleccionado un modo de hospedaje adecuado, utilice la herramienta de línea de comandos de configuración de modelos de servicio COM+ (ComSvcConfig.exe) para configurar las interfaces de aplicaciones que se expondrán como servicios web.</span><span class="sxs-lookup"><span data-stu-id="f925a-103">Once you have selected an appropriate hosting mode, use the COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) to configure the application interfaces that will be exposed as Web services.</span></span>

> [!NOTE]
> <span data-ttu-id="f925a-104">Debe ser un administrador en el equipo para realizar cualquiera de las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="f925a-104">You must be an administrator on the machine to perform any of the following tasks.</span></span>

 <span data-ttu-id="f925a-105">Al usar ComSvcConfig.exe en un equipo con Windows 7 para configurar un servicio web con la finalidad de usar la última versión de modelo de servicio (actualmente, la versión 4.5), lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="f925a-105">When using ComSvcConfig.exe on a Windows 7 machine to configure a web service to use the latest service model version (currently v4.5), perform the following steps:</span></span>

1. <span data-ttu-id="f925a-106">Establezca la clave del registro  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` en un valor DWORD de 0x00000001</span><span class="sxs-lookup"><span data-stu-id="f925a-106">Set the registry key  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` to a DWORD value of 0x00000001</span></span>

2. <span data-ttu-id="f925a-107">Ejecute comsvcconfig.exe</span><span class="sxs-lookup"><span data-stu-id="f925a-107">Run comsvcconfig.exe</span></span>

3. <span data-ttu-id="f925a-108">Revierta la clave del Registro agregada en el paso 1 a su valor original, o elimínela si no existía.</span><span class="sxs-lookup"><span data-stu-id="f925a-108">Revert the registry key added in step 1 back to its original value, or delete it if did not exist.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f925a-109">Es importante revertir esta clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="f925a-109">Reverting this registry key is important.</span></span> <span data-ttu-id="f925a-110">Se trata de una clave de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="f925a-110">This is a compatibility key.</span></span> <span data-ttu-id="f925a-111">Si no se revierte este cambio, se pueden producir problemas con otras aplicaciones .NET activas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f925a-111">Not reverting this change may cause issues with other .NET applications running on the machine).</span></span>

> [!WARNING]
> <span data-ttu-id="f925a-112">Cuando se usa ComSvcConfig.exe/install en un equipo con Windows 8, se muestra un cuadro de diálogo que indica "una aplicación de su equipo necesita la siguiente característica de Windows: .NET Framework 3,5 (incluye .NET 2,0 y .NET 3,0" si .NET Framework 3,5 no está instalado.</span><span class="sxs-lookup"><span data-stu-id="f925a-112">When using ComSvcConfig.exe  /install on a Windows 8 machine, a dialog is displayed stating "An app on your PC needs the following Windows feature: .NET Framework 3.5 (includes .NET 2.0 and .NET 3.0" if .NET Framework 3.5 is not installed.</span></span> <span data-ttu-id="f925a-113">Se puede omitir este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f925a-113">This dialog may be ignored.</span></span> <span data-ttu-id="f925a-114">También puede establecer la clave del Registro OnlyUseLatestCLR a un valor DWORD de 0x00000001</span><span class="sxs-lookup"><span data-stu-id="f925a-114">Alternatively you can sed the OnlyUseLatestCLR registry key to a DWORD value of 0x00000001</span></span>

## <a name="add-an-interface-using-the-com-hosting-mode"></a><span data-ttu-id="f925a-115">Agregar una interfaz mediante el modo de hospedaje de COM+</span><span class="sxs-lookup"><span data-stu-id="f925a-115">Add an interface using the COM+ hosting mode</span></span>

- <span data-ttu-id="f925a-116">Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f925a-116">Run ComSvcConfig using the `/install` and `/hosting:complus` options, as shown in the following example.</span></span>

    ```console
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose
    ```

     <span data-ttu-id="f925a-117">El comando agrega la interfaz `IFinances` del componente (de la aplicación OnlineStore COM+) `ItemOrders.IFinancial` al conjunto de interfaces que se expondrán como servicios web.</span><span class="sxs-lookup"><span data-stu-id="f925a-117">The command adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="f925a-118">El servicio utiliza el modo de hospedaje de COM+ y por consiguiente requiere la activación explícita de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f925a-118">The service uses the COM+ hosting mode and therefore requires explicit application activation.</span></span>

     <span data-ttu-id="f925a-119">Aunque el carácter comodín ( \* ) se puede usar para el componente y la interfaz, evite usarlo porque es posible que desee exponer solo la funcionalidad seleccionada como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="f925a-119">While the wildcard asterisk (\*) character can be used for the component and the interface, avoid using it because you might want to expose only selected functionality as a Web service.</span></span> <span data-ttu-id="f925a-120">Si se ejecuta con una versión futura de este componente, al utilizar el carácter comodín se pueden exponer involuntariamente interfaces que pueden no haber estado presentes cuando se determinó la sintaxis de configuración.</span><span class="sxs-lookup"><span data-stu-id="f925a-120">If run with a future version of this component, using the wildcard may unintentionally expose interfaces that may not have been present when the configuration syntax was determined.</span></span>

     <span data-ttu-id="f925a-121">La opción /verbose indica a la herramienta que muestre las advertencias además de cualquier error.</span><span class="sxs-lookup"><span data-stu-id="f925a-121">The /verbose option instructs the tool to display warnings in addition to any errors.</span></span>

     <span data-ttu-id="f925a-122">El contrato para el servicio expuesto contendrá todos los métodos de la interfaz `IFinances`.</span><span class="sxs-lookup"><span data-stu-id="f925a-122">The contract for the exposed service will contain all of the methods from the `IFinances` interface.</span></span>

## <a name="add-specific-methods-from-an-interface-using-the-com-hosting-mode"></a><span data-ttu-id="f925a-123">Agregar métodos específicos desde una interfaz mediante el modo de hospedaje de COM+</span><span class="sxs-lookup"><span data-stu-id="f925a-123">Add specific methods from an interface using the COM+ hosting mode</span></span>

- <span data-ttu-id="f925a-124">Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus` con denominación explícita de los métodos necesarios, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f925a-124">Run ComSvcConfig using the `/install` and `/hosting:complus` options with explicit naming of the required methods, as shown in the following example.</span></span>

    ```console
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose
    ```

     <span data-ttu-id="f925a-125">El comando agrega solo los métodos `Credit` y `Debit` de la interfaz `IFinances` como operaciones al contrato de servicios expuesto.</span><span class="sxs-lookup"><span data-stu-id="f925a-125">The command adds only the `Credit` and `Debit` methods from the `IFinances` interface as operations to the exposed service contract.</span></span> <span data-ttu-id="f925a-126">Todos los otros métodos en la interfaz se omitirán del contrato y no podrán ser llamados por los clientes de servicios web.</span><span class="sxs-lookup"><span data-stu-id="f925a-126">All other methods on the interface will be omitted from the contract and will not be callable from Web service clients.</span></span>

## <a name="add-an-interface-using-the-web-hosting-mode"></a><span data-ttu-id="f925a-127">Agregar una interfaz mediante el modo de hospedaje Web</span><span class="sxs-lookup"><span data-stu-id="f925a-127">Add an interface using the Web hosting mode</span></span>

- <span data-ttu-id="f925a-128">Ejecute ComSvcConfig utilizando la opción `/install` y la opción `/hosting:was`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f925a-128">Run ComSvcConfig using the `/install` option and the `/hosting:was` option, as shown in the following example.</span></span>

    ```console
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose
    ```

     <span data-ttu-id="f925a-129">El comando agrega la interfaz `IStockLevels` en el componente `ItemInventory.Warehouse` (de la aplicación OnlineWarehouse COM+) al conjunto de interfaces que se expondrán como servicios web.</span><span class="sxs-lookup"><span data-stu-id="f925a-129">The command adds the `IStockLevels` interface on the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="f925a-130">El servicio está hospedado en Web en el directorio virtual de OnlineWarehouse de IIS en lugar de en COM+ y así la aplicación se activa automáticamente como se requiere.</span><span class="sxs-lookup"><span data-stu-id="f925a-130">The service is Web hosted in the OnlineWarehouse virtual directory of IIS rather than in COM+, and thus the application is automatically activated as required.</span></span>

     <span data-ttu-id="f925a-131">Para utilizar la configuración en proceso hospedada en Web, la aplicación COM+ se debe configurar para ejecutarse como una aplicación de biblioteca en lugar de una aplicación de servidor utilizando la consola de administración de Servicios de componentes.</span><span class="sxs-lookup"><span data-stu-id="f925a-131">To use the Web-hosted in-process configuration, the COM+ application must be configured to run as a Library application rather than a Server application using the Component Services administration console.</span></span> <span data-ttu-id="f925a-132">Las aplicaciones configuradas como aplicaciones de servidor utilizan el modo hospedado por Web estándar e incurren un salto de proceso para procesar cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="f925a-132">Applications configured as Server applications use the standard Web-hosted mode and incur a process hop to process each request.</span></span>

     <span data-ttu-id="f925a-133">La opción `/mex` agrega un extremo de servicio adicional de Intercambio de metadatos (MEX) que utiliza el mismo transporte que el extremo de servicio de la aplicación para admitir clientes que desean recuperar una definición del contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="f925a-133">The `/mex` option adds an additional Metadata Exchange (MEX) service endpoint that uses the same transport as the application's service endpoint to support clients that want to retrieve a contract definition from the service.</span></span>

## <a name="remove-a-web-service-for-a-specified-interface"></a><span data-ttu-id="f925a-134">Quitar un servicio web para una interfaz especificada</span><span class="sxs-lookup"><span data-stu-id="f925a-134">Remove a Web service for a specified interface</span></span>

- <span data-ttu-id="f925a-135">Ejecute ComSvcConfig utilizando la opción `/uninstall`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f925a-135">Run ComSvcConfig using the `/uninstall` option, as shown in the following example.</span></span>

    ```console
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus
    ```

     <span data-ttu-id="f925a-136">El comando quita la interfaz `IFinances` del componente (de la aplicación OnlineStore COM+) `ItemOrders.Financial`.</span><span class="sxs-lookup"><span data-stu-id="f925a-136">The command removes the `IFinances` interface on the `ItemOrders.Financial` component (from the OnlineStore COM+ application).</span></span>

## <a name="list-currently-exposed-interfaces"></a><span data-ttu-id="f925a-137">Enumerar las interfaces actualmente expuestas</span><span class="sxs-lookup"><span data-stu-id="f925a-137">List currently exposed interfaces</span></span>

- <span data-ttu-id="f925a-138">Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f925a-138">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>

    ```console
    ComSvcConfig.exe /list
    ```

     <span data-ttu-id="f925a-139">El comando hace una lista de las interfaces actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, y se pone a disposición del equipo local.</span><span class="sxs-lookup"><span data-stu-id="f925a-139">The command lists the currently exposed interfaces, along with the corresponding address and binding details, scoped to the local machine.</span></span>

## <a name="list-specific-currently-exposed-interfaces"></a><span data-ttu-id="f925a-140">Enumerar interfaces específicas actualmente expuestas</span><span class="sxs-lookup"><span data-stu-id="f925a-140">List specific currently exposed interfaces</span></span>

- <span data-ttu-id="f925a-141">Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f925a-141">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>

    ```console
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus
    ```

     <span data-ttu-id="f925a-142">El comando hace una lista de las interfaces hospedadas por COM+ actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, para la aplicación OnlineStore COM+ en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f925a-142">The command lists currently exposed COM+-hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>

## <a name="display-help-for-options"></a><span data-ttu-id="f925a-143">Mostrar ayuda para opciones</span><span class="sxs-lookup"><span data-stu-id="f925a-143">Display help for options</span></span>

- <span data-ttu-id="f925a-144">Ejecutar ComSvcConfig utilizando la opción /?</span><span class="sxs-lookup"><span data-stu-id="f925a-144">Run ComSvcConfig using the /?</span></span> <span data-ttu-id="f925a-145">, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f925a-145">option, as shown in the following example.</span></span>

    ```console
    ComSvcConfig.exe /?
    ```

## <a name="see-also"></a><span data-ttu-id="f925a-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f925a-146">See also</span></span>

- [<span data-ttu-id="f925a-147">Información general de la integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="f925a-147">Integrating with COM+ Applications Overview</span></span>](integrating-with-com-plus-applications-overview.md)
