---
title: "Herramienta de configuración del modelo de servicio COM+ (ComSvcConfig.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3f812beea611633fe1fa47ced5db46c462443f28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a><span data-ttu-id="e5360-102">Herramienta de configuración del modelo de servicio COM+ (ComSvcConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="e5360-102">COM+ Service Model Configuration Tool (ComSvcConfig.exe)</span></span>
<span data-ttu-id="e5360-103">La herramienta de línea de comandos de configuración del modelo de servicios COM+ (ComSvcConfig.exe) le permite configurar interfaces de COM+ que se van a exponer como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="e5360-103">The COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) enables you to configure COM+ interfaces to be exposed as Web services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5360-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5360-104">Syntax</span></span>  
  
```  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a><span data-ttu-id="e5360-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5360-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5360-106">Debe ser un administrador en el equipo local para utilizar ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="e5360-106">You must be an administrator on the local computer to use ComSvcConfig.exe.</span></span>  
  
 <span data-ttu-id="e5360-107">La herramienta se puede encontrar en la ubicación siguiente</span><span class="sxs-lookup"><span data-stu-id="e5360-107">The tool can be found in the following location</span></span>  
  
 <span data-ttu-id="e5360-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="e5360-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
 <span data-ttu-id="e5360-109">Para obtener más información acerca de ComSvcConfig.exe, consulte [Cómo: usar la herramienta COM + Service Model Configuration](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e5360-109">For more information about ComSvcConfig.exe, see [How to: Use the COM+ Service Model Configuration Tool](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span></span>  
  
 <span data-ttu-id="e5360-110">La tabla siguiente describe los modos que se pueden utilizar con ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="e5360-110">The following table describes the modes that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="e5360-111">Opción</span><span class="sxs-lookup"><span data-stu-id="e5360-111">Option</span></span>|<span data-ttu-id="e5360-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5360-112">Description</span></span>|  
|------------|-----------------|  
|`install`|<span data-ttu-id="e5360-113">Instala una configuración para una interfaz de COM+ para la integración del modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="e5360-113">Installs a configuration for a COM+ interface for Service Model integration.</span></span><br /><br /> <span data-ttu-id="e5360-114">Forma abreviada: `/i`</span><span class="sxs-lookup"><span data-stu-id="e5360-114">Short form `/i`.</span></span>|  
|`uninstall`|<span data-ttu-id="e5360-115">Desinstala una configuración para una interfaz de COM+ de la integración del modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="e5360-115">Uninstalls a configuration for a COM+ interface from Service Model integration.</span></span><br /><br /> <span data-ttu-id="e5360-116">Forma abreviada: `/u`</span><span class="sxs-lookup"><span data-stu-id="e5360-116">Short form `/u`.</span></span>|  
|`list`|<span data-ttu-id="e5360-117">Hace una lista de información sobre las aplicaciones y componentes COM+ que tienen interfaces configuradas para la integración del modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="e5360-117">Lists information about COM+ applications and components that have interfaces that are configured for Service Model integration.</span></span><br /><br /> <span data-ttu-id="e5360-118">Forma abreviada: `/l`</span><span class="sxs-lookup"><span data-stu-id="e5360-118">Short form `/l`.</span></span>|  
  
 <span data-ttu-id="e5360-119">La tabla siguiente describe los marcadores que se pueden utilizar con ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="e5360-119">The following table describes the flags that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="e5360-120">Opción</span><span class="sxs-lookup"><span data-stu-id="e5360-120">Option</span></span>|<span data-ttu-id="e5360-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5360-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e5360-122">`/application:`\< *ApplicationID* &#124; *ApplicationName*\></span><span class="sxs-lookup"><span data-stu-id="e5360-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span></span>|<span data-ttu-id="e5360-123">Especifica la aplicación COM+ que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="e5360-123">Specifies the COM+ application to configure.</span></span><br /><br /> <span data-ttu-id="e5360-124">Forma abreviada: `/a`</span><span class="sxs-lookup"><span data-stu-id="e5360-124">Short form `/a`.</span></span>|  
|<span data-ttu-id="e5360-125">`/contract:`\< *ClassID* &#124; *ProgID* &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124;\*\></span><span class="sxs-lookup"><span data-stu-id="e5360-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span></span>|<span data-ttu-id="e5360-126">Especifica el componente y la interfaz COM+ que se configurarán como contrato para el servicio.</span><span class="sxs-lookup"><span data-stu-id="e5360-126">Specifies the COM+ component and interface that will be configured as the contract for the service.</span></span><br /><br /> <span data-ttu-id="e5360-127">Forma abreviada: `/c`</span><span class="sxs-lookup"><span data-stu-id="e5360-127">Short form `/c`.</span></span><br /><br /> <span data-ttu-id="e5360-128">Mientras que el carácter comodín (\*) puede utilizarse al especificar los nombres de componente y la interfaz, se recomienda que no se utilicen, porque podría exponer interfaces que no se pretendía.</span><span class="sxs-lookup"><span data-stu-id="e5360-128">While the wildcard character (\*) can be used when you specify the component and interface names, we recommend that you do not use it, because you might expose interfaces that you did not intend to.</span></span>|  
|<span data-ttu-id="e5360-129">`/hosting:`\< *complus* &#124; *era*\></span><span class="sxs-lookup"><span data-stu-id="e5360-129">`/hosting:` \<*complus*  &#124; *was*\></span></span>|<span data-ttu-id="e5360-130">Especifica si utilizar el modo de alojamiento COM+ o el modo del alojamiento Web.</span><span class="sxs-lookup"><span data-stu-id="e5360-130">Specifies whether to use the COM+ hosting mode or the Web hosting mode.</span></span><br /><br /> <span data-ttu-id="e5360-131">Forma abreviada: `/h`</span><span class="sxs-lookup"><span data-stu-id="e5360-131">Short form `/h`.</span></span><br /><br /> <span data-ttu-id="e5360-132">Para utilizar el modo del alojamiento de COM+ se requiere activación explícita de la aplicación COM+.</span><span class="sxs-lookup"><span data-stu-id="e5360-132">Using the COM+ hosting mode requires explicit activation of the COM+ application.</span></span> <span data-ttu-id="e5360-133">Utilizar el modo del alojamiento Web permite activar la aplicación COM+ automáticamente tal y como se requiere.</span><span class="sxs-lookup"><span data-stu-id="e5360-133">Using the Web hosting mode allows the COM+ application to be automatically activated as required.</span></span> <span data-ttu-id="e5360-134">Si la aplicación COM+ es una aplicación de biblioteca, se ejecuta en el proceso de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e5360-134">If the COM+ application is a library application, it runs in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="e5360-135">Si la aplicación COM+ es una aplicación de servidor, se ejecuta en el proceso de Dllhost.exe.</span><span class="sxs-lookup"><span data-stu-id="e5360-135">If the COM+ application is a server application, it runs in the Dllhost.exe process.</span></span>|  
|<span data-ttu-id="e5360-136">`/webSite:`\< *WebsiteName*\></span><span class="sxs-lookup"><span data-stu-id="e5360-136">`/webSite:` \<*WebsiteName*\></span></span>|<span data-ttu-id="e5360-137">Especifica el sitio web para alojamiento cuando se utiliza el modo de alojamiento Web (vea el marcador `/hosting`).</span><span class="sxs-lookup"><span data-stu-id="e5360-137">Specifies the Web site for hosting when Web hosting mode is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="e5360-138">Forma abreviada: `/w`</span><span class="sxs-lookup"><span data-stu-id="e5360-138">Short form `/w`.</span></span><br /><br /> <span data-ttu-id="e5360-139">Si no se especifica ningún sitio web, se utiliza el sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e5360-139">If no Web site is specified, the default Web site is used.</span></span>|  
|<span data-ttu-id="e5360-140">`/webDirectory:`\< *WebDirectoryName*\></span><span class="sxs-lookup"><span data-stu-id="e5360-140">`/webDirectory:` \<*WebDirectoryName*\></span></span>|<span data-ttu-id="e5360-141">Especifica el directorio virtual para alojamiento cuando se utiliza el alojamiento Web (vea el marcador `/hosting`).</span><span class="sxs-lookup"><span data-stu-id="e5360-141">Specifies the virtual directory for hosting when Web hosting is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="e5360-142">Forma abreviada: `/d`</span><span class="sxs-lookup"><span data-stu-id="e5360-142">Short form `/d`.</span></span>|  
|`/mex`|<span data-ttu-id="e5360-143">Agrega un punto de conexión de servicio de intercambio de metadatos (MEX) a la configuración de servicio predeterminada para admitir clientes que desean recuperar del servicio una definición del contrato.</span><span class="sxs-lookup"><span data-stu-id="e5360-143">Adds a Metadata Exchange (MEX) service endpoint to the default service configuration to support clients that want to retrieve a contract definition from the service.</span></span><br /><br /> <span data-ttu-id="e5360-144">Forma abreviada: `/x`</span><span class="sxs-lookup"><span data-stu-id="e5360-144">Short form `/x`.</span></span>|  
|`/id`|<span data-ttu-id="e5360-145">Muestra la información de aplicación, componente e interfaz como id.</span><span class="sxs-lookup"><span data-stu-id="e5360-145">Displays the application, component, and interface information as IDs.</span></span><br /><br /> <span data-ttu-id="e5360-146">Forma abreviada: `/k`</span><span class="sxs-lookup"><span data-stu-id="e5360-146">Short form `/k`.</span></span>|  
|`/nologo`|<span data-ttu-id="e5360-147">Evita que ComSvcConfig.exe muestre su logotipo.</span><span class="sxs-lookup"><span data-stu-id="e5360-147">Prevents ComSvcConfig.exe from displaying its logo.</span></span><br /><br /> <span data-ttu-id="e5360-148">Forma abreviada: `/n`</span><span class="sxs-lookup"><span data-stu-id="e5360-148">Short form `/n`.</span></span>|  
|`/verbose`|<span data-ttu-id="e5360-149">Genera todas las advertencias o el texto informativo además de los errores encontrados.</span><span class="sxs-lookup"><span data-stu-id="e5360-149">Outputs all warnings or informational text in addition to any errors encountered.</span></span><br /><br /> <span data-ttu-id="e5360-150">Forma abreviada: `/v`</span><span class="sxs-lookup"><span data-stu-id="e5360-150">Short form `/v`.</span></span>|  
|`/help`|<span data-ttu-id="e5360-151">Muestra el mensaje de uso.</span><span class="sxs-lookup"><span data-stu-id="e5360-151">Displays the usage message.</span></span><br /><br /> <span data-ttu-id="e5360-152">Forma abreviada: `/?`</span><span class="sxs-lookup"><span data-stu-id="e5360-152">Short form `/?`.</span></span>|  
|`/partial`|<span data-ttu-id="e5360-153">Genera una configuración de servicio cuando la interfaz especificada incluye una o más firmas de método que se pueden exponer.</span><span class="sxs-lookup"><span data-stu-id="e5360-153">Generates a service configuration when the specified interface includes one or more method signatures that can be exposed.</span></span> <span data-ttu-id="e5360-154">En el momento de inicialización del servicio, aparecen métodos compatibles como operaciones en el contrato de servicios y los métodos no compatibles se omiten y no están presentes en el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="e5360-154">At service initialization time, compatible methods appear as operations on the service contract, and non-compatible methods are ignored and absent from the service contract.</span></span><br /><br /> <span data-ttu-id="e5360-155">Si falta este marcador, la herramienta no generará una configuración de servicio cuando la interfaz especificada incluye uno o más métodos incompatibles.</span><span class="sxs-lookup"><span data-stu-id="e5360-155">If this flag is missing, the tool will not generate a service configuration when the specified interface includes one or more incompatible methods.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="e5360-156">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e5360-156">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="e5360-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5360-157">Description</span></span>  
 <span data-ttu-id="e5360-158">El ejemplo siguiente agrega la interfaz `IFinances` del componente `ItemOrders.IFinancial` (de la aplicación COM+ de OnlineStore) al conjunto de interfaces que se exponen como servicios web utilizando el modo del alojamiento COM+.</span><span class="sxs-lookup"><span data-stu-id="e5360-158">The following example adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that are exposed as Web services, using the COM+ hosting mode.</span></span> <span data-ttu-id="e5360-159">Se generarán todas las advertencias además de cualquier error encontrado.</span><span class="sxs-lookup"><span data-stu-id="e5360-159">All warnings will be output in addition to any errors encountered.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e5360-160">Código</span><span class="sxs-lookup"><span data-stu-id="e5360-160">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a><span data-ttu-id="e5360-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5360-161">Description</span></span>  
 <span data-ttu-id="e5360-162">El ejemplo siguiente agrega la interfaz `IStockLevels` del componente `ItemInventory.Warehouse` (de la aplicación COM+ de OnlineWarehouse) al conjunto de interfaces que se exponen como servicios web utilizando el modo de alojamiento Web.</span><span class="sxs-lookup"><span data-stu-id="e5360-162">The following example adds the `IStockLevels` interface of the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that are exposed as Web services, using the Web hosting mode.</span></span> <span data-ttu-id="e5360-163">El servicio Web está alojado en Web en el directorio virtual de OnlineWarehouse de IIS.</span><span class="sxs-lookup"><span data-stu-id="e5360-163">The Web service is Web hosted in the OnlineWarehouse virtual directory of IIS.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e5360-164">Código</span><span class="sxs-lookup"><span data-stu-id="e5360-164">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a><span data-ttu-id="e5360-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5360-165">Description</span></span>  
 <span data-ttu-id="e5360-166">El ejemplo siguiente quita la interfaz `IFinances` del componente `ItemOrders.Financial` (de la aplicación COM+ de OnlineStore) del conjunto de interfaces que se exponen como servicios web utilizando el modo del alojamiento COM+.</span><span class="sxs-lookup"><span data-stu-id="e5360-166">The following example removes the `IFinances` interface of the `ItemOrders.Financial` component (from the OnlineStore COM+ application) from the set of interfaces that are exposed as Web services.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e5360-167">Código</span><span class="sxs-lookup"><span data-stu-id="e5360-167">Code</span></span>  
  
```  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a><span data-ttu-id="e5360-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5360-168">Description</span></span>  
 <span data-ttu-id="e5360-169">El ejemplo siguiente enumera las interfaces hospedadas en COM+ expuestas actualmente, junto con la dirección correspondiente y los detalles del enlace, para la aplicación OnlineStore COM+ en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="e5360-169">The following example lists currently exposed COM+ hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e5360-170">Código</span><span class="sxs-lookup"><span data-stu-id="e5360-170">Code</span></span>  
  
```  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5360-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5360-171">See Also</span></span>  
 [<span data-ttu-id="e5360-172">Cómo: utilizar la herramienta de configuración del modelo de servicio COM +</span><span class="sxs-lookup"><span data-stu-id="e5360-172">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
