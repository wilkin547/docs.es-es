---
title: "Consideraciones de seguridad con metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e78ef8ab-4f63-4656-ab93-b1deab2666d5
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# Consideraciones de seguridad con metadatos
Cuando se usan las características de metadatos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], deben tenerse en cuenta las implicaciones de seguridad de la publicación, recuperación y utilización de los metadatos del servicio.  
  
## Cuándo publicar metadatos  
 Los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no publican datos de manera predeterminada.  Para publicar metadatos de un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], debe habilitarse explícitamente la publicación de metadatos agregando los extremos de metadatos al servicio \(vea [Publicación de metadatos](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)\).  Deshabilitar la publicación de metadatos reduce la superficie de ataque de su servicio y disminuye el riesgo de divulgación involuntaria de información.  No todos los servicios deben publicar metadatos.  Si no tiene que publicar metadatos, considere el mantener esta opción desactivada.  Observe que todavía puede generar metadatos y código de cliente directamente desde los ensamblados del servicio mediante [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo usar Svcutil.exe para exportar metadatos, vea [Cómo: Utilizar Svcutil.exe para exportar metadatos desde el código de servicio compilado](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md).  
  
## Publicar metadatos mediante un enlace seguro  
 Los enlaces de metadatos predeterminados que proporciona [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no son seguros y permiten el acceso anónimo a los metadatos.  Los metadatos de servicio que un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] publica contienen una descripción detallada del servicio y pueden incluir, de manera intencionada o involuntaria, información confidencial.  Por ejemplo, los metadatos de servicio pueden contener información sobre operaciones de infraestructura que no se tenía intención de divulgar públicamente.  Para proteger los metadatos de servicio de los accesos no autorizados, utilice un enlace de seguridad para el extremo de los metadatos.  Los extremos de metadatos responden a las solicitudes HTTP\/GET que pueden utilizar la capa de sockets seguros \(SSL\) para proteger los metadatos.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Cómo: Proteger los extremos de metadatos](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md).  
  
 La protección de los extremos de metadatos también proporciona un método para que los solicitantes recuperen metadatos de servicio de manera segura, sin el riesgo de manipulación o suplantación.  
  
## Utilización únicamente de metadatos de confianza  
 Se pueden utilizar metadatos de servicio para construir automáticamente los componentes en tiempo de ejecución necesarios para llamar al servicio.  Asimismo, pueden utilizarse metadatos en tiempo de diseño para desarrollar una aplicación cliente, o en el tiempo de ejecución para actualizar dinámicamente el enlace utilizado por un cliente para llamar a un servicio.  
  
 Los metadatos de servicio pueden manipularse o suplantarse cuando se recuperan de manera insegura.  Los metadatos modificados pueden redirigir el cliente a un servicio malintencionado, incluir parámetros de seguridad comprometedores o contener estructuras XML malintencionadas.  Los documentos de metadatos pueden ser grandes y con frecuencia se almacenan en el sistema de archivos.  Para protegerse de la manipulación y suplantación, use un enlace seguro para solicitar los metadatos de servicio cuando haya uno disponible.  
  
## Utilización de técnicas seguras para procesar metadatos  
 Con frecuencia, los metadatos de servicio se recuperan desde un servicio, a través de una red, utilizando protocolos normalizados como WS\-MetadataExchange \(MEX\).  Muchos formatos de metadatos incluyen mecanismos de referencia que señalan a metadatos adicionales.  El tipo <xref:System.ServiceModel.Description.MetadataExchangeClient> procesa automáticamente las referencias a documentos del lenguaje de descripción de servicios Web \(WSDL\), el esquema XML y documentos MEX.  El tamaño del objeto <xref:System.ServiceModel.Description.MetadataSet> creado a partir de los metadatos recuperados es directamente proporcional al valor <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> para la instancia <xref:System.ServiceModel.Description.MetadataExchangeClient> que se utiliza, y el valor `MaxReceivedMessageSize` para el enlace utilizado por esa instancia <xref:System.ServiceModel.Description.MetadataExchangeClient>.  Establezca estas cuotas en los valores adecuados siguiendo el dictado de su escenario.  
  
 En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los metadatos de servicio se procesan como XML.  Cuando se procesan documentos XML, las aplicaciones deberían protegerse de las estructuras XML malintencionadas.  Use `XmlDictionaryReader` con cuotas adecuadas para procesar XML y establezca también la propiedad <xref:System.XML.XmlReaderSettings.ProhibitDtd%2A> del objeto <xref:System.Xml.XmlReaderSettings> de modo que la instancia de <xref:System.Xml.XmlReader> sea `true`.  
  
 El sistema de metadatos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es extensible, y las extensiones de metadatos pueden registrarse en el archivo de configuración de la aplicación \(vea [Extensión del sistema de metadatos](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)\).  Las extensiones de metadatos pueden ejecutar código arbitrario, por lo que debería proteger su archivo de configuración de la aplicación con listas de control de acceso \(ACL\) adecuadas, y registrar sólo implementaciones de extensión de metadatos de confianza.  
  
## Validación de los clientes generados  
 Al generar código de cliente a partir de los metadatos recuperados de un origen que no es de confianza, valide el código de cliente generado para asegurarse de que el cliente generado cumple las directivas de seguridad de las aplicaciones cliente.  Puede utilizar un comportamiento de validación para comprobar los valores del enlace del cliente o, inspeccionar visualmente el código generado mediante herramientas.  Para consultar un ejemplo de cómo implementar un cliente que valida comportamientos, vea [Validación de cliente](../../../../docs/framework/wcf/samples/client-validation.md).  
  
## Protección de los archivos de configuración de la aplicación  
 El archivo de configuración de la aplicación de un servicio puede controlar si se publican metadatos y cómo.  Es recomendable proteger el archivo de configuración de la aplicación con listas de control de acceso \(ACL\) adecuadas, para asegurarse de que un atacante no pueda modificar esos valores.  
  
## Vea también  
 [Cómo: Proteger los extremos de metadatos](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md)   
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)