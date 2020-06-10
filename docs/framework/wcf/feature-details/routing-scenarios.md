---
title: Escenarios de enrutamiento
ms.date: 03/30/2017
helpviewer_keywords:
- routing [WCF], scenarios
ms.assetid: ec22f308-665a-413e-9f94-7267cb665dab
ms.openlocfilehash: 455a6e42aea064d48846994b4e729b90667bc8e1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590506"
---
# <a name="routing-scenarios"></a>Escenarios de enrutamiento
Aunque el servicio de enrutamiento es muy personalizable, puede ser un desafío para diseñar una lógica de enrutamiento eficaz al crear una nueva configuración desde el principio.  Sin embargo, hay varios escenarios comunes que sigue la mayoría de las configuraciones del servicio de enrutamiento. Aunque puede que estos escenarios no se apliquen directamente a su configuración concreta, el hecho de saber cómo se puede configurar el servicio de enrutamiento para administrar estos escenarios le ayudará a entender el servicio de enrutamiento.  
  
## <a name="common-scenarios"></a>Escenarios comunes  
 El uso más básico del servicio de enrutamiento es agregar varios extremos de destino para reducir el número de extremos expuestos en las aplicaciones cliente y, a continuación, usar filtros de mensajes para enrutar cada mensaje al destino correcto. Los mensajes se pueden enrutar en función de requisitos de procesamiento físicos o lógicos, como un tipo de mensaje que debe ser procesado por un servicio concreto, o en función de necesidades del negocio arbitrarias, como proporcionar procesamiento de prioridad de mensajes a partir de un origen concreto. En la siguiente tabla, se muestra una lista de algunos de los escenarios comunes y cuándo se producen:  
  
|Escenario|Cuándo se utiliza|  
|--------------|--------------|  
|Control de versiones de servicios|Debe admitir varias versiones de un servicio o puede implementar un servicio actualizado en el futuro|  
|Particionar datos de servicio|Debe crear una partición de un servicio en varios hosts|  
|Actualización dinámica|Debe reconfigurar dinámicamente la lógica de enrutamiento en el tiempo de ejecución para administrar el cambio de implementaciones de servicio|  
|Multidifusión|Debe enviar un mensaje a varios puntos de conexión|  
|Puente protocolar|Recibe mensajes en un protocolo de transporte, y el punto de conexión del destino utiliza un protocolo diferente|  
|Tratamiento de errores|Necesita proporcionar resistencia ante los cortes de la red y los errores de comunicación|  
  
> [!NOTE]
> Aunque muchos de los escenarios presentados son específicos de ciertas necesidades empresariales o requisitos de procesamiento, la planificación de soporte de actualizaciones dinámicas y el empleo del control de errores se pueden considerar a menudo como prácticas recomendadas, ya que le permiten modificar la lógica de enrutamiento en el tiempo de ejecución y recuperarse de errores transitorios de la red y errores de comunicación.  
  
### <a name="service-versioning"></a>Control de versiones del servicio  
 Al introducir una nueva versión de un servicio, a menudo debe mantener la versión anterior hasta que todos los clientes hayan pasado al nuevo servicio. Esto es especialmente importante si el servicio es un proceso de ejecución prolongada que tarda días, semanas o, incluso, meses completarse. Normalmente, esto requiere la implementación de una nueva dirección de extremo para el nuevo servicio mientras se mantiene el extremo original para la versión anterior.  
  
 Utilizando el servicio de enrutamiento, puede exponer un punto de conexión para recibir mensajes de aplicaciones cliente y, a continuación, enrutar cada mensaje a la versión de servicio correcta en función del contenido del mensaje. La implementación más básica implica agregar un encabezado personalizado al mensaje que indica la versión del servicio con el que se procesará el mensaje. El servicio de enrutamiento puede utilizar XPathMessageFilter para inspeccionar cada mensaje con el fin de detectar la presencia del encabezado personalizado y enrutar el mensaje al punto de conexión de destino adecuado.  
  
 Para conocer los pasos utilizados para crear una configuración de control de versiones de servicio, consulte [How to: Service Versioning](how-to-service-versioning.md).
  
### <a name="service-data-partitioning"></a>Particionar datos de servicio  
 Al diseñar un entorno distribuido, a menudo es conveniente repartir la carga de procesamiento entre varios equipos para proporcionar una alta disponibilidad, disminuir la carga de procesamiento en equipos individuales o proporcionar recursos dedicados para un determinado subconjunto de mensajes. Aunque el servicio de enrutamiento no reemplaza una solución de equilibrio de carga dedicada, su capacidad de realizar un enrutamiento basado en el contenido se puede utilizar para enrutar de otro modo mensajes similares a destinos concretos. Por ejemplo, puede tener un requisito para procesar mensajes de un cliente concreto por separado de los mensajes recibidos de otros clientes.  
  
 Para obtener información sobre los pasos utilizados para crear una configuración de particiones de datos de servicio, consulte [Cómo: crear particiones de datos de servicio](how-to-service-data-partitioning.md).  
  
