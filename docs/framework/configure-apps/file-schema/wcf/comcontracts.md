---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 404cc66ce423ba947c2817b56bebb4daf341ef0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176050"
---
# \<comContracts>

La sección de configuración `comContracts` contiene elementos que le permiten especificar varias propiedades de un contrato de servicios de la integración de COM+.  
  
## <a name="specifying-namespace-and-contract"></a>Especificar espacio de nombres y contrato  

 Los contratos de servicio de integración de COM+ están restringidos actualmente al `http://tempuri.org` espacio de nombres y el nombre del contrato se deriva de la interfaz com compatible. Puede, sin embargo, especificar alternativas mediante la sección `comContracts` en el archivo de configuración.  
  
 Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres y nombre del contrato del contrato de servicios, así como una opción para exigir el uso en enlaces con sesión.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.  
  
 Cuando esta sección está vacía, la inicialización del servicio aplica un espacio de nombres y un nombre de contrato predeterminados tomados del identificador de la interfaz COM de apoyo.  
  
 Además, puede utilizar el [\<exposedMethod>](exposedmethod.md) elemento para especificar los métodos com+ que se exponen cuando la interfaz en un componente com+ se expone como un servicio Web. También puede usar [\<persistableTypes>](persistabletypes.md) para especificar los tipos con persistencia que se usan en la integración de. Por último, puede usar el [\<userDefinedType>](userdefinedtype.md) elemento para incluir tipos definidos por el usuario (UDT) que se van a incluir en el contrato de servicio.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [Integración con aplicaciones COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedimiento para configurar los parámetros de los servicios COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
