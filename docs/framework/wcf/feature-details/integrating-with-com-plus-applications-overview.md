---
description: 'Más información acerca de: integración con aplicaciones COM+ información general'
title: Integración en la información general de las aplicaciones COM+
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: e481e48f-7096-40eb-9f20-7f0098412941
ms.openlocfilehash: c24ce95651aff222b8374243143afc7166406fcf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802793"
---
# <a name="integrating-with-com-applications-overview"></a>Integración en la información general de las aplicaciones COM+

Windows Communication Foundation (WCF) proporciona un entorno completo para crear aplicaciones distribuidas. Si ya usa la lógica de aplicación basada en componentes hospedada en COM+, puede usar WCF para ampliar la lógica existente en lugar de tener que volver a escribirla. Un escenario común es cuando se quiere exponer una lógica de negocio de Enterprise Services o COM+ mediante servicios web.  
  
 Cuando una interfaz en un componente COM+ se expone como un servicio web, la especificación y contrato de estos servicios se determina por una asignación automática realizada cuando se inicia la aplicación. La lista siguiente muestra el modelo conceptual para esta asignación:  
  
- Un servicio se define para cada clase COM expuesta.  
  
- El contrato para el servicio se deriva directamente de la definición de interfaz del componente seleccionado con la posibilidad de exclusión de método definida en la configuración.  
  
- Las operaciones en ese contrato se derivan directamente de los métodos en la definición de interfaz del componente.  
  
- Los parámetros para esas operaciones se derivan directamente del tipo de interoperabilidad COM que corresponde a los parámetros de método del componente.  
  
 Las direcciones y enlaces de transporte predeterminados para el servicio son proporcionadas en un archivo de configuración de servicio, pero se pueden reconfigurar si se necesita.  
  
> [!NOTE]
> Los contratos para los servicios web expuestos siguen siendo constantes siempre que las interfaces COM+ y la configuración no se modifiquen. Una modificación a varias interfaces no actualiza automáticamente los servicios disponibles y requiere que se ejecute de nuevo la herramienta COM+ Service Model Configuration (ComSvcConfig.exe).  
  
 Los requisitos de autorización y autenticación de la aplicación COM+ y sus componentes se siguen necesitando cuando se usan como un servicio web.  
  
 Si el llamador inicia una transacción del servicio web, los componentes marcados como transaccionales se inscriben dentro de ese ámbito de la transacción.  
  
 Se exige a los pasos siguientes que expongan una interfaz de componente de COM+ como un servicio web sin modificar el componente:  
  
1. Determine si la interfaz de componente de COM+ se puede exponer como un servicio web.  
  
2. Seleccione un modo de alojamiento adecuado.  
  
3. Use la herramienta de configuración del modelo de servicio COM+ (ComSvcConfig.exe) para agregar un servicio web para la interfaz. Para obtener más información sobre cómo usar ComSvcConfig.exe, consulte [Cómo: usar la herramienta de configuración del modelo de servicio com+](how-to-use-the-com-service-model-configuration-tool.md).  
  
4. Configure las opciones de servicio adicionales en el archivo de configuración de la aplicación. Para obtener más información acerca de cómo configurar un componente, consulte [Cómo: configurar el servicio com+](how-to-configure-com-service-settings.md).  
  
## <a name="supported-interfaces"></a>Interfaces admitidas  

 Hay algunas restricciones en el tipo de interfaces que se pueden exponer como un servicio web. No se admiten los siguientes tipos de interfaz:  
  
- Interfaces que pasan referencias de objeto como parámetros: el siguiente enfoque de referencia de objeto limitado se describe en la sección Compatibilidad de referencia de objeto limitado.  
  
- Interfaces que pasan tipos que no son compatibles con las conversiones de interoperabilidad de COM .NET Framework.  
  
- Interfaces para las aplicaciones que tienen la agrupación de aplicaciones habilitadas cuando lo hospedan COM+.  
  
- Interfaces de componentes que se marcan como privado en la aplicación.  
  
- Interfaces de infraestructura COM+.  
  
- Interfaces de la aplicación de sistema.  
  
- Interfaces de los componentes de Enterprise Services no agregados a la caché global de ensamblados.  
  
### <a name="limited-object-reference-support"></a>Compatibilidad limitada de referencia de objeto  

 Dado que varios componentes implementados de COM+ utilizan objetos por parámetros de referencia, como devolver un objeto ADO Recordset, la integración de COM+ incluye compatibilidad limitada para los parámetros de referencia de objeto. La compatibilidad se limita a los objetos que implementan la interfaz COM `IPersistStream`. Esto incluye los objetos ADO Recordset y se puede implementar para objetos COM específicos de la aplicación.  
  
 Para habilitar esta compatibilidad, la herramienta ComSvcConfig.exe proporciona el modificador **allowreferences** que deshabilita el parámetro de firma de método normal y comprueba que la herramienta se ejecuta para asegurarse de que no se utilizan parámetros de referencia de objeto. Además, los tipos de objeto que se pasan como parámetros se deben denominar e identificar en el <`persistableTypes`> elemento de configuración que es un elemento secundario del `comContract` elemento de> <.  
  
 Cuando se usa esta característica, el servicio de integración de COM+ utiliza la interfaz `IPersistStream` para serializar o deserializar la instancia de objeto. Si la instancia de objeto no es compatible con `IPersistStream`, se producirá una excepción.  
  
 Dentro de una aplicación de cliente, los métodos en el objeto <xref:System.ServiceModel.ComIntegration.PersistStreamTypeWrapper> se pueden utilizar para pasar un objeto a un servicio y de igual forma recuperar un objeto.  
  
