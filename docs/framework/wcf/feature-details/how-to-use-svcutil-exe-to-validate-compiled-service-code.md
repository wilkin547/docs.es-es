---
title: 'Cómo: Utilizar Svcutil.exe para validar el código del servicio compilado'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 9e7bdf98f578e9b5f9ef2be9c46ccbe811358467
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490466"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="3e7e2-102">Cómo: Utilizar Svcutil.exe para validar el código del servicio compilado</span><span class="sxs-lookup"><span data-stu-id="3e7e2-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="3e7e2-103">Puede usar el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para detectar errores en las configuraciones y las implementaciones del servicio sin hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="3e7e2-104">Validar un servicio</span><span class="sxs-lookup"><span data-stu-id="3e7e2-104">To validate a service</span></span>  
  
1.  <span data-ttu-id="3e7e2-105">Compile su servicio en un archivo ejecutable y uno o más ensamblados dependientes.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2.  <span data-ttu-id="3e7e2-106">Abra un símbolo del sistema de SDK.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-106">Open an SDK command prompt</span></span>  
  
3.  <span data-ttu-id="3e7e2-107">En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="3e7e2-108">Para obtener más información sobre los distintos parámetros, consulte el Validationsection de servicio de la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tema.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="3e7e2-109">Debe utilizar la opción `/serviceName` para indicar el nombre de configuración del servicio que quiere validar.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="3e7e2-110">El argumento `assemblyPath` especifica la ruta de acceso al archivo ejecutable para el servicio y uno o más ensamblados que contienen los tipos de servicio que se validarán.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="3e7e2-111">El ensamblado ejecutable debe tener un archivo de configuración asociado para proporcionar la configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="3e7e2-112">Puede utilizar los caracteres comodín de la línea de comandos estándar para proporcionar varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e7e2-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e7e2-113">Example</span></span>  
 <span data-ttu-id="3e7e2-114">Lo siguiente controla el servicio myServiceName implementados en el archivo ejecutable myServiceHost.exe.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="3e7e2-115">Se carga el archivo de configuración para el servicio (myServiceHost.exe.config) automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e7e2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e7e2-116">See Also</span></span>  
 [<span data-ttu-id="3e7e2-117">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="3e7e2-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
