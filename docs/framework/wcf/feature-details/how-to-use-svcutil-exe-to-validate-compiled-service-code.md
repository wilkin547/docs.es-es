---
title: Procedimiento para usar Svcutil.exe para validar el código del servicio compilado
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 21cd0c13cea764efb60b7b94b699e9a483269da8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280668"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Procedimiento para usar Svcutil.exe para validar el código del servicio compilado

Puede usar la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para detectar errores en las implementaciones de servicio y las configuraciones sin hospedar el servicio.  
  
### <a name="to-validate-a-service"></a>Validar un servicio  
  
1. Compile su servicio en un archivo ejecutable y uno o más ensamblados dependientes.  
  
2. Abra un símbolo del sistema de SDK.  
  
3. En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente. Para obtener más información sobre los distintos parámetros, vea el Validationsection de servicio del tema [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Debe utilizar la opción `/serviceName` para indicar el nombre de configuración del servicio que quiere validar.  
  
     El argumento `assemblyPath` especifica la ruta de acceso al archivo ejecutable para el servicio y uno o más ensamblados que contienen los tipos de servicio que se validarán. El ensamblado ejecutable debe tener un archivo de configuración asociado para proporcionar la configuración de servicio. Puede utilizar los caracteres comodín de la línea de comandos estándar para proporcionar varios ensamblados.  
  
## <a name="example"></a>Ejemplo  

 Lo siguiente controla el servicio myServiceName implementados en el archivo ejecutable myServiceHost.exe.  Se carga el archivo de configuración para el servicio (myServiceHost.exe.config) automáticamente.  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
