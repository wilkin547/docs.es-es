---
title: "Cómo: Utilizar Svcutil.exe para validar el código del servicio compilado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9aeeccc42d5fbbed34ffedf01712b208c98ec58e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="47d7f-102">Cómo: Utilizar Svcutil.exe para validar el código del servicio compilado</span><span class="sxs-lookup"><span data-stu-id="47d7f-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="47d7f-103">Puede usar el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para detectar errores en las configuraciones y las implementaciones del servicio sin hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="47d7f-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="47d7f-104">Validar un servicio</span><span class="sxs-lookup"><span data-stu-id="47d7f-104">To validate a service</span></span>  
  
1.  <span data-ttu-id="47d7f-105">Compile su servicio en un archivo ejecutable y uno o más ensamblados dependientes.</span><span class="sxs-lookup"><span data-stu-id="47d7f-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2.  <span data-ttu-id="47d7f-106">Abra un símbolo del sistema de SDK.</span><span class="sxs-lookup"><span data-stu-id="47d7f-106">Open an SDK command prompt</span></span>  
  
3.  <span data-ttu-id="47d7f-107">En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente.</span><span class="sxs-lookup"><span data-stu-id="47d7f-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="47d7f-108">Para obtener más información sobre los distintos parámetros, consulte el Validationsection de servicio de la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tema.</span><span class="sxs-lookup"><span data-stu-id="47d7f-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="47d7f-109">Debe utilizar la opción `/serviceName` para indicar el nombre de configuración del servicio que quiere validar.</span><span class="sxs-lookup"><span data-stu-id="47d7f-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="47d7f-110">El argumento `assemblyPath` especifica la ruta de acceso al archivo ejecutable para el servicio y uno o más ensamblados que contienen los tipos de servicio que se validarán.</span><span class="sxs-lookup"><span data-stu-id="47d7f-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="47d7f-111">El ensamblado ejecutable debe tener un archivo de configuración asociado para proporcionar la configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="47d7f-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="47d7f-112">Puede utilizar los caracteres comodín de la línea de comandos estándar para proporcionar varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="47d7f-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47d7f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47d7f-113">Example</span></span>  
 <span data-ttu-id="47d7f-114">Lo siguiente controla el servicio myServiceName implementados en el archivo ejecutable myServiceHost.exe.</span><span class="sxs-lookup"><span data-stu-id="47d7f-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="47d7f-115">Se carga el archivo de configuración para el servicio (myServiceHost.exe.config) automáticamente.</span><span class="sxs-lookup"><span data-stu-id="47d7f-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="47d7f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="47d7f-116">See Also</span></span>  
 [<span data-ttu-id="47d7f-117">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="47d7f-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
