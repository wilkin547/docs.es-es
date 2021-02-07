---
description: 'Más información acerca de cómo: usar Svcutil.exe para validar el código de servicio compilado'
title: Procedimiento para usar Svcutil.exe para validar el código del servicio compilado
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: b68cdeb61ac1f42cacdcf7d1468623acb8542abe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734170"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="57146-103">Procedimiento para usar Svcutil.exe para validar el código del servicio compilado</span><span class="sxs-lookup"><span data-stu-id="57146-103">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>

<span data-ttu-id="57146-104">Puede usar la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para detectar errores en las implementaciones de servicio y las configuraciones sin hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="57146-104">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="57146-105">Validar un servicio</span><span class="sxs-lookup"><span data-stu-id="57146-105">To validate a service</span></span>  
  
1. <span data-ttu-id="57146-106">Compile su servicio en un archivo ejecutable y uno o más ensamblados dependientes.</span><span class="sxs-lookup"><span data-stu-id="57146-106">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="57146-107">Abra un símbolo del sistema de SDK.</span><span class="sxs-lookup"><span data-stu-id="57146-107">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="57146-108">En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente.</span><span class="sxs-lookup"><span data-stu-id="57146-108">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="57146-109">Para obtener más información sobre los distintos parámetros, vea el Validationsection de servicio del tema [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="57146-109">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="57146-110">Debe utilizar la opción `/serviceName` para indicar el nombre de configuración del servicio que quiere validar.</span><span class="sxs-lookup"><span data-stu-id="57146-110">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="57146-111">El argumento `assemblyPath` especifica la ruta de acceso al archivo ejecutable para el servicio y uno o más ensamblados que contienen los tipos de servicio que se validarán.</span><span class="sxs-lookup"><span data-stu-id="57146-111">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="57146-112">El ensamblado ejecutable debe tener un archivo de configuración asociado para proporcionar la configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="57146-112">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="57146-113">Puede utilizar los caracteres comodín de la línea de comandos estándar para proporcionar varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="57146-113">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57146-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57146-114">Example</span></span>  

 <span data-ttu-id="57146-115">Lo siguiente controla el servicio myServiceName implementados en el archivo ejecutable myServiceHost.exe.</span><span class="sxs-lookup"><span data-stu-id="57146-115">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="57146-116">Se carga el archivo de configuración para el servicio (myServiceHost.exe.config) automáticamente.</span><span class="sxs-lookup"><span data-stu-id="57146-116">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="57146-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="57146-117">See also</span></span>

- [<span data-ttu-id="57146-118">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="57146-118">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