### <a name="dynamic-routing"></a>Enrutamiento dinámico  
 A menudo, es conveniente modificar la configuración de enrutamiento para satisfacer las cambiantes necesidades empresariales, como agregar una ruta a una versión más reciente de un servicio, cambiar los criterios de enrutamiento o cambiar el punto de conexión de destino de un mensaje determinado al que enruta el filtro. El servicio de enrutamiento le permite hacer esto a través de <xref:System.ServiceModel.Routing.RoutingExtension>, que le permite proporcionar un nuevo RoutingConfiguration durante el tiempo de ejecución. La nueva configuración surte efecto inmediatamente, pero solo afecta a cualquier sesión nueva procesada mediante el servicio de enrutamiento.  
  
 Para conocer los pasos que se usan para implementar el enrutamiento dinámico, consulte [Cómo: actualización dinámica](how-to-dynamic-update.md).
  
### <a name="multicast"></a>Multidifusión  
 Al enrutar mensajes, normalmente enruta cada mensaje a un extremo de destino concreto.  Sin embargo, algunas veces, puede necesitar enrutar una copia del mensaje a varios puntos de conexión de destino. Para realizar un enrutamiento de multidifusión, deben cumplirse las siguientes condiciones:  
  
- La forma del canal no puede ser de solicitud-respuesta (aunque sí unidireccional o dúplex), porque, en caso de solicitud-respuesta, la aplicación cliente solo puede recibir una respuesta para cada solicitud.  
  
- Varios filtros deben devolver **true** al evaluar el mensaje.  
  
 Si se cumplen estas condiciones, cada punto de conexión de destino asociado a un filtro que devuelva un valor verdadero recibirá una copia del mensaje.  
  
### <a name="protocol-bridging"></a>Puente protocolar  
 Al enrutar mensajes entre protocolos de SOAP diferentes entre sí, el servicio de enrutamiento utiliza API de WCF para convertir el mensaje de un protocolo al otro. Esto se produce automáticamente cuando el extremo de servicio expuesto por el servicio de enrutamiento usa un protocolo diferente al de los extremos de cliente a los que se enrutan los mensajes. Es posible deshabilitar este comportamiento si los protocolos en uso no son estándar; sin embargo, en ese caso, debe proporcionar su propio código de puente.
  
### <a name="error-handling"></a>Tratamiento de errores  
 En un entorno distribuido, no es raro encontrar errores transitorios de red o errores de comunicación. Sin un servicio intermedio como el servicio de enrutamiento, la carga de administrar tales errores recae en la aplicación cliente. Si la aplicación cliente no incluye una lógica concreta para realizar reintentos en caso de producirse errores de la red o errores de comunicación ni conocimiento de ubicaciones alternativas, el usuario puede encontrarse con escenarios donde un mensaje tenga que enviarse varias veces antes de ser procesado correctamente por el servicio de destino. Esto puede hacer que el cliente esté descontento con la aplicación, ya que se puede percibir como no confiable.  
  
 El servicio de enrutamiento intenta solucionar este escenario proporcionando capacidades de control de errores sólidas para los mensajes que se encuentran con errores de la red o errores relacionados con la comunicación. Al crear una lista de posibles extremos de destino y asociar esta lista a cada filtro de mensajes, elimina el punto de concentración de errores que se produce cuando solo hay un destino posible. En caso de error, el servicio de enrutamiento intentará entregar el mensaje al punto de conexión siguiente de la lista hasta que se entregue el mensaje, se produzca un error no relacionado con la comunicación o se hayan agotado todos los puntos de conexión.  
  
 Para conocer los pasos utilizados para configurar el control de errores, consulte [How to: control de errores](how-to-error-handling.md).
  
### <a name="in-this-section"></a>En esta sección  
 [Cómo Control de versiones del servicio](how-to-service-versioning.md)  
  
 [Cómo Particionar datos de servicio](how-to-service-data-partitioning.md)  
  
 [Cómo actualización dinámica](how-to-dynamic-update.md)  
  
 [Cómo Control de errores](how-to-error-handling.md)  
  
## <a name="see-also"></a>Vea también

- [Introducción al enrutamiento](routing-introduction.md)