> [!NOTE]
> Debido a la naturaleza personalizada y específica de la plataforma del enfoque de serialización, es más adecuado para su uso entre clientes de WCF y servicios WCF.  
  
## <a name="selecting-the-hosting-mode"></a>Seleccionar el modo de hospedaje  

 COM+ expone servicios web en uno de los modos de hospedaje siguientes:  
  
- Hospedaje en COM  
  
     El servicio web se hospeda dentro del proceso de servidor de COM+ dedicado a la aplicación (Dllhost.exe). Este modo exige que se inicie la aplicación exactamente antes de que pueda recibir solicitudes del servicio web. Las opciones COM+ "Ejecutar como servicio NT” o "Dejar ejecutándose cuando está inactivo" se pueden utilizar para evitar el cierre por inactividad de la aplicación y sus servicios. Este modo proporciona acceso tanto al servicio web como a DCOM a la aplicación de servidor.  
  
- Hospedado por Web  
  
     El servicio web se hospeda dentro de un proceso de trabajo de servidor web. Este modo no le exige a COM+ que esté activo cuando se recibe la solicitud inicial. Si la aplicación no está activa cuando se recibe esta solicitud, se activa automáticamente antes de procesar la solicitud. Este modo también proporciona acceso a la aplicación de servidor tanto al servicio web como a DCOM, pero produce un salto del proceso para las solicitudes del servicio web. Esto exige normalmente que el cliente habilite la suplantación. En WCF, esto se puede hacer con la <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> propiedad de la <xref:System.ServiceModel.Security.WindowsClientCredential> clase, a la que se tiene acceso como una propiedad de la <xref:System.ServiceModel.ChannelFactory%601> clase genérica, así como el <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> valor de enumeración.  
  
- Hospedaje en web en proceso  
  
     La lógica del servicio web y de la aplicación COM+ se hospedan dentro del proceso de trabajo del servidor web. Esto proporciona la activación automática del modo de hospedaje en web sin producir un salto del proceso para las solicitudes del servicio web. El inconveniente es que no se puede tener acceso a la aplicación de servidor a través de DCOM.  
  
### <a name="security-considerations"></a>Consideraciones sobre la seguridad  

 Al igual que otros servicios de WCF, la configuración de seguridad para el servicio expuesto se administra a través de los valores de configuración del canal de WCF. No se exige la configuración de seguridad de DCOM tradicional, como los valores de permisos de  equipo de DCOM. Para exigir las funciones de aplicación COM+, la autorización de “comprobaciones de acceso de nivel de componente” ha de estar habilitada para el componente.  
  
 El uso de un enlace no seguro hace vulnerable la comunicación a manipulaciones o a divulgación de información. Para evitar esto, se recomienda que utilice un enlace seguro.  
  
 Para los modos de hospedaje en COM+ y web, las aplicaciones de cliente deben permitir al proceso de servidor suplantar al usuario del cliente. Esto puede realizarse en los clientes de WCF estableciendo el nivel de suplantación en <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> .  
  
 Si Internet Information Server (IIS) o el Servicio de activación de procesos de Windows (WAS) utilizan transporte HTTP, la herramienta Httpcfg.exe se puede utilizar para reservar una dirección de punto de conexión de transporte. En otras configuraciones es importante proteger contra servicios maliciosos que actúan como el servicio intencional. Para evitar que un servicio malicioso se inicie en el punto de conexión deseado, el servicio legítimo se puede configurar para que se ejecute como un servicio NT. Esto permite que el servicio legítimo exija la dirección del punto de conexión antes que cualquier servicio malicioso.  
  
 Al exponer una aplicación COM+ con roles COM+ configurados como un servicio hospedado en Web, se debe agregar la "iniciar cuenta de proceso de IIS" a uno de los roles de la aplicación. Esta cuenta, que suele tener el nombre IWAM_machinename, se debe agregar para habilitar el apagado limpio de objetos después del uso. No se le deberían otorgar permisos adicionales a esta cuenta.  
  
 Las características de reciclaje de proceso de COM+ no se pueden utilizar en aplicaciones integradas. Si la aplicación se configura para utilizar reciclaje de proceso y los componentes se ejecutan en un proceso hospedado por COM+, el servicio no se inicia. Este requisito no incluye servicios del modo en proceso de hospedaje en web porque no se aplica la configuración de reciclaje de proceso.  
  
## <a name="see-also"></a>Vea también

- [Integración con la información general de las aplicaciones COM](integrating-with-com-applications-overview.md)
