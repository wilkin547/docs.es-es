---
description: Más información acerca de la extensión de ServiceHost y el nivel de modelo de servicio
title: Extensión de ServiceHost y la capa de modelos de servicios
ms.date: 03/30/2017
helpviewer_keywords:
- extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
ms.openlocfilehash: 446c02fbbb2391a4cc9c08c9e42f2194dfbcf9b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735067"
---
# <a name="extending-servicehost-and-the-service-model-layer"></a>Extensión de ServiceHost y la capa de modelos de servicios

El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada. Las extensiones de modelo de servicio modifican o implementan el comportamiento de la comunicación o la ejecución y características implicadas en la funcionalidad de distribuidor o cliente, comportamientos personalizados, interceptación de mensajes y parámetros, y otra funcionalidad de extensibilidad.  
  
## <a name="in-this-section"></a>En esta sección  

 [Extensión de clientes](extending-clients.md)  
 Describe las interfaces que pueden interceptar y modificar el tiempo de ejecución del cliente, así como las clases en las que puede insertar sus extensiones personalizadas en aplicaciones cliente. Por ejemplo, puede realizar el registro de mensajes del cliente personalizado, realizar serialización del mensaje personalizada, etc.  
  
 [Extensión de distribuidores](extending-dispatchers.md)  
 Describe las interfaces que pueden interceptar y modificar el tiempo de ejecución del servicio, así como las clases en las que puede insertar sus extensiones personalizadas en aplicaciones de servicio. Por ejemplo, puede realizar el registro de servicio personalizado, la validación de mensajes del lado de servicio, distribución personalizada, etc.  
  
 [Objetos extensibles](extensible-objects.md)  
 Describe los cinco objetos extensibles y el patrón <xref:System.ServiceModel.IExtensibleObject%601>. El patrón de objeto extensible se utiliza para extender clases de tiempo de ejecución existentes con nueva funcionalidad o para agregar un nuevo estado a un objeto. Las extensiones, asociadas a uno de los objetos extensibles, permiten que los comportamientos en fases muy diferentes de procesamiento tengan acceso al estado compartido y funcionalidad adjuntos a un objeto extensible común al que pueden tener acceso.  
  
 [Configuración y extensión del tiempo de ejecución con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md)  
 Para cambiar la configuración o insertar extensiones en el tiempo de ejecución de WCF, use comportamientos. WCF incluye comportamientos implementados por el sistema para controlar la limitación de peticiones, la creación de instancias y muchos otros aspectos de servicios y operaciones. En esta sección se describe cómo crear sus propios comportamientos personalizados y cómo hacer que estén disponibles para el uso tanto a nivel de programación como utilizando archivos de configuración.  
  
 [Extensión del hospedaje mediante ServiceHostFactory](extending-hosting-using-servicehostfactory.md)  
 Describe cómo extender <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>y utilizar las clases <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> para personalizar el entorno del host.  
  
## <a name="reference"></a>Referencia  
  
## <a name="related-sections"></a>Secciones relacionadas
