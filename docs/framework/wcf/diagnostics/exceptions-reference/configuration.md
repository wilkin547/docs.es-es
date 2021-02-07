---
description: 'Más información acerca de: configuración'
title: Configuración
ms.date: 03/30/2017
ms.assetid: 86a6e12f-73b5-450e-8725-f4ca5fe0702c
ms.openlocfilehash: a0eaafc9f2b33441e80a35d103f6e13bd562dd70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759788"
---
# <a name="configuration"></a>Configuración

En este tema se enumeran todas las excepciones generadas por la configuración de Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|ConfigBindingCannotBeConfigured|No se puede configurar el enlace en el punto de conexión de servicio.|  
|ConfigElementKeyNull|La clave de elemento de configuración concreta no puede ser NULL.|  
|ConfigExtensionTypeNotRegisteredInCollection|El tipo de extensión concreto no está registrado en la colección de extensión concreta.|  
|ConfigIndexOutOfRange|El valor para el atributo concreto está fuera del intervalo.|  
|ConfigInvalidBindingConfigurationName|La configuración concreta no tiene un enlace con el nombre específico.|  
|ConfigInvalidBindingName|La configuración concreta no tiene un enlace con el nombre específico. Éste es un valor no válido para el enlace.|  
|ConfigInvalidCommonEndpointBehaviorType|No pueda agregar la extensión de comportamiento concreta al comportamiento del extremo común porque no implementa el tipo específico.|  
|ConfigInvalidCommonServiceBehaviorType|No pueda agregar la extensión de comportamiento concreta al comportamiento del servicio común porque no implementa el tipo específico.|  
|ConfigInvalidEndpointBehaviorType|No pueda agregar la extensión de comportamiento concreta al comportamiento del punto de conexión concreto porque el tipo de comportamiento subyacente no implementa la interfaz IServiceBehavior.|  
|ConfigInvalidExtensionType|El tipo específico debe derivar de la extensión concreta para que se utilice en la colección.|  
|ConfigInvalidServiceBehaviorType|No pueda agregar la extensión de comportamiento al comportamiento de servicio con el nombre específico porque el tipo de comportamiento subyacente no implementa la interfaz IServiceBehavior.|  
|ConfigMessageEncodingAlreadyInBinding|No puede agregar el elemento de codificación de mensajes concreto. Otro elemento de codificación de mensajes ya existe en el enlace concreto. Solo puede haber un elemento de codificación de mensajes para cada enlace.|  
|ConfigNoExtensionCollectionAssociatedWithType|No puede encontrar la colección de extensiones asociada a la extensión del tipo específico.|  
|ConfigSectionNotFound|No se puede crear la sección de configuración concreta. Al archivo Machine.config le falta información. Compruebe que esta sección de configuración esté correctamente registrada y que ha escrito correctamente el nombre de sección. Para las secciones Windows Communication Foundation, ejecute ServiceModelReg.exe -i para corregir este error.|  
|ConfigTransportAlreadyInBinding|No puede agregar el elemento de transporte concreto. Otro elemento de transporte ya existe en el enlace concreto. Solo puede haber un elemento de codificación de mensajes para cada enlace.|
