---
title: Consideraciones de seguridad con metadatos
ms.date: 03/30/2017
ms.assetid: e78ef8ab-4f63-4656-ab93-b1deab2666d5
ms.openlocfilehash: c41ebf5c39e74932a4bade610c4e236b28444327
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601028"
---
# <a name="security-considerations-with-metadata"></a>Consideraciones de seguridad con metadatos
Al usar las características de metadatos en Windows Communication Foundation (WCF), tenga en cuenta las implicaciones de seguridad de la publicación, recuperación y uso de los metadatos de servicio.  
  
## <a name="when-to-publish-metadata"></a>Cuándo publicar metadatos  
 Los servicios WCF no publican metadatos de forma predeterminada. Para publicar los metadatos de un servicio WCF, debe habilitar explícitamente la publicación de metadatos agregando extremos de metadatos al servicio (consulte [metadatos de publicación](publishing-metadata.md)). Deshabilitar la publicación de metadatos reduce la superficie de ataque de su servicio y disminuye el riesgo de divulgación involuntaria de información. No todos los servicios deben publicar metadatos. Si no tiene que publicar metadatos, considere el mantener esta opción desactivada. Tenga en cuenta que todavía puede generar metadatos y código de cliente directamente desde los ensamblados del servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Para obtener más información sobre cómo usar SvcUtil. exe para exportar metadatos, vea [Cómo: usar SvcUtil. exe para exportar metadatos desde el código de servicio compilado](how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md).  
  
## <a name="publishing-metadata-using-a-secure-binding"></a>Publicar metadatos mediante un enlace seguro  
 Los enlaces de metadatos predeterminados que proporciona WCF no son seguros y permiten el acceso anónimo a los metadatos. Los metadatos de servicio que publica un servicio WCF contienen una descripción detallada del servicio y pueden contener información confidencial intencionada o accidentalmente. Por ejemplo, los metadatos de servicio pueden contener información sobre operaciones de infraestructura que no se tenía intención de divulgar públicamente. Para proteger los metadatos de servicio de los accesos no autorizados, utilice un enlace de seguridad para el punto de conexión de los metadatos. Los puntos de conexión de metadatos responden a las solicitudes HTTP/GET que pueden utilizar la capa de sockets seguros (SSL) para proteger los metadatos. Para obtener más información, consulte [Cómo: proteger los extremos de metadatos](how-to-secure-metadata-endpoints.md).  
  
 La protección de los puntos de conexión de metadatos también proporciona un método para que los solicitantes recuperen metadatos de servicio de manera segura, sin el riesgo de manipulación o suplantación.  
  
## <a name="using-only-trusted-metadata"></a>Utilización únicamente de metadatos de confianza  
 Se pueden utilizar metadatos de servicio para construir automáticamente los componentes en tiempo de ejecución necesarios para llamar al servicio. Asimismo, pueden utilizarse metadatos en tiempo de diseño para desarrollar una aplicación cliente, o en el tiempo de ejecución para actualizar dinámicamente el enlace utilizado por un cliente para llamar a un servicio.  
  
 Los metadatos de servicio pueden manipularse o suplantarse cuando se recuperan de manera insegura. Los metadatos modificados pueden redirigir el cliente a un servicio malintencionado, incluir parámetros de seguridad comprometedores o contener estructuras XML malintencionadas. Los documentos de metadatos pueden ser grandes y con frecuencia se almacenan en el sistema de archivos. Para protegerse de la manipulación y suplantación, use un enlace seguro para solicitar los metadatos de servicio cuando haya uno disponible.  
  
## <a name="using-safe-techniques-for-processing-metadata"></a>Utilización de técnicas seguras para procesar metadatos  
 Con frecuencia, los metadatos de servicio se recuperan desde un servicio, a través de una red, utilizando protocolos normalizados como WS-MetadataExchange (MEX). Muchos formatos de metadatos incluyen mecanismos de referencia que señalan a metadatos adicionales. El tipo <xref:System.ServiceModel.Description.MetadataExchangeClient> procesa automáticamente las referencias a documentos del lenguaje de descripción de servicios Web (WSDL), el esquema XML y documentos MEX. El tamaño del objeto <xref:System.ServiceModel.Description.MetadataSet> creado a partir de los metadatos recuperados es directamente proporcional al valor <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> para la instancia <xref:System.ServiceModel.Description.MetadataExchangeClient> que se utiliza, y el valor `MaxReceivedMessageSize` para el enlace utilizado por esa instancia <xref:System.ServiceModel.Description.MetadataExchangeClient>. Establezca estas cuotas en los valores adecuados siguiendo el dictado de su escenario.  
  
 En WCF, los metadatos de servicio se procesan como XML. Cuando se procesan documentos XML, las aplicaciones deberían protegerse de las estructuras XML malintencionadas. Use el <xref:System.Xml.XmlDictionaryReader> con las cuotas adecuadas al procesar XML y también establezca la <xref:System.Xml.XmlTextReader.DtdProcessing%2A> propiedad en <xref:System.Xml.DtdProcessing.Prohibit> .  
  
 El sistema de metadatos de WCF es extensible y las extensiones de metadatos pueden registrarse en el archivo de configuración de la aplicación (consulte [extensión del sistema de metadatos](../extending/extending-the-metadata-system.md)). Las extensiones de metadatos pueden ejecutar código arbitrario, por lo que debería proteger su archivo de configuración de la aplicación con listas de control de acceso (ACL) adecuadas, y registrar sólo implementaciones de extensión de metadatos de confianza.  
  
## <a name="validating-generated-clients"></a>Validación de los clientes generados  
 Al generar código de cliente a partir de los metadatos recuperados de un origen que no es de confianza, valide el código de cliente generado para asegurarse de que el cliente generado cumple las directivas de seguridad de las aplicaciones cliente. Puede utilizar un comportamiento de validación para comprobar los valores del enlace del cliente o, inspeccionar visualmente el código generado mediante herramientas. Para obtener un ejemplo de cómo implementar un cliente que valida los comportamientos, consulte [validación de cliente](../samples/client-validation.md).  
  
## <a name="protecting-application-configuration-files"></a>Protección de los archivos de configuración de la aplicación  
 El archivo de configuración de la aplicación de un servicio puede controlar si se publican metadatos y cómo. Es recomendable proteger el archivo de configuración de la aplicación con listas de control de acceso (ACL) adecuadas, para asegurarse de que un atacante no pueda modificar esos valores.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para proteger puntos de conexión de metadatos](how-to-secure-metadata-endpoints.md)
- [Seguridad](security.md)
